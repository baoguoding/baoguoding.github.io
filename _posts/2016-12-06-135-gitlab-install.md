---
layout: post
title: GitLab安装实录
pid: 135
tags: [git, gitlab]
---
# 安装GitLab(建议迅雷吧！)

    https://about.gitlab.com/downloads/

    [root@localhost src]# cd ~
    [root@localhost ~]# cd /usr/local/src/
    [root@localhost src]# curl -LJO https://mirror.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/gitlab-ce-8.5.4-ce.0.el7.x86_64.rpm
    [root@localhost src]# rpm -i gitlab-ce-8.5.4-ce.0.el7.x86_64.rpm
    [root@localhost src]# gitlab-ctl reconfigure

# 安装发件邮箱

    [root@localhost ~]# sudo yum -y install postfix cronie
    [root@localhost ~]# sudo service postfix start
    [root@localhost ~]# sudo chkconfig postfix on
    [root@localhost ~]# sudo gitlab-ctl reconfigure

# Update gitlab.rb

    [root@localhost ~]# vim /etc/gitlab/gitlab.rb     

    # Change the external_url to the address your users will type in their browser
    external_url 'http://xxhost.com'

    #Sending application email via SMTP
    gitlab_rails['smtp_enable'] = true
    gitlab_rails['smtp_address'] = "smtp.163.com"
    gitlab_rails['smtp_port'] = 25 
    gitlab_rails['smtp_user_name'] = "xxuser@163.com"
    gitlab_rails['smtp_password'] = "xxpassword"
    gitlab_rails['smtp_domain'] = "163.com"
    gitlab_rails['smtp_authentication'] = :login
    gitlab_rails['smtp_enable_starttls_auto'] = true

    ##修改gitlab配置的发信人
    gitlab_rails['gitlab_email_from'] = "xxuser@163.com"
    user["git_user_email"] = "xxuser@163.com"

# Update Nginx Port

    [root@localhost ~]# vim /var/opt/gitlab/nginx/conf/gitlab-http.conf  //修改端口
    server {
      listen *:8001;
      server_name 192.168.15.87;
    }
# Restart gitlab
    [root@localhost ~]# gitlab-ctl restart



# Default Account & Login

    http://192.168.15.87:8001/users/sign_in
    Username: root
    Password: 5iveL!fe



# 常用命令
    [root@localhost ~]# gitlab-ctl stop
    [root@localhost ~]# gitlab-ctl start
    [root@localhost ~]# gitlab-ctl status
    [root@localhost ~]# systemctl status nginx 
    [root@localhost ~]# gitlab-ctl restart nginx
    [root@localhost nginx]# gitlab-ctl tail


# 默认安装目录

    /var/opt/gitlab/




# 本地如何使用


    用户在本地创建public key..然后Copy public并上传到服务器。
    C:\Users\baoguo\.ssh 运行Git Bash Here
    $ ssh-keygen -t rsa -C "baoguo.ding@foxmail.com"



    Command line instructions


    Git global setup

    git config --global user.name "Administrator"
    git config --global user.email "admin@example.com"

    Create a new repository

    git clone git@192.168.15.87:root/sample.git
    cd sample
    touch README.md
    git add README.md
    git commit -m "add README"
    git push -u origin master

    Existing folder or Git repository

    cd existing_folder
    git init
    git remote add origin git@192.168.15.87:root/sample.git
    git add .
    git commit
    git push -u origin master



参考：

[GitLab在CentOS7下LNMP环境的安装使用](http://blog.csdn.net/w670328683/article/details/50736977)
