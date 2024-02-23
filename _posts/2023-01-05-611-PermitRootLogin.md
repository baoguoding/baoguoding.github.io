---
layout: post
title: Centos 禁用外网直接访问
pid: 611
tags: [linux, ssh, iptables, useradd]
---



Centos 禁用外网直接访问

创建个人账号

useradd zhangsan

passwd zhangsan

修改防火墙

vim /etc/sysconfig/iptables  ***记得把下面用到的端口添加进去***

service iptables restart


更新端口配置

vim /etc/ssh/sshd_config


Port 22

Port 9982

service sshd restart

***这个地方一定要先试用zhangsan以及新的端口登录一下，然后再做下面的改动，否则会永远都登录不进系统***

禁用root登录

PermitRootLogin yes 改成 no

service sshd restart

