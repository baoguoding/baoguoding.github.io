---
layout: post
title: keepalived
pid: 651
tags: [linux]
---



## Nginx+keepalived主备模式

```shell
systemctl stop firewalld.service
systemctl disable firewalld.service
wget https://www.keepalived.org/software/keepalived-1.3.5.tar.gz
wget http://nginx.org/download/nginx-1.18.0.tar.gz
tar -xf keepalived-1.3.5.tar.gz -C /usr/src/
tar -xf nginx-1.18.0.tar.gz -C /usr/src/
```



```shell
yum -y install gcc-c++ pcre pcre-devel zlib zlib-devel openssl openssl-devel libnl libnl-devel libnfnetlink libnfnetlink-devel
useradd -s /sbin/nologin nginx -M
cd /usr/src/nginx-1.18.0/
./configure --prefix=/usr/local/nginx --user=nginx --group=nginx --with-http_stub_status_module --with-http_ssl_module
make && make install

vim /etc/profile
export PATH=$PATH:/usr/local/nginx/sbin

source /etc/profile
nginx -c /usr/local/nginx/conf/nginx.conf
echo "this is 172.16.52.151 page" > /usr/local/nginx/html/index.html
```



```shell
cd /usr/src/keepalived-1.3.5/
sudo ./configure --prefix=/usr/local/keepalived/ --with-kernel-dir=/usr/src/kernels/3.10.0-514.el7.x86_64/
sudo make install
cp /usr/src/keepalived-1.3.5/keepalived/etc/init.d/keepalived /etc/init.d/
mkdir -p /etc/keepalived
cp /usr/local/keepalived/etc/keepalived/keepalived.conf  /etc/keepalived/
cp /usr/src/keepalived-1.3.5/keepalived/etc/sysconfig/keepalived /etc/sysconfig/

vim /etc/profile
export PATH=$PATH:/usr/local/keepalived/sbin
source /etc/profile

vim /etc/keepalived/keepalived.conf
```



```shell
! Configuration File for keepalived

global_defs {
   notification_email {
     baoguo.ding@foxmail.com
   }
   notification_email_from root@localhost
   smtp_server 127.0.0.1
   smtp_connect_timeout 30
   router_id LVS_DEVEL
}

vrrp_script chk_nginx {
   script  "/data/sh/check_nginx.sh"
   interval 2
   weight 2
}

vrrp_instance VI_1 {
    state BACKUP
    interface ens33
    virtual_router_id 51
    priority 90
    advert_int 5
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
    track_script {
        chk_nginx
    }
}
```

```shell
mkdir -p /data/sh/

vim /data/sh/check_nginx.sh
#!/bin/bash
#auto  check  nginx  process
#by  author  baoguo
killall  -0   nginx
if  [[ $? -ne 0 ]];then
service keepalived stop
fi


chmod +x /data/sh/check_nginx.sh

vim /lib/systemd/system/keepalived.service
PIDFile=/var/run/keepalived.pid

service keepalived start
service keepalived status
service keeplived stop
service keeplived restart
```



## Nginx+keepalived双主企业架构



**node1配置**

```shell
vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   notification_email {
     baoguo.ding@foxmail.com
   }
   notification_email_from root@localhost
   smtp_server 127.0.0.1
   smtp_connect_timeout 30
   router_id LVS_DEVEL
}

vrrp_script chk_nginx {
   script  "/data/sh/check_nginx.sh"
   interval 2
   weight 2
}

vrrp_instance VI_1 {
    state MASTER
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 51
    priority 100
    advert_int 5
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
    track_script {
        chk_nginx
    }
}

vrrp_instance VI_2 {
    state BACKUP
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 52
    priority 90
    advert_int 5
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 2222
    }
    virtual_ipaddress {
        172.16.52.200
    }
    track_script {
        chk_nginx
    }
}
```

**node2配置**

```shell
vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   notification_email {
     baoguo.ding@foxmail.com
   }
   notification_email_from root@localhost
   smtp_server 127.0.0.1
   smtp_connect_timeout 30
   router_id LVS_DEVEL
}

vrrp_script chk_nginx {
   script  "/data/sh/check_nginx.sh"
   interval 2
   weight 2
}

vrrp_instance VI_1 {
    state BACKUP
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 51
    priority 90
    advert_int 5
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
    track_script {
        chk_nginx
    }
}

vrrp_instance VI_2 {
    state MASTER
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 52
    priority 100
    advert_int 5
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 2222
    }
    virtual_ipaddress {
        172.16.52.200
    }
    track_script {
        chk_nginx
    }
}
```


```shell
service keepalived restart
```

```cmd
[root@localhost ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1387sec preferred_lft 1387sec
    inet 172.16.52.200/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
```



```cmd
[root@localhost ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1250sec preferred_lft 1250sec
    inet 172.16.52.200/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
```

当VIP迁移后，ens33就会多出来IP信息。



# 参考

[keepalive高可用软件配置及详解](https://blog.csdn.net/weixin_45625174/article/details/108600061)
