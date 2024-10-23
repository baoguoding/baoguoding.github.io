---
layout: post
title: MySQL高可用之KeepAlived双主
pid: 652
tags: [linux]
---



本实例包括mysql的双主配置、keepalived主从配置，keepalived双主配置。



## 安装mysql5.7

```shell
rpm -qa | grep -i mysql
ps ajx | grep mysqld
rpm -qa | grep mysql
rpm -qa | grep mysql | xargs yum -y remove
ll /etc/yum.repos.d
cat /etc/redhat-release
wget http://repo.mysql.com/mysql57-community-release-el7.rpm
rpm -ivh mysql57-community-release-el7.rpm
yum list | grep mysql
ll /etc/yum.repos.d
rpm --import https://repo.mysql.com/RPM-GPG-KEY-mysql-2022
yum install -y mysql-community-server
which mysql
which mysqld
ll /etc/my.cnf
```

## 设置mysql root密码

```sql
systemctl restart mysqld
sudo grep 'temporary password' /var/log/mysqld.log
mysql -u root -p
ALTER USER 'root'@'localhost' IDENTIFIED BY 'passwrod';
FLUSH PRIVILEGES;
EXIT;
```

## 在node1操作 - Mysql添加配置

```shell
[root@localhost ~]# vim /etc/my.cnf
log-bin=mysql-bin
server-id=1
relay-log=relay-bin
relay-log-index=relay-bin.index
auto_increment_increment=2
auto_increment_offset=1

[root@localhost ~]# systemctl restart mysqld

[root@localhost ~]# mysql -uroot -p
mysql> grant replication slave on *.* to rep@'172.16.52.%' identified by 'password';
mysql> flush privileges;
mysql> show master status;
+------------------+----------+--------------+------------------+-------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+------------------+----------+--------------+------------------+-------------------+
| mysql-bin.000001 |      608 |              |                  |                   |
+------------------+----------+--------------+------------------+-------------------+
1 row in set (0.00 sec)

```



## 在node2操作 - Mysql添加配置

```shell
[root@localhost ~]# vim /etc/my.cnf
log-bin=mysql-bin
server-id=2
relay-log=relay-bin
relay-log-index=relay-bin.index
auto_increment_increment=2
auto_increment_offset=2

[root@localhost ~]# systemctl restart mysqld

[root@localhost ~]# mysql -u root
mysql> change master to master_host='172.16.52.151',master_user='rep',master_password='password',master_log_file='mysql-bin.000001',master_log_pos=608;
mysql> start slave;
mysql> show slave status\G
*************************** 1. row ***************************
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes

node1主，node2从配置完成

下面是配置
node2主，node1从的配置信息

mysql> grant replication slave on *.* to rep@'172.16.52.%' identified by 'password';
Query OK, 0 rows affected, 1 warning (0.01 sec)

mysql> flush privileges;
Query OK, 0 rows affected (0.01 sec)

mysql> show master status;
+------------------+----------+--------------+------------------+-------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+------------------+----------+--------------+------------------+-------------------+
| mysql-bin.000001 |      608 |              |                  |                   |
+------------------+----------+--------------+------------------+-------------------+
1 row in set (0.01 sec)


```



## 在node1操作

```sql
[root@localhost ~]# mysql -u root -p
mysql> change master to master_host='172.16.52.152',master_user='rep',master_password='password',master_log_file='mysql-bin.000001',master_log_pos=608;
mysql> start slave;
mysql> show slave status\G
*************************** 1. row ***************************
             Slave_IO_Running: Yes
            Slave_SQL_Running: Yes



```

## 在node1和node2进行Mysql双主测试。

```sql
node1 操作

mysql> create database test_db;
Query OK, 1 row affected (0.00 sec)

mysql> use test_db;
Database changed
mysql> create table tab1(id int);
Query OK, 0 rows affected (0.00 sec)

node2 操作

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
| test_db            |
+--------------------+
5 rows in set (0.00 sec)

mysql> use test_db;
mysql> show tables;
+-------------------+
| Tables_in_test_db |
+-------------------+
| tab1              |
+-------------------+
1 row in set (0.00 sec)

mysql> insert into tab1 values(1);
Query OK, 1 row affected (0.00 sec)

mysql> select * from tab1;
+------+
| id   |
+------+
|    1 |
+------+
1 row in set (0.00 sec)

mysql>

node1 操作

mysql> select * from tab1;
+------+
| id   |
+------+
|    1 |
+------+
1 row in set (0.00 sec)
```



## 在node1上操作 - Keepalived主从配置

```
[root@localhost ~]# vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   router_id mysql-master01
}

vrrp_instance VI_1 {
    state BACKUP
    interface ens33
    virtual_router_id 51
    priority 100
    advert_int 1
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
}

virtual_server 172.16.52.188 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.151 3306 {
        weight 1
        notify_down /etc/keepalived/bin/mysql.sh
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}

[root@localhost ~]# mkdir /etc/keepalived/bin/
[root@localhost ~]# vim /etc/keepalived/bin/mysql.sh
#!/bin/bash
pkill keepalived

[root@localhost ~]# chmod +x /etc/keepalived/bin/mysql.sh
[root@localhost ~]# service keepalived stop
[root@localhost ~]# service keepalived start
[root@localhost ~]# service keepalived status
```



## 在node2上操作 - Keepalived主从配置

```shell
[root@localhost ~]# vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   router_id mysql-master02
}

vrrp_instance VI_1 {
    state BACKUP
    interface ens33
    virtual_router_id 51
    priority 50
    nopreempt
    advert_int 1
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
}

virtual_server 172.16.52.188 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.152 3306 {
        notify_down /etc/keepalived/bin/mysql.sh
        weight 1
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}

[root@localhost ~]# mkdir /etc/keepalived/bin/
[root@localhost ~]# vim /etc/keepalived/bin/mysql.sh
#!/bin/bash
pkill keepalived

[root@localhost ~]# chmod +x /etc/keepalived/bin/mysql.sh
[root@localhost ~]# service keepalived stop
[root@localhost ~]# service keepalived start
[root@localhost ~]# service keepalived status
```



