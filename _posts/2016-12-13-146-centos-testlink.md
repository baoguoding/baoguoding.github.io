---
layout: post
title: Centos中安装Testlink
pid: 145
tags: [centos, 软件开发]
---

因为Testlink用到了PHP和MySql,但是在配置wecenter的时候，我已经安装了这2个，所以，这里我就不需要重复安装，具体步骤自己找，本文只是描述在CentOS 7上面安装testlink相关操作步骤。

自己动手，方能丰衣足食。

记住这个东西要先安装一下版本[testlink_1.7.5.tar.gz]

# TestLink 下载地址

[TestLink testlink-1.9.15.tar.gz](https://sourceforge.net/projects/testlink)


# Update PHP Version

## 安装PHP和php-fpm组件：
	[root@localhost ~]# php -v
	[root@localhost ~]# yum list installed | grep php
	[root@localhost ~]# yum remove xxxxx
	[root@localhost ~]# yum -y update
	[root@localhost ~]# yum -y install epel-release
	[root@localhost ~]# wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
	[root@localhost ~]# wget https://centos7.iuscommunity.org/ius-release.rpm
	[root@localhost ~]# rpm -Uvh ius-release*.rpm
	[root@localhost ~]# yum -y update
	[root@localhost ~]# yum -y install php56u php56u-opcache php56u-xml php56u-mcrypt php56u-gd php56u-devel php56u-mysql php56u-intl php56u-mbstring php56u-bcmath
	[root@localhost ~]# yum list installed | grep php
	[root@localhost ~]# yum install php56u-fpm
	[root@localhost ~]# php -v
	[root@localhost ~]# php-fpm -v
	[root@localhost ~]# vim /etc/php.ini
	cgi.fix_pathinfo=0

	[root@localhost ~]# vim /etc/php-fpm.d/www.conf
	; Note: This value is mandatory.
	;listen = 127.0.0.1:9000
	listen=/var/run/php-fpm/php-fpm.sock

	; Unix user/group of processes
	; Note: The user is mandatory. If the group is not set, the default user's group
	;       will be used.
	;user = php-fpm
	user = nginx
	;group = php-fpm
	group = nginx

	[root@localhost ~]# sudo systemctl start php-fpm
	[root@localhost ~]# sudo systemctl enable php-fpm.service




# 安装配置Testlink应用程序

	[root@localhost ~]# adduser testlink
	[root@localhost ~]# passwd testlink
	[root@localhost ~]# visudo
	##
	## Allow root to run any commands anywhere
	root    ALL=(ALL)       ALL
	wwwroot ALL=(ALL)       ALL
	testlink        ALL=(ALL)       ALL


	copy file from mylocal to /usr/local/src/

	[root@localhost ~]# su testlink
	[testlink@localhost ~]$ cd /usr/local/src/
	[testlink@localhost src]$ sudo tar zxvf testlink-1.9.15.tar.gz
	[testlink@localhost src]$ sudo mv testlink-1.9.15/* /home/testlink/
	[testlink@localhost src]$ cd ~
	[testlink@localhost ~]$ sudo chmod -R 755 /home/testlink/gui/templates_c
	[testlink@localhost ~]$ sudo chown -R nginx:nginx /home/testlink/gui/templates_c
	[testlink@localhost ~]$ sudo mkdir /var/testlink
	[testlink@localhost ~]$ sudo mkdir /var/testlink/logs
	[testlink@localhost ~]$ sudo mkdir /var/testlink/upload_area
	[testlink@localhost ~]$ sudo chmod -R 777 /var/testlink
	[testlink@localhost ~]$ sudo chown -R nginx:nginx /home/testlink
	[testlink@localhost ~]# vim /home/testlink/config.inc.php

	$tlCfg->config_check_warning_mode = 'SILENT';



# 配置Nginx
	server {

	    # 监听端口，默认就是80
	    listen 8002;


	    # 网站域名
	    server_name www.testlink.com;

	    # 网站根目录(我是改成了/home/wwwroot)
	    root /home/testlink;
	    #root /usr/share/nginx/html;
	    index index.php index.html index.htm;

	    location / {
		try_files $uri $uri/ /index.php; #开启伪静态
	    }

	    # 错误页配置
	    error_page 404 /404.html;
	    error_page 500 502 503 504 /50x.html;
	    location = /50x.html {
		root /usr/share/nginx/html;
	    }

	    # php-fpm配置，即对于php后缀的，都是用php-fpm处理
	    location ~ \.php$ {
		try_files $uri =404;
		fastcgi_pass unix:/var/run/php-fpm/php-fpm.sock;
		#fastcgi_pass 127.0.0.1:9000;
		fastcgi_index index.php;
		fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
		include fastcgi_params;
	    }

	}



# 配置邮箱

	[root@localhost ~]# vim /home/testlink/config.inc.php

	/**
	 * @var string SMTP server name or IP address ("localhost" should work in the most cases)
	 * Configure using custom_config.inc.php
	 * @uses lib/functions/email_api.php
	 */
	$g_smtp_host        = 'mail.163.com.cn';  # SMTP server MUST BE configured

	# Configure using custom_config.inc.php
	$g_tl_admin_email     = 'baoguo.ding@foxmail.com'; # for problem/error notification
	$g_from_email         = 'baoguo.ding@foxmail.com';  # email sender
	$g_return_path_email  = 'baoguo.ding@foxmail.com';

	/**
	 * Email notification priority (low by default)
	 * Urgent = 1, Not Urgent = 5, Disable = 0
	 **/
	$g_mail_priority = 5;

	/**
	 * Taken from mantis for phpmailer config
	 * select the method to mail by:
	 * PHPMAILER_METHOD_MAIL - mail()
	 * PHPMAILER_METHOD_SENDMAIL - sendmail
	 * PHPMAILER_METHOD_SMTP - SMTP
	 */
	$g_phpMailer_method = PHPMAILER_METHOD_SMTP;

	/** Configure only if SMTP server requires authentication */
	$g_smtp_username    = 'baoguo.ding@foxmail.com';  # user
	$g_smtp_password    = '*********';  # password





# 参考资料
1. [PHP 5.5 5.6, or 7.0—CentOS](http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-centos.html#instgde-prereq-php56-install-centos)
2. [HOW TO INSTALL PHP 5.6 ON CENTOS 7 WITH PHP-FPM NGINX AND MARIADB WITH VSFTPD](https://www.xshellz.com/community/tutorials/47975/How-to-install-php-5.6-on-CentOS-7-with-php-fpm-nginx-and-mariadb-with-vsftpd)
3. [TestLinkとは](http://qiita.com/shoooo/items/01682a255448c2b4ecd3)
4. [Centos下Yum安装PHP5.5,5.6,7.0](http://www.blogjava.net/nkjava/archive/2015/01/20/422289.html)
5. [TestLink学习二：Windows搭建TestLink环境](http://www.cnblogs.com/yangxia-test/p/4414840.html)
6. [TestLink学习三：发送邮件的两种配置方法](http://www.cnblogs.com/yangxia-test/p/4453042.html)

