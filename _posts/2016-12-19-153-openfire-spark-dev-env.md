---
layout: post
title: Openfire和Spark开发环境搭建
pid: 153
tags: [im, openfire, spark]
---
# Openfire开发环境搭建

    在这个搭建过程中，重点是需要用到几个包和一个奇怪的错误，其他没有什么难点。

    Jdk: 1.8.0_92

    1. [Downloads](http://www.igniterealtime.org/downloads/source.jsp)
    2. [openfire_src_4_0_4.zip](http://www.igniterealtime.org/downloads/download-landing.jsp?file=openfire/openfire_src_4_0_4.zip)
    3. [openfire_src_4_0_4.tar.gz](http://www.igniterealtime.org/downloads/download-landing.jsp?file=openfire/openfire_src_4_0_4.tar.gz)


    ## unzip openfire_src_4_0_4.zip to your eclipse workspace
    注意：不要修改openfire_src的名字

    ## open eclipse,new project with name[openfire_src], and finish
    注意：这个地方openfire_src文件是绝对路径。

    ## add below 4 files to "\openfire_src\build\lib" and "add to build path".
    1. coherence.jar
    2. coherence-work.jar
    3. tangosol.jar
    4. ant-1.8.1.jar

    链接：[4 files](http://pan.baidu.com/s/1dFwt9Wt) 密码：526v


    "add to build path": selected jars, right click, choose Build Path >> Add to Build Path.

    ## Setup Ant
    1. Window --> Show View --> Ant
    2. Add Buildfiles >> choose file \openfire_src\build\build.xml


    ## Copy tools.jar

    from \jdk1.8.0_92\lib to \jre1.8.0_92\lib

    ## run ant

    ## add jars with beow path to "Add to Build Path"

    \openfire_src\target\openfire\lib\*.jar


    ## remove the rest complied error project from your work space.



    ## Setup starter

    1. Run >> Run Configurations >> Java Application >> New >> Name: ServerStarter
    2. Main Tab
      Project: openfire_src
      Main class: org.jivesoftware.openfire.starter.ServerStarter
      choose "Include system libraries when searching for a main class".
    3. Arguments Tab
      VM arguments: -DopenfireHome="${workspace_loc:openfire_src}/target/openfire"
    4. Class Tab
      Choose "User Entries" >> Advanced >> Add Folders
      a. src/i18n
      b. src/resources
      c. 
    5. Common Tab
      Selected checkbox "Debug" and "Run".

    6. Click apply, and run.


    ## Open http://127.0.0.1:9090 

    username:admin
    password:admin



# Spark开发环境搭建

    ## Setup starter

    1. Run >> Run Configurations >> Java Application >> New >> Name: SparkStarter
    2. Main Tab
      Main class: org.jivesoftware.launcher.Startup
      Stop in main
    4. Class Tab
      Choose "User Entries" >> Advanced >> Add Folders
      a. /src/resources



# 参考资料

1. [Openfire和Spark本地开发环境搭建记要](http://coffeelover.iteye.com/blog/1533174)
2. [openfire插件开发环境搭建](http://beautyofprogram.iteye.com/blog/772281)
3. [Openfire SVN + Eclipse 3.3 + Subversive Installation Guide](https://community.igniterealtime.org/docs/DOC-1020)
4. [Openfire Plugins Setup Guide For Eclipse](https://community.igniterealtime.org/docs/DOC-1200)
5. [openfire 搭建](http://wobuxiaole.iteye.com/blog/622294)
6. [技术笔记：XMPP之openfire+spark+smack](http://www.cnblogs.com/5207/p/5377510.html)
7. [Openfire开发配置,Openfire源代码配置,OpenFire二次开发配置](http://www.cnblogs.com/lixiaolun/archive/2013/12/07/3462780.html)
8. [Openfire+Spark源码开发环境搭建](https://my.oschina.net/fallenpanda/blog/192496)
9. [Openfire和Spark本地开发环境搭建记要](http://coffeelover.iteye.com/blog/1533174)
10. [利用Openfire+spark+Smack实现XMPP即时通信](http://www.tuicool.com/articles/fEFRBra)
