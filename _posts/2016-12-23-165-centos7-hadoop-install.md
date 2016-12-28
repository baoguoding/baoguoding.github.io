---
layout: post
title: 在Centos7中安装Hadoop实战
pid: 165
tags: [centos, hadoop]
---
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
            <value>hdfs://localhost:9000</value> 如果你希望所有IP都可以访问可以修改成0.0.0.0
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
    -A INPUT -p tcp -m state --state NEW -m tcp --dport 50070 -j ACCEPT
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




1. [HDFS简单入门](http://www.cnblogs.com/archimedes/p/hadoop-simple.html)
2. [hadoop集群搭建](http://blog.chinaunix.net/uid-23916356-id-3254578.html)
3. [Hadoop 集群搭建](http://www.tuicool.com/articles/uAnyEfj)
4. [安装并运行hadoop](http://www.cnblogs.com/archimedes/p/run-hadoop.html)
5. [Ubuntu 14.04下安装JDK8](http://www.cnblogs.com/archimedes/p/ubuntu-jdk8.html)
6. [HDFS主要特性和体系结构](http://www.cnblogs.com/wuyudong/p/4404242.html)
7. [Hadoop安装教程_单机/伪分布式配置_Hadoop2.6.0/Ubuntu14.04](http://dblab.xmu.edu.cn/blog/install-hadoop/)
8. [Hadoop集群（第5期）_Hadoop安装配置](http://www.cnblogs.com/xia520pi/archive/2012/05/16/2503949.html)
