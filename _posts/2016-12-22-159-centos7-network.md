---
layout: post
title: Centos7中配置固定IP
pid: 159
tags: [linux, centos, network]
---
如需要重启后，自动打开网络连接，需要配置ONBOOT=yes。

    [root@localhost ~]# vim /etc/sysconfig/network-scripts/ifcfg-enp4s0

    TYPE=Ethernet
    ONBOOT=yes
    BOOTPROTO=none
    DEFROUTE=yes
    IPV4_FAILURE_FATAL=no
    IPV6INIT=no
    IPV6_AUTOCONF=yes
    IPV6_DEFROUTE=yes
    IPV6_FAILURE_FATAL=no
    NAME=enp4s0
    UUID=53d9056f-c7da-4599-a8be-f3f7bfd6f96a
    DEVICE=enp4s0
    ONBOOT=no
    DNS1=192.168.10.1
    DNS2=61.177.7.1
    IPV6_PEERDNS=yes
    IPV6_PEERROUTES=yes
    IPADDR=192.168.10.68
    PREFIX=24
    GATEWAY=192.168.10.1


    [root@localhost ~]# shutdown -r now
