---
layout: post
title: Gitlab Migrate
pid: 253
tags: [centos, linux, gitlab]
---

Gitlab服务器迁移

在做下面所有步骤之前，请确认新的服务器和旧的服务器版本是一致的。

    # BACKUP
    [root@localhost ~]# gitlab-rake gitlab:backup:create RAILS_ENV=production

    # DOWNLOAD from source server
    [root@localhost ~]# /var/opt/gitlab/backups/1500886271_gitlab_backup.tar

    # UPLOAD to dest server
    [root@localhost ~]# /var/opt/gitlab/backups/1500886271_gitlab_backup.tar

    # RESTORE
    [root@localhost ~]# gitlab-rake gitlab:backup:restore RAILS_ENV=production   BACKUP=1500889620

    # RESET YOUR LOCAL
    [root@localhost ~]# git remote set-url origin git@192.168.xx.xx:root/sample.git

    # TEST TO PULL
    [root@localhost ~]# get pull

    # CLOSE SOURCE Server
    [root@localhost ~]# gitlab-ctl stop



# 参考
[Gitlab服务器迁移](http://blog.smallmuou.xyz/git/2016/04/22/Gitlab%E6%9C%8D%E5%8A%A1%E5%99%A8%E8%BF%81%E7%A7%BB.html)
