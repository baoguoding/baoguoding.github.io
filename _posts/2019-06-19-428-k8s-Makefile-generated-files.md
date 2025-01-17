---
layout: post
title: 解读K8S Makefile.generated_files
pid: 428
tags: [k8s]
---

# 文件路径

Makefile -> build/root/Makefile.generated_files

make -f Makefile.generated_files generated_files CALLED_FROM_MAIN_MAKEFILE=1

# 准备工作

```shell
ifeq ($(CALLED_FROM_MAIN_MAKEFILE),)
    $(error Please use the main Makefile, e.g. `make generated_files`)
endif

# Don't allow an implicit 'all' rule.  This is not a user-facing file.
ifeq ($(MAKECMDGOALS),)
    $(error This Makefile requires an explicit rule to be specified)
endif

ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** starting Makefile.generated_files for goal(s) "$(MAKECMDGOALS)")
    $(warning ***** $(shell date))
endif

SHELL := /bin/bash
```

# This rule collects all the generated file sets into a single rule.  Other
# rules should depend on this to ensure generated files are rebuilt.
.PHONY: generated_files
generated_files: gen_deepcopy gen_defaulter gen_conversion gen_openapi gen_bindata

#
# Helper logic to calculate Go's dependency DAG ourselves.
#

# This is a file that will be emitted by the go2make tool, containing a
# variable for each Go package in the project (including deps) which lists all
# of the transitive deps of that package.  Each variable is named the same as
# the package - for example the variable for `k8s.io/kubernetes/pkg/api` is
# $(k8s.io/kubernetes/pkg/api).  This is roughly the same DAG that the Go
# compiler uses.  These variables can be used to figure out if, for example,
# generated code needs to be regenerated.
GO_PKGDEPS_FILE = go-pkgdeps.mk

# Include the Go package dependencies file.  This will cause the rule of
# the same name to be considered and if it is updated, make will restart and
# reload the updated deps.
sinclude $(META_DIR)/$(GO_PKGDEPS_FILE)

# Update the set of Go deps for our project.  This will let us determine if
# we really need to do expensive codegen.  We use FORCE because it is not a
# PHONY file, but we do want it to be re-evaluated every time make is run.  The
# file will only be touched if it actually changes.
$(META_DIR)/$(GO_PKGDEPS_FILE): FORCE
	if [[ "$(DBG_CODEGEN)" == 1 ]]; then          \
	    echo "DBG: calculating Go dependencies";  \
	fi
	hack/run-in-gopath.sh go install ./hack/make-rules/helpers/go2make
	hack/run-in-gopath.sh go2make                     \
	    k8s.io/kubernetes/...                         \
	    --prune  k8s.io/kubernetes/staging            \
	    --prune  k8s.io/kubernetes/vendor             \
	    k8s.io/kubernetes/vendor/k8s.io/...           \
	    github.com/jteeuwen/go-bindata/go-bindata/... \
	    > $@.tmp
	if ! cmp -s $@.tmp $@; then                       \
	    if [[ "$(DBG_CODEGEN)" == 1 ]]; then          \
	        echo "DBG: $(GO_PKGDEPS_FILE) changed";   \
	    fi;                                           \
	    cat $@.tmp > $@;                              \
	fi
	rm -f $@.tmp

.PHONY: FORCE
FORCE:

#
# Helper logic to find which directories need codegen as quickly as possible.
#

# This variable holds a list of every directory that contains Go files in this
# project.  Other rules and variables can use this as a starting point to
# reduce filesystem accesses.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all *.go dirs)
endif
ALL_GO_DIRS := $(shell                                                   \
    hack/make-rules/helpers/cache_go_dirs.sh $(META_DIR)/all_go_dirs.mk  \
)

# Generate a list of all files that have a `+k8s:` comment-tag.  This will be
# used to derive lists of files/dirs for generation tools.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all +k8s: tags)
endif
ALL_K8S_TAG_FILES := $(shell                             \
    find $(ALL_GO_DIRS) -maxdepth 1 -type f -name \*.go  \
        | xargs grep --color=never -l '^// *+k8s:'       \
)


