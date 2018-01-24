---
layout: post
title: 前后端分离式项目CI实践
pid: 268
tags: [vueJs, SpringBoot]
---

# Install & Configure JDK

> 自己找帮助

# Install & Configure Maven

> 自己找帮助

# Install & Configure Jenkins

	sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat/jenkins.repo 
	sudo rpm --import https://jenkins-ci.org/redhat/jenkins-ci.org.key
	sudo yum install jenkins
	sudo service jenkins restart
	sudo chkconfig jenkins on
	vim /etc/sysconfig/jenkins
	sudo service jenkins stop
	sudo service jenkins start
	vim /etc/sysconfig/iptables
	service iptables restart
	vim /var/lib/jenkins/secrets/initialAdminPassword

# Create & Grant folder Permission

	mkdir /usr/local/xx-main/deploy
	mkdir /usr/local/xx-main/deploy_backup
	mkdir /usr/local/xx-main/deploy_script
	cd /usr/local/xx-main
	chown -R jenkins:jenkins *
	mkdir /usr/local/xx_frontend
	cd /usr/local
	chown -R jenkins:jenkins /usr/local/xx_frontend

# Prepare Linux deploy_script

> stop.sh

	#!将应用停止
	#!stop.sh
	#!/bin/bash
	cd /usr/local/xx-main/deploy_script
	echo "Stopping SpringBoot Application"
	ls
	pid=`ps -ef | grep xx-main.jar | grep -v grep | awk '{print $2}'`
	if [ -n "$pid" ]
	then
	#!kill -9 强制终止
	   echo "kill -9 的pid:" $pid
	   kill -9 $pid
	fi


> replace.sh

	#!编译好的jar包存放地址
	source_file=/var/lib/jenkins/workspace/xx-main/xx-main/target/xx-main.jar
	#!将现有的jar备份后，将新的jar包替换
	target_file="/usr/local/xx-main/deploy/xx-main.jar"

	cd /usr/local/xx-main

	if [ -f "$target_file" ]
	then
	mv ./deploy/xx-main.jar ./deploy_backup/xx-main.jar.`date +%Y%m%d%H%M%S`
	fi
	cp $source_file ./deploy


> startup.sh

	#!/bin/bash
	echo "**********************jenkins started*************************"
	echo "授予当前用户权限"

	chmod 777 /usr/local/xx-main/deploy/hyl-main.jar
	echo "执行....."
	cd /usr/local/xx-main/deploy
	java -jar xx-main.jar
	echo "**********************jenkins end*************************"


# Global Tool Configuration

> JDK

	/usr/java/jdk1.7.0_80

> MAVEN

	/usr/share/maven

> NodeJS

	/usr/local/node


# Manage PlugIn

	1. NodeJS Plugin
	2. Maven Integration plugin


# Create Manven Project in Jenkins

## POST Steps - Run only if build succeeds

	#!/bin/bash
	cd /usr/local/xx-main/deploy_script
	echo "Execute shell Start"
	sh stop.sh
	sh replace.sh
	echo "Execute shell Finish"
	chmod 777 /usr/local/xx-main/deploy_script/startup.sh
	BUILD_ID=dontKillMe nohup /usr/local/xx-main/deploy_script/startup.sh &


# Create NodeJs Project in Jenkins

## Provide Node & npm bin/ folder to PATH -- NodeJS Installation

## Build -- Execute Shell

	#!/bin/bash
	pwd 
	source /etc/profile
	cd xx_frontend/
	npm install
	# nohup npm run dev > /dev/null 2>&1 &
	# npm run dev
	# (npm run dev &)
	npm run build


# Configure nginx

	server {
		listen       7001;
		server_name  localhost;

		#error_page  404              /404.html;
		location / {
			root /usr/local/xx_frontend/;
			index index.html index.htm;
		}

		# redirect server error pages to the static page /50x.html
		#
		error_page   500 502 503 504  /50x.html;
		location = /50x.html {
			root   /usr/share/nginx/html;
		}

	}




# Configure iptables

	-A INPUT -p tcp -m state --state NEW -m tcp --dport 8888 -j ACCEPT
	-A INPUT -p tcp -m state --state NEW -m tcp --dport 7001 -j ACCEPT
	-A INPUT -p tcp -m state --state NEW -m tcp --dport 7002 -j ACCEPT


# Try It!

	CI服务器
	http://10.18.10.22:8888
	admin - jenkins

	# 前端
	http://10.18.10.22:7001/#/

	# 后端
	http://10.18.10.22:7002/ping


# 一点遗憾

我期望将有状态的内容都放到nodeJs里面去，将无状态的内容都放到Springboot API中，但是vue.js不支持，所以，目前只能是去使用这一的折中的办法后面再看有没有好的实践方法吧！
