---
layout: post
title: centos下使用nginx搭建https服务器 
pid: 128
tags: [centos, nginx, https]
---
centos下安装nginx （注：如果nginx成功启动后还是不能访问查看一下防火墙策略）


    # 安装编译环境
    [wwwroot@localhost conf]$ sudo yum -y install gcc gcc-c++ autoconf automake 

    # 安装依赖包 
    [wwwroot@localhost conf]$ sudo yum -y install zlib zlib-devel openssl openssl--devel pcre pcre-devel 


    # 下载nginx源码
    http://nginx.org/en/download.html


    # 解压nginx
    [wwwroot@localhost conf]$ sudo tar zxvf nginx-版本号.tar.gz 


    # cd到目录
    cd nginx-版本号 


    # 生成make文件
    [wwwroot@localhost conf]$ sudo ./configure --with-http_ssl_module


    # 编译
    [wwwroot@localhost conf]$ sudo make


    # 安装 
    [wwwroot@localhost conf]$ sudo make install


    # 配置conf

    server {

     listen 443;
     ssl on;
     ssl_certificate /etc/nginx/conf/server.crt;
     ssl_certificate_key /etc/nginx/conf/server_nopwd.key;
    }


    # cd到目录
    [wwwroot@localhost conf]$ cd /etc/nginx/conf/


    创建服务器私钥
    [wwwroot@localhost conf]$ sudo openssl genrsa -des3 -out server.key 1024


    签名请求的证书
    [wwwroot@localhost conf]$ sudo openssl req -new -key server.key -out server.csr

注意此步骤过程中需要填写一系列的东西（公司名称、所在地等按照实际情况填）

尤其注意 your server' hostname的填写，如果没有域名就直接填ip，如果有域名就填域名（都不需要端口号）

例如：

    直接填ip：  192.168.10.64

    域名： xph.baoguoding.com

    模糊域名：  * .baoguoding.com


制作解密后的私钥

    [wwwroot@localhost conf]$ sudo openssl rsa -in server.key -out server_nopwd.key
    [wwwroot@localhost conf]$ sudo openssl x509 -req -days 3650 -in server.csr -signkey server_nopwd.key -out server.crt


启动nginx

    [wwwroot@localhost conf]$ sudo nginx -s reload

进入nginx主页查看

    https://192.168.10.64:443

# 参考资料

[centos下使用nginx搭建https服务器](http://blog.csdn.net/u014190646/article/details/50058859)