#
# Code generation logic.
#


# Deep-copy generation
#
# Any package that wants deep-copy functions generated must include a
# comment-tag in column 0 of one file of the form:
#     // +k8s:deepcopy-gen=<VALUE>
#
# The <VALUE> may be one of:
#     generate: generate deep-copy functions into the package
#     register: generate deep-copy functions and register them with a
#               scheme

# The result file, in each pkg, of deep-copy generation.
DEEPCOPY_BASENAME := $(GENERATED_FILE_PREFIX)deepcopy
DEEPCOPY_FILENAME := $(DEEPCOPY_BASENAME).go

# The tool used to generate deep copies.
DEEPCOPY_GEN := $(BIN_DIR)/deepcopy-gen

# Find all the directories that request deep-copy generation.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all +k8s:deepcopy-gen tags)
endif
DEEPCOPY_DIRS := $(shell                                             \
    grep --color=never -l '+k8s:deepcopy-gen=' $(ALL_K8S_TAG_FILES)  \
        | xargs -n1 dirname                                          \
        | LC_ALL=C sort -u                                           \
)
DEEPCOPY_FILES := $(addsuffix /$(DEEPCOPY_FILENAME), $(DEEPCOPY_DIRS))

# Reset the list of packages that need generation.
$(shell mkdir -p $$(dirname $(META_DIR)/$(DEEPCOPY_GEN)))
$(shell rm -f $(META_DIR)/$(DEEPCOPY_GEN).todo)

# This rule aggregates the set of files to generate and then generates them all
# in a single run of the tool.
.PHONY: gen_deepcopy
gen_deepcopy: $(DEEPCOPY_GEN) $(META_DIR)/$(DEEPCOPY_GEN).todo
	if [[ -s $(META_DIR)/$(DEEPCOPY_GEN).todo ]]; then                 \
	    pkgs=$$(cat $(META_DIR)/$(DEEPCOPY_GEN).todo | paste -sd, -);  \
	    if [[ "$(DBG_CODEGEN)" == 1 ]]; then                           \
	        echo "DBG: running $(DEEPCOPY_GEN) for $$pkgs";            \
	    fi;                                                            \
	    ./hack/run-in-gopath.sh $(DEEPCOPY_GEN)                        \
	        --v $(KUBE_VERBOSE)                                        \
	        --logtostderr                                              \
	        -i "$$pkgs"                                                \
	        --bounding-dirs $(PRJ_SRC_PATH),"k8s.io/api"               \
	        -O $(DEEPCOPY_BASENAME)                                    \
	        "$$@";                                                     \
	fi                                                                 \

# For each dir in DEEPCOPY_DIRS, this establishes a dependency between the
# output file and the input files that should trigger a rebuild.
#
# Note that this is a deps-only statement, not a full rule (see below).  This
# has to be done in a distinct step because wildcards don't work in static
# pattern rules.
#
# The '$(eval)' is needed because this has a different RHS for each LHS, and
# would otherwise produce results that make can't parse.
$(foreach dir, $(DEEPCOPY_DIRS), $(eval                     \
    $(dir)/$(DEEPCOPY_FILENAME): $($(PRJ_SRC_PATH)/$(dir))  \
))

# How to regenerate deep-copy code.  This is a little slow to run, so we batch
# it up and trigger the batch from the 'generated_files' target.
$(META_DIR)/$(DEEPCOPY_GEN).todo: $(DEEPCOPY_FILES)

$(DEEPCOPY_FILES): $(DEEPCOPY_GEN)
	if [[ "$(DBG_CODEGEN)" == 1 ]]; then        \
	    echo "DBG: deepcopy needed $(@D): $?";  \
	    ls -lf --full-time $@ $? || true;       \
	fi
	echo $(PRJ_SRC_PATH)/$(@D) >> $(META_DIR)/$(DEEPCOPY_GEN).todo

