---
layout: post
title: nginx代理https服务器，连接tomcat实战
pid: 129
tags: [nginx, tomcat, https]
---
用户通过https访问nginx,nginx和tomcat之间使用http交互。

User ---(https)--> Nginx ---(http)---> Tomcat ----> SpringMVC

从User 到Nginx的配置，参照[centos下使用nginx搭建https服务器](http://www.baoguoding.com/2016/12/128-centos-nginx-https.html).

从Nginx到http过程如下:

# 前提
	我们不希望为了增加https，而需要更改我们的应用程序。
	SSL的默认端口是443，我们不打算更改我们的默认端口。
	假设我们之前没有使用https访问的地址是:192.168.10.188:8080
	我们希望给客户良好的体验。

# 方法一

	server {
	    listen 8080;
	    server_name _;
	    rewrite ^ https://$host$request_uri? permanent;
	}

	server {
		listen       443;
		server_name  localhost;

		ssl on;
		ssl_certificate /etc/nginx/conf/server.crt;
		ssl_certificate_key /etc/nginx/conf/server_nopwd.key;

		location / {
			index  index.html index.htm;
			proxy_redirect          off;
			proxy_set_header        Host            $http_host;
			proxy_set_header        X-Real-IP       $remote_addr;
			proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
			proxy_set_header	    X-Forwarded-Proto  https;
			client_max_body_size    10m;
			client_body_buffer_size 128k;
			proxy_buffers           32 4k;
			proxy_connect_timeout   3;
			proxy_send_timeout      30;
			proxy_read_timeout      30;
			proxy_pass http://site;
		}
	}


# 方法二

	server {
		listen       8080;
		listen       443 ssl; # ssl on要注解掉
		server_name  localhost;

		if ($scheme != "https") {
			rewrite ^ https://$host$request_uri? permanent;
		}


		#ssl on; 
		ssl_certificate /etc/nginx/conf/server.crt;
		ssl_certificate_key /etc/nginx/conf/server_nopwd.key;

		location / {
			index  index.html index.htm;
			proxy_redirect          off;
			proxy_set_header        Host            $http_host;
			proxy_set_header        X-Real-IP       $remote_addr;
			proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
			proxy_set_header	    X-Forwarded-Proto  https;
			client_max_body_size    10m;
			client_body_buffer_size 128k;
			proxy_buffers           32 4k;
			proxy_connect_timeout   3;
			proxy_send_timeout      30;
			proxy_read_timeout      30;
			proxy_pass http://site;
		}
	}




# 参考资料

1. [SSL证书与Https应用部署小结](http://han.guokai.blog.163.com/blog/static/136718271201211631456811/)
2. [nginx使用ssl模块配置HTTPS支持](http://www.cnblogs.com/yanghuahui/archive/2012/06/25/2561568.html)
3. [Nginx搭建https服务器](http://www.cnblogs.com/grimm/p/5938511.html)
4. [centos下使用nginx搭建https服务器](http://blog.csdn.net/u014190646/article/details/50058859)
5. [nginx 代理https后，应用redirect https变成http](https://my.oschina.net/greki/blog/168089)
6. [解决Nginx+Tomcat下客户端https请求跳转成http的问题](http://blog.csdn.net/lindev/article/details/23952395)
7. [nginx强制使用https访问(http跳转到https)](http://blog.csdn.net/wzy_1988/article/details/8549290)
8. [nginx配置详解](http://blog.csdn.net/xmtblog/article/details/42295181)
