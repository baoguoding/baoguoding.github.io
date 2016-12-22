---
layout: post
title: Centos7启用iptables实战
pid: 160
tags: [linux, centos, network]
---
# 关闭firewall：

    [root@localhost ~]# systemctl stop firewalld.service #停止firewall
    [root@localhost ~]# systemctl disable firewalld.service #禁止firewall开机启动
    Removed symlink /etc/systemd/system/dbus-org.fedoraproject.FirewallD1.service.
    Removed symlink /etc/systemd/system/basic.target.wants/firewalld.service.


# 安装iptables防火墙:

    [root@localhost ~]# yum install iptables-services #安装
    [root@localhost ~]# vim /etc/sysconfig/iptables #编辑防火墙配置文件
    [root@localhost ~]# systemctl restart iptables.service #最后重启防火墙使配置生效
    [root@localhost ~]# systemctl enable iptables.service #设置防火墙开机启动 

# 参考资料:

[CentOS 7.0，启用iptables防火墙](http://www.open-open.com/lib/view/open1411818940031.html)