# How to build the generator tool.  The deps for this are defined in
# the $(GO_PKGDEPS_FILE), above.
#
# A word on the need to touch: This rule might trigger if, for example, a
# non-Go file was added or deleted from a directory on which this depends.
# This target needs to be reconsidered, but Go realizes it doesn't actually
# have to be rebuilt.  In that case, make will forever see the dependency as
# newer than the binary, and try to "rebuild" it over and over.  So we touch
# it, and make is happy.
$(DEEPCOPY_GEN): $(k8s.io/kubernetes/vendor/k8s.io/code-generator/cmd/deepcopy-gen)
	KUBE_BUILD_PLATFORMS="" hack/make-rules/build.sh ./vendor/k8s.io/code-generator/cmd/deepcopy-gen
	touch $@


# Defaulter generation
#
# Any package that wants defaulter functions generated must include a
# comment-tag in column 0 of one file of the form:
#     // +k8s:defaulter-gen=<VALUE>
#
# The <VALUE> depends on context:
#     on types:
#       true:  always generate a defaulter for this type
#       false: never generate a defaulter for this type
#     on functions:
#       covers: if the function name matches SetDefault_NAME, instructs
#               the generator not to recurse
#     on packages:
#       FIELDNAME: any object with a field of this name is a candidate
#                  for having a defaulter generated

# The result file, in each pkg, of defaulter generation.
DEFAULTER_BASENAME := $(GENERATED_FILE_PREFIX)defaults
DEFAULTER_FILENAME := $(DEFAULTER_BASENAME).go

# The tool used to generate defaulters.
DEFAULTER_GEN := $(BIN_DIR)/defaulter-gen

# All directories that request any form of defaulter generation.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all +k8s:defaulter-gen tags)
endif
DEFAULTER_DIRS := $(shell                                            \
    grep --color=never -l '+k8s:defaulter-gen=' $(ALL_K8S_TAG_FILES) \
        | xargs -n1 dirname                                          \
        | LC_ALL=C sort -u                                           \
)

DEFAULTER_FILES := $(addsuffix /$(DEFAULTER_FILENAME), $(DEFAULTER_DIRS))

# Reset the list of packages that need generation.
$(shell mkdir -p $$(dirname $(META_DIR)/$(DEFAULTER_GEN)))
$(shell rm -f $(META_DIR)/$(DEFAULTER_GEN).todo)

# This rule aggregates the set of files to generate and then generates them all
# in a single run of the tool.
.PHONY: gen_defaulter
gen_defaulter: $(DEFAULTER_GEN) $(META_DIR)/$(DEFAULTER_GEN).todo
	if [[ -s $(META_DIR)/$(DEFAULTER_GEN).todo ]]; then                 \
	    pkgs=$$(cat $(META_DIR)/$(DEFAULTER_GEN).todo | paste -sd, -);  \
	    if [[ "$(DBG_CODEGEN)" == 1 ]]; then                            \
	        echo "DBG: running $(DEFAULTER_GEN) for $$pkgs";            \
	    fi;                                                             \
	    ./hack/run-in-gopath.sh $(DEFAULTER_GEN)                        \
	        --v $(KUBE_VERBOSE)                                         \
	        --logtostderr                                               \
	        -i "$$pkgs"                                                 \
	        --extra-peer-dirs $$(echo $(addprefix $(PRJ_SRC_PATH)/, $(DEFAULTER_DIRS)) | sed 's/ /,/g') \
	        -O $(DEFAULTER_BASENAME)                                    \
	        "$$@";                                                      \
	fi

# For each dir in DEFAULTER_DIRS, this establishes a dependency between the
# output file and the input files that should trigger a rebuild.
#
# Note that this is a deps-only statement, not a full rule (see below for that).
#
# The '$(eval)' is needed because this has a different RHS for each LHS, and
# would otherwise produce results that make can't parse.
$(foreach dir, $(DEFAULTER_DIRS), $(eval                     \
    $(dir)/$(DEFAULTER_FILENAME): $($(PRJ_SRC_PATH)/$(dir))  \
))

# How to regenerate defaulter code.  This is a little slow to run, so we batch
# it up and trigger the batch from the 'generated_files' target.
$(META_DIR)/$(DEFAULTER_GEN).todo: $(DEFAULTER_FILES)

