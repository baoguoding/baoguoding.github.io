---
layout: post
title: redmine安装及配置
pid: 136
tags: [redmine]
---
# 设置淘宝镜像

    [root@localhost ~]# bundle config mirror.https://rubygems.org https://ruby.taobao.org
    [root@localhost ~]# gem update 

# 先安装CentOS系统包与兼容包
    yum -y install patch make gcc gcc-c++ gcc-g77 flex* bison file
    yum -y install libtool libtool-libs autoconf kernel-devel
    yum -y install libjpeg libjpeg-devel libpng libpng-devel libpng10 libpng10-devel gd gd-devel
    yum -y install freetype freetype-devel libxml2 libxml2-devel zlib zlib-devel
    yum -y install glib2 glib2-devel bzip2 bzip2-devel libevent libevent-devel
    yum -y install ncurses ncurses-devel curl curl-devel e2fsprogs
    yum -y install e2fsprogs-devel krb5 krb5-devel libidn libidn-devel
    yum -y install openssl openssl-devel vim-minimal nano sendmail
    yum -y install fonts-chinese gettext gettext-devel
    yum -y install ncurses-devel
    yum -y install gmp-devel pspell-devel
    yum -y install unzip
    yum -y install automake libmcrypt* libtool-ltdl-devel*
    yum -y install readline* libxslt* pcre* net-snmp* gmp* libtidy*
    yum -y install ImageMagick* svnversion*


# 安装rvm 程序
    [root@localhost ~]# bash < <( curl -L https://get.rvm.io )
    [root@localhost ~]# source /etc/profile.d/rvm.sh
    [root@localhost ~]# rvm -v
    [root@localhost ~]# rvm install ruby
    [root@localhost ~]# gem -v
    [root@localhost ~]# gem install rails
    [root@localhost ~]# gem install rake
    [root@localhost ~]# gem install mysql2
    [root@localhost ~]# gem install rbpdf-font
    [root@localhost src]# gem install --local ./rbpdf-font-1.19.0.gem



    [root@localhost ~]# cd /opt/
    [root@localhost opt]# svn co http://svn.redmine.org/redmine/branches/2.3-stable redmine
    [root@localhost opt]# svn co http://svn.redmine.org/redmine/branches/3.3-stable redmine
    [root@localhost src]# cd redmine/
    [root@localhost redmine]# bundle install
    [root@localhost redmine]# cd config/
    [root@localhost config]# mv database.yml.example database.yml
    [root@localhost config]# mv configuration.yml.example configuration.yml
    [root@localhost config]# vim database.yml
    production:
      adapter: mysql2
      database: redmine
      host: 127.0.0.1
      username: root
      password: "******"
      encoding: utf8

    [root@localhost config]# cd ..
    [root@localhost redmine]# rake config/initializers/secret_token.rb
    [root@localhost redmine]# rake db:migrate RAILS_ENV="production"
    [root@localhost redmine]# ./bin/rails server -p3000 -b127.0.0.1 -e production
    后台运行
    [root@localhost redmine]# ./bin/rails server -p3000 -b0.0.0.0 -e production -d

    [root@localhost redmine]# ps -ef | grep rails
    http://127.0.0.1:3000/

    默认用户名和密码
    admin
    admin


# 配置邮件服务器
    [root@localhost ~]# ps auxf | grep sendmail
    [root@localhost ~]# service sendmail start
    [root@localhost ~]# yum -y install sendmail
    [root@localhost ~]# mail -s "mail from baoguo" baoguo.ding@roadshare.com < mail.txt 
    [root@localhost ~]# tail /var/log/maillog
    [root@localhost ~]# vim /opt/redmine/config/configuration.yml


    default:
      # Outgoing emails configuration
      # See the examples below and the Rails guide for more configuration options:
      # http://guides.rubyonrails.org/action_mailer_basics.html#action-mailer-configuration
      email_delivery:

      # ==== Simple SMTP server at localhost
      #
      #  email_delivery:
      #    delivery_method: :smtp
      #    smtp_settings:
      #      address: "localhost"
      #      port: 25
      #
      # ==== SMTP server at example.com using LOGIN authentication and checking HELO for foo.com
      #
      #  email_delivery:
          delivery_method: :smtp
          smtp_settings:
            address: "****"
            port: 25
            authentication: :login
            domain: '****'
            user_name: 'baoguo.ding@foxmail.com'
            password: '*****'
      #

    [root@localhost redmine]# ./bin/rails server -p3000 -b0.0.0.0 -e production -d


    http://192.168.xx.xx:3000/my/page

    1. 管理 >>>  配置 >>> 一般 >>> 主机名称 
    2. 管理 >>>  配置 >>> 邮件通知 >> 修改发件人，保存， 点击最下方的“发送测试邮件”。


＃ 参考资料

1. [centos7下使用gitlab+redmine+jenkins](http://blog.csdn.net/u012375924/article/details/47951173)
2. [CentOS 7下安装Redmine中文版图文教程](http://www.cr173.com/html/50478_1.html)
3. [CentOS安装配置redmine 走了好多弯路 总算搞定](https://my.oschina.net/smilelxb/blog/496763)
4. [Redmine安装过程疑难杂症](http://zengrong.net/post/1936.htm)
5. [redmine邮件发送功能配置详解](http://blog.chinaunix.net/uid-26000296-id-5047175.html)
