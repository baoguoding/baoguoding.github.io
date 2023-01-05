---
layout: post
title: Centos 禁用外网直接访问
pid: 611
tags: [linux]
---



Centos 禁用外网直接访问

创建个人账号

useradd zhangsan

passwd zhangsan


修改防火墙

vim /etc/sysconfig/iptables

service iptables restart


更新端口配置和禁用root登录

vim /etc/ssh/sshd_config


Port 22

Port 9982

PermitRootLogin yes 改成 no

service sshd restart