$(DEFAULTER_FILES): $(DEFAULTER_GEN)
	if [[ "$(DBG_CODEGEN)" == 1 ]]; then         \
	    echo "DBG: defaulter needed $(@D): $?";  \
	    ls -lf --full-time $@ $? || true;        \
	fi
	echo $(PRJ_SRC_PATH)/$(@D) >> $(META_DIR)/$(DEFAULTER_GEN).todo

# How to build the generator tool.  The deps for this are defined in
# the $(GO_PKGDEPS_FILE), above.
#
# A word on the need to touch: This rule might trigger if, for example, a
# non-Go file was added or deleted from a directory on which this depends.
# This target needs to be reconsidered, but Go realizes it doesn't actually
# have to be rebuilt.  In that case, make will forever see the dependency as
# newer than the binary, and try to "rebuild" it over and over.  So we touch
# it, and make is happy.
$(DEFAULTER_GEN): $(k8s.io/kubernetes/vendor/k8s.io/code-generator/cmd/defaulter-gen)
	KUBE_BUILD_PLATFORMS="" hack/make-rules/build.sh ./vendor/k8s.io/code-generator/cmd/defaulter-gen
	touch $@


# Conversion generation
#
# Any package that wants conversion functions generated must include one or
# more comment-tags in any .go file, in column 0, of the form:
#     // +k8s:conversion-gen=<CONVERSION_TARGET_DIR>
#
# The CONVERSION_TARGET_DIR is a project-local path to another directory which
# should be considered when evaluating peer types for conversions.  Types which
# are found in the source package (where conversions are being generated)
# but do not have a peer in one of the target directories will not have
# conversions generated.
#
# TODO: it might be better in the long term to make peer-types explicit in the
# IDL.

# The result file, in each pkg, of conversion generation.
CONVERSION_BASENAME := $(GENERATED_FILE_PREFIX)conversion
CONVERSION_FILENAME := $(CONVERSION_BASENAME).go

# The tool used to generate conversions.
CONVERSION_GEN := $(BIN_DIR)/conversion-gen

# The name of the metadata file listing conversion peers for each pkg.
CONVERSIONS_META := conversions.mk

# All directories that request any form of conversion generation.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all +k8s:conversion-gen tags)
endif
CONVERSION_DIRS := $(shell                                              \
    grep --color=never '^// *+k8s:conversion-gen=' $(ALL_K8S_TAG_FILES) \
        | cut -f1 -d:                                                   \
        | xargs -n1 dirname                                             \
        | LC_ALL=C sort -u                                              \
)

CONVERSION_FILES := $(addsuffix /$(CONVERSION_FILENAME), $(CONVERSION_DIRS))
CONVERSION_EXTRA_PEER_DIRS := k8s.io/kubernetes/pkg/apis/core,k8s.io/kubernetes/pkg/apis/core/v1,k8s.io/api/core/v1

# Reset the list of packages that need generation.
$(shell mkdir -p $$(dirname $(META_DIR)/$(CONVERSION_GEN)))
$(shell rm -f $(META_DIR)/$(CONVERSION_GEN).todo)

# This rule aggregates the set of files to generate and then generates them all
# in a single run of the tool.
.PHONY: gen_conversion
gen_conversion: $(CONVERSION_GEN) $(META_DIR)/$(CONVERSION_GEN).todo
	if [[ -s $(META_DIR)/$(CONVERSION_GEN).todo ]]; then                 \
	    pkgs=$$(cat $(META_DIR)/$(CONVERSION_GEN).todo | paste -sd, -);  \
	    if [[ "$(DBG_CODEGEN)" == 1 ]]; then                             \
	        echo "DBG: running $(CONVERSION_GEN) for $$pkgs";            \
	    fi;                                                              \
	    ./hack/run-in-gopath.sh $(CONVERSION_GEN)                        \
	        --extra-peer-dirs $(CONVERSION_EXTRA_PEER_DIRS)              \
	        --v $(KUBE_VERBOSE)                                          \
	        --logtostderr                                                \
	        -i "$$pkgs"                                                  \
	        -O $(CONVERSION_BASENAME)                                    \
	        "$$@";                                                       \
	fi

