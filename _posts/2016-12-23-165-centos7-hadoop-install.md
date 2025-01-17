---
layout: post
title: 在Centos7中安装Hadoop实战
pid: 165
tags: [centos]
---
# 更新limits.conf 
    
    [root@master ~]# vim /etc/security/limits.conf 

    hdfs            -       nofile          32768
    hbase           -       nofile          32768

    hdfs            soft    nproc           32000
    hdfs            hard    nproc           32000

    hbase           soft    nproc           32000
    hbase           hard    nproc           32000

[参考](https://github.com/mcsrainbow/salt-states-hadoop/blob/master/salt/hadoop/files/limits.conf)

# 更新hostname

    [root@master ~]# hostnamectl set-hostname master
    [root@master ~]# hostname
    [root@master ~]# vim /etc/hosts
    127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
    ::1         localhost localhost.localdomain localhost6 localhost6.localdomain6

    192.168.10.68 master.hadoop.lan


# 创建hadoop用户

    [root@localhost ~]# useradd -m hadoop -s /bin/bash
    [root@localhost ~]# passwd hadoop
    [root@localhost ~]# visudo

    ## Allow root to run any commands anywhere
    root    ALL=(ALL)       ALL
    hadoop  ALL=(ALL)       ALL


# 安装配置Jdk和JAVA_HOME

参考： [Centos7安装jdk实战](http://www.baoguoding.com/2016/12/164-centos7-jdk.html)

# 安装配置Hadoop

下载[Hadoop 2.7.3 binary](http://www.apache.org/dyn/closer.cgi/hadoop/common/hadoop-2.7.3/hadoop-2.7.3.tar.gz)。

    [hadoop@localhost ~]$ cd /usr/local/
    [hadoop@localhost local]$ sudo tar -zxvf hadoop-2.7.3.tar.gz -C /usr/local/
    [hadoop@localhost local]$ sudo mv ./hadoop-2.7.3 ./hadoop
    [hadoop@localhost local]$ sudo chown -R hadoop ./hadoop
    [hadoop@localhost local]$ cd hadoop/
    [hadoop@localhost hadoop]$ ./bin/hadoop version
    [hadoop@localhost hadoop]$ vim ~/.bashrc

    # User specific aliases and functions
    export HADOOP_HOME=/usr/local/hadoop
    export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native

    export JAVA_HOME=/usr/java/jdk1.8.0_112
    export CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
    export PATH=$PATH:$JAVA_HOME/bin
    
    export PATH=$PATH:/usr/local/hadoop/sbin:/usr/local/hadoop/bin

    [hadoop@localhost hadoop]$ source ~/.bashrc

# Hadoop 附带了丰富的例子

    [hadoop@localhost hadoop]$ ./bin/hadoop jar ./share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.3.jar

# grep 例子

我们将 input 文件夹中的所有文件作为输入，筛选当中符合正则表达式 dfs[a-z.]+ 的单词并统计出现的次数，最后输出结果到 output 文件夹中。

    [hadoop@localhost hadoop]$ ./bin/hadoop jar ./share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.3.jar grep ./input ./output 'dfs[a-z.]+'
    [hadoop@localhost hadoop]$ cat ./output/*
    [hadoop@localhost hadoop]$ rm -r ./output


# Hadoop伪分布式配置

## Update core-site.xml

    [hadoop@localhost hadoop]$ cp ./etc/hadoop/core-site.xml ./etc/hadoop/core-site.xml.bak
    [hadoop@localhost hadoop]$ vim ./etc/hadoop/core-site.xml

[BEFORE]

    <?xml version="1.0" encoding="UTF-8"?>
    <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>
    <configuration>
    </configuration>


[AFTER]

    <?xml version="1.0" encoding="UTF-8"?>
    <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>


    <configuration>
        <property>
            <name>hadoop.tmp.dir</name>
            <value>file:/usr/local/hadoop/tmp</value>
            <description>Abase for other temporary directories.</description>
        </property>
        <property>
            <name>fs.defaultFS</name>
            <value>hdfs://master.hadoop.lan:9000</value>
        </property>
    </configuration>

## Update hdfs-site.xml

    [hadoop@localhost hadoop]$ cp ./etc/hadoop/hdfs-site.xml ./etc/hadoop/hdfs-site.xml.bak
    [hadoop@localhost hadoop]$ vim ./etc/hadoop/hdfs-site.xml

[BEFORE]

    <?xml version="1.0" encoding="UTF-8"?>
    <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

    <configuration>

    </configuration>

[AFTER]

    <?xml version="1.0" encoding="UTF-8"?>
    <?xml-stylesheet type="text/xsl" href="configuration.xsl"?>

    <configuration>
        <property>
            <name>dfs.replication</name>
            <value>1</value>
        </property>
        <property>
            <name>dfs.namenode.name.dir</name>
            <value>file:/usr/local/hadoop/tmp/dfs/name</value>
        </property>
        <property>
            <name>dfs.datanode.data.dir</name>
            <value>file:/usr/local/hadoop/tmp/dfs/data</value>
        </property>
    </configuration>


## 执行 NameNode 的格式化

    [hadoop@localhost hadoop]$ ./bin/hdfs namenode -format

## 开启 NameNode 和 DataNode 守护进程

    [hadoop@localhost hadoop]$ ./sbin/start-dfs.sh


## 查看是否启动成功

    [hadoop@localhost hadoop]$ jps


## 配置防火墙

    [hadoop@localhost ~]$ sudo vim /etc/sysconfig/iptables
    -A INPUT -p tcp -m state --state NEW -m tcp --dport 9000 -j ACCEPT
    -A INPUT -p tcp -m state --state NEW -m tcp --dport 50070 -j ACCEPT
    -A INPUT -p tcp -m state --state NEW -m tcp --dport 50010 -j ACCEPT
    [hadoop@localhost ~]$ service iptables restart

## 通过浏览器访问
http://localhost:50070


# 运行Hadoop伪分布式实例

## 运行程序
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -mkdir -p /user/hadoop
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -mkdir input
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -put ./etc/hadoop/*.xml input
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -ls input
    [hadoop@localhost hadoop]$ ./bin/hadoop jar ./share/hadoop/mapreduce/hadoop-mapreduce-examples-*.jar grep input output 'dfs[a-z.]+'
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -cat output/*

## 取结果到本地
    [hadoop@localhost hadoop]$ rm -r ./output
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -get output ./output
    [hadoop@localhost hadoop]$ cat ./output/*

    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -ls
    [hadoop@localhost hadoop]$ ./bin/hdfs dfs -rm -r output



# 常用命令
    [hadoop@localhost hadoop]$ ./sbin/stop-dfs.sh
    [hadoop@localhost hadoop]$ rm -r ./tmp
    [hadoop@localhost hadoop]$ ./bin/hdfs namenode -format
    [hadoop@localhost hadoop]$ ./sbin/start-dfs.sh 

# 最终，总结下来解决办法大概有三种：

    1、在系统的环境变量或java JVM变量里面添加HADOOP_USER_NAME，这个值具体等于多少看自己的情况，以后会运行HADOOP上的Linux的用户名。（修改完重启eclipse，不然可能不生效）

    2、将当前系统的帐号修改为hadoop

    3、使用HDFS的命令行接口修改相应目录的权限，hadoop fs -chmod 777 /user,后面的/user是要上传文件的路径，不同的情况可能不一样，比如要上传的文件路径为hdfs://namenode/user/xxx.doc，则这样的修改可以，如果要上传的文件路径为hdfs://namenode/java/xxx.doc，则要修改的为hadoop fs -chmod 777 /java或者hadoop fs -chmod 777 /，java的那个需要先在HDFS里面建立Java目录，后面的这个是为根目录调整权限。

    我喜欢第一个方法。

# 其他

    https://github.com/srccodes/hadoop-common-2.2.0-bin

    http://www.huqiwen.com/2013/07/18/hdfs-permission-denied/


    Exception in thread "main" org.apache.hadoop.security.AccessControlException: Permission denied: user=baoguo, access=WRITE, inode="/d100":hadoop:supergroup:drwxr-xr-x

    http://blog.csdn.net/xw13106209/article/details/6866072

    Name node is in safe mode
    bin/hadoop dfsadmin -safemode leave 

    用户可以通过dfsadmin -safemode value 来操作安全模式，参数value的说明如下：
    enter - 进入安全模式
    leave - 强制NameNode离开安全模式
    get - 返回安全模式是否开启的信息
    wait - 等待，一直到安全模式结束。


# 参考资料

1. [HDFS简单入门](http://www.cnblogs.com/archimedes/p/hadoop-simple.html)
2. [hadoop集群搭建](http://blog.chinaunix.net/uid-23916356-id-3254578.html)
3. [Hadoop 集群搭建](http://www.tuicool.com/articles/uAnyEfj)
4. [安装并运行hadoop](http://www.cnblogs.com/archimedes/p/run-hadoop.html)
5. [Ubuntu 14.04下安装JDK8](http://www.cnblogs.com/archimedes/p/ubuntu-jdk8.html)
6. [HDFS主要特性和体系结构](http://www.cnblogs.com/wuyudong/p/4404242.html)
7. [Hadoop安装教程_单机/伪分布式配置_Hadoop2.6.0/Ubuntu14.04](http://dblab.xmu.edu.cn/blog/install-hadoop/)
8. [Hadoop集群（第5期）_Hadoop安装配置](http://www.cnblogs.com/xia520pi/archive/2012/05/16/2503949.html)
9. [Hadoop之——HDFS操作实例](http://blog.csdn.net/l1028386804/article/details/45921443)
10. [hadoop集群默认配置和常用配置](http://www.cnblogs.com/ggjucheng/archive/2012/04/17/2454590.html)
11. [hadoop http address绑定内网地址](http://blog.csdn.net/cheersu/article/details/8191743)
12. [Hadoop上传文件报错解决方法](http://www.fuhenet.com/news/9005.html)