## 在node1 和 node2 上测试Keepalived主从配置

```shell
node1 操作
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:d7:de:df brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.151/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1252sec preferred_lft 1252sec
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::32da:49b5:524c:fc84/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node2 操作

[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1463sec preferred_lft 1463sec
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node1 操作

[root@localhost ~]# ps -ef |grep keep
baoguo     2299   1887  0 02:38 ?        00:00:00 /usr/libexec/gsd-housekeeping
root     103392      1  0 08:22 ?        00:00:00 /usr/local/keepalived/sbin/keepalived -D
root     103394 103392  0 08:22 ?        00:00:00 /usr/local/keepalived/sbin/keepalived -D
root     103395 103392  0 08:22 ?        00:00:00 /usr/local/keepalived/sbin/keepalived -D
root     103522  92236  0 08:31 pts/0    00:00:00 grep --color=auto keep
[root@localhost ~]# service mysql stop
Redirecting to /bin/systemctl stop mysql.service
Failed to stop mysql.service: Unit mysql.service not loaded.
[root@localhost ~]# service mysqld stop
Redirecting to /bin/systemctl stop mysqld.service
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:d7:de:df brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.151/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1050sec preferred_lft 1050sec
    inet6 fe80::32da:49b5:524c:fc84/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node2 操作

[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1275sec preferred_lft 1275sec
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node1 操作

[root@localhost ~]# service mysqld start
Redirecting to /bin/systemctl start mysqld.service
[root@localhost ~]# ps -ef |grep keep
```



## Node1 - keepalived 双主配置

```shell
[root@localhost ~]# vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   router_id mysql-master01
}

vrrp_instance VI_1 {
    state MASTER
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 51
    priority 100
    advert_int 1
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
}

vrrp_instance VI_2 {
    state BACKUP
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 52
    priority 90
    advert_int 1
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 2222
    }
    virtual_ipaddress {
        172.16.52.200
    }
}


virtual_server 172.16.52.188 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.151 3306 {
        weight 1
        notify_down /etc/keepalived/bin/mysql.sh
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}

virtual_server 172.16.52.200 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.151 3306 {
        weight 1
        notify_down /etc/keepalived/bin/mysql.sh
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}




[root@localhost ~]# service keepalived restart
[root@localhost ~]# service keepalived status
```



## Node2 - keepalived 双主配置

```shell
[root@localhost ~]# vim /etc/keepalived/keepalived.conf
! Configuration File for keepalived

global_defs {
   router_id mysql-master01
}

vrrp_instance VI_1 {
    state BACKUP
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 51
    priority 90
    advert_int 1
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 1111
    }
    virtual_ipaddress {
        172.16.52.188
    }
}

vrrp_instance VI_2 {
    state MASTER
    interface ens33
    lvs_sync_daemon_inteface ens33
    virtual_router_id 52
    priority 100
    advert_int 1
    nopreempt
    authentication {
        auth_type PASS
        auth_pass 2222
    }
    virtual_ipaddress {
        172.16.52.200
    }
}


virtual_server 172.16.52.188 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.152 3306 {
        weight 1
        notify_down /etc/keepalived/bin/mysql.sh
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}

virtual_server 172.16.52.200 3306 {
    delay_loop 6
    lb_algo rr
    lb_kind DR
    persistence_timeout 50
    protocol TCP
    real_server 172.16.52.152 3306 {
        weight 1
        notify_down /etc/keepalived/bin/mysql.sh
        TCP_CHECK {
            connect_port 3306
            connect_timeout 3
            retry 3
            delay_before_retry 3
        }
    }
}

[root@localhost ~]# service keepalived restart
[root@localhost ~]# service keepalived status
```



## keepalived 双主检测

```
node1检测
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:d7:de:df brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.151/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1408sec preferred_lft 1408sec
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::32da:49b5:524c:fc84/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node2检测
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1690sec preferred_lft 1690sec
    inet 172.16.52.200/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
关闭node1
[root@localhost ~]# service mysqld stop
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:d7:de:df brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.151/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1281sec preferred_lft 1281sec
    inet6 fe80::32da:49b5:524c:fc84/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
       
查看node2
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1550sec preferred_lft 1550sec
    inet 172.16.52.200/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
重启node1
[root@localhost ~]# service mysqld start
[root@localhost ~]# service keepalived start
[root@localhost ~]# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:d7:de:df brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.151/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1170sec preferred_lft 1170sec
    inet 172.16.52.188/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::32da:49b5:524c:fc84/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
       
node2查看状态
[root@localhost ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: ens33: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    link/ether 00:0c:29:6c:98:e8 brd ff:ff:ff:ff:ff:ff
    inet 172.16.52.152/24 brd 172.16.52.255 scope global noprefixroute dynamic ens33
       valid_lft 1432sec preferred_lft 1432sec
    inet 172.16.52.200/32 scope global ens33
       valid_lft forever preferred_lft forever
    inet6 fe80::99d9:7b51:5574:23fe/64 scope link noprefixroute
       valid_lft forever preferred_lft forever


```



## 参考

[MySQL高可用之KeepAlived+双主](https://blog.csdn.net/flynetcn/article/details/137152376)

[【MySQL入门指南】Centos7下MySQL5.7安装教程（全程图解）](https://blog.csdn.net/whc18858/article/details/130003385)

[mysql5.7系列修改root默认密码](https://www.cnblogs.com/activiti/p/7810166.html)