# For each dir in CONVERSION_DIRS, this establishes a dependency between the
# output file and the input files that should trigger a rebuild.
#
# Note that this is a deps-only statement, not a full rule (see below for that).
#
# The '$(eval)' is needed because this has a different RHS for each LHS, and
# would otherwise produce results that make can't parse.
$(foreach dir, $(CONVERSION_DIRS), $(eval                     \
    $(dir)/$(CONVERSION_FILENAME): $($(PRJ_SRC_PATH)/$(dir))  \
))

# How to regenerate conversion code.  This is a little slow to run, so we batch
# it up and trigger the batch from the 'generated_files' target.
$(META_DIR)/$(CONVERSION_GEN).todo: $(CONVERSION_FILES)

$(CONVERSION_FILES): $(CONVERSION_GEN)
	if [[ "$(DBG_CODEGEN)" == 1 ]]; then          \
	    echo "DBG: conversion needed $(@D): $?";  \
	    ls -lf --full-time $@ $? || true;         \
	fi
	echo $(PRJ_SRC_PATH)/$(@D) >> $(META_DIR)/$(CONVERSION_GEN).todo

# How to build the generator tool.  The deps for this are defined in
# the $(GO_PKGDEPS_FILE), above.
#
# A word on the need to touch: This rule might trigger if, for example, a
# non-Go file was added or deleted from a directory on which this depends.
# This target needs to be reconsidered, but Go realizes it doesn't actually
# have to be rebuilt.  In that case, make will forever see the dependency as
# newer than the binary, and try to rebuild it over and over.  So we touch it,
# and make is happy.
$(CONVERSION_GEN): $(k8s.io/kubernetes/vendor/k8s.io/code-generator/cmd/conversion-gen)
	KUBE_BUILD_PLATFORMS="" hack/make-rules/build.sh ./vendor/k8s.io/code-generator/cmd/conversion-gen
	touch $@


# OpenAPI generation
#
# Any package that wants open-api functions generated must include a
# comment-tag in column 0 of one file of the form:
#     // +k8s:openapi-gen=true
#
# The result file, in each pkg, of open-api generation.
OPENAPI_BASENAME := $(GENERATED_FILE_PREFIX)openapi
OPENAPI_FILENAME := $(OPENAPI_BASENAME).go
OPENAPI_OUTPUT_PKG := pkg/generated/openapi
BOILERPLATE_FILENAME := vendor/k8s.io/code-generator/hack/boilerplate.go.txt
REPORT_FILENAME := $(OUT_DIR)/violations.report
KNOWN_VIOLATION_FILENAME := api/api-rules/violation_exceptions.list
# When UPDATE_API_KNOWN_VIOLATIONS is set to be true, let the generator to write
# updated API violations to the known API violation exceptions list.
ifeq ($(UPDATE_API_KNOWN_VIOLATIONS),true)
    REPORT_FILENAME:=$(KNOWN_VIOLATION_FILENAME)
    # When UPDATE_API_KNOWN_VIOLATIONS is set to be true, touch the exceptions
    # list so that the OPENAPI_OUTFILE target re-run instead of being cached.
    $(shell touch $(KNOWN_VIOLATION_FILENAME))
endif
API_RULE_CHECK_FAILURE_MESSAGE := "ERROR: \n\t API rule check failed. Reported violations differ from known violations. Please read api/api-rules/README.md to resolve the failure. \n"

# The tool used to generate open apis.
OPENAPI_GEN := $(BIN_DIR)/openapi-gen

# Find all the directories that request open-api generation.
ifeq ($(DBG_MAKEFILE),1)
    $(warning ***** finding all +k8s:openapi-gen tags)
endif
OPENAPI_DIRS := $(shell                                             \
    grep --color=never -l '+k8s:openapi-gen=' $(ALL_K8S_TAG_FILES)  \
        | xargs -n1 dirname                                         \
        | LC_ALL=C sort -u                                          \
)

OPENAPI_OUTFILE := $(OPENAPI_OUTPUT_PKG)/$(OPENAPI_FILENAME)

# This rule is the user-friendly entrypoint for openapi generation.
.PHONY: gen_openapi
gen_openapi: $(OPENAPI_OUTFILE) $(OPENAPI_GEN)

# For each dir in OPENAPI_DIRS, this establishes a dependency between the
# output file and the input files that should trigger a rebuild.
#
# Note that this is a deps-only statement, not a full rule (see below for that).
#
# The '$(eval)' is needed because this has a different RHS for each LHS, and
# would otherwise produce results that make can't parse.
$(foreach dir, $(OPENAPI_DIRS), $(eval             \
    $(OPENAPI_OUTFILE): $($(PRJ_SRC_PATH)/$(dir))  \
))

# How to regenerate open-api code.  This emits a single file for all results.
# The Make rule fails if generated API rule violation report differs from the checked-in
# violation file, and prints error message to request developer to fix either the API
# source code, or the known API rule violation file.
$(OPENAPI_OUTFILE): $(OPENAPI_GEN) $(KNOWN_VIOLATION_FILENAME)
	./hack/run-in-gopath.sh $(OPENAPI_GEN)                                          \
	    --v $(KUBE_VERBOSE)                                                         \
	    --logtostderr                                                               \
	    -i $$(echo $(addprefix $(PRJ_SRC_PATH)/, $(OPENAPI_DIRS)) | sed 's/ /,/g')  \
	    -p $(PRJ_SRC_PATH)/$(OPENAPI_OUTPUT_PKG)                                    \
	    -O $(OPENAPI_BASENAME)                                                      \
	    -h $(BOILERPLATE_FILENAME)                                                  \
	    -r $(REPORT_FILENAME)                                                       \
	    "$$@";                                                                      \
	diff $(REPORT_FILENAME) $(KNOWN_VIOLATION_FILENAME) ||                          \
	(echo -e $(API_RULE_CHECK_FAILURE_MESSAGE); exit 1)


# How to build the generator tool.  The deps for this are defined in
# the $(GO_PKGDEPS_FILE), above.
#
# A word on the need to touch: This rule might trigger if, for example, a
# non-Go file was added or deleted from a directory on which this depends.
# This target needs to be reconsidered, but Go realizes it doesn't actually
# have to be rebuilt.  In that case, make will forever see the dependency as
# newer than the binary, and try to "rebuild" it over and over.  So we touch
# it, and make is happy.
$(OPENAPI_GEN): $(k8s.io/kubernetes/vendor/k8s.io/kube-openapi/cmd/openapi-gen)
	KUBE_BUILD_PLATFORMS="" hack/make-rules/build.sh ./vendor/k8s.io/kube-openapi/cmd/openapi-gen
	touch $@


# bindata generation
#

# The tool used to generate bindata files.
BINDATA_GEN := $(BIN_DIR)/go-bindata

# A wrapper script that generates all bindata files.  It is fast enough that we
# don't care.
BINDATA_SCRIPT := hack/generate-bindata.sh

# This rule is the user-friendly entrypoint for bindata generation.
.PHONY: gen_bindata
gen_bindata: $(BINDATA_GEN) FORCE
	./hack/run-in-gopath.sh $(BINDATA_SCRIPT)

# How to build the generator tool.  The deps for this are defined in
# the $(BINDATA_GEN).mk, above.
#
# A word on the need to touch: This rule might trigger if, for example, a
# non-Go file was added or deleted from a directory on which this depends.
# This target needs to be reconsidered, but Go realizes it doesn't actually
# have to be rebuilt.  In that case, make will forever see the dependency as
# newer than the binary, and try to rebuild it over and over.  So we touch it,
# and make is happy.
$(BINDATA_GEN): $(k8s.io/kubernetes/vendor/github.com/jteeuwen/go-bindata/go-bindata)
	KUBE_BUILD_PLATFORMS="" hack/make-rules/build.sh ./vendor/github.com/jteeuwen/go-bindata/go-bindata
	touch $@
