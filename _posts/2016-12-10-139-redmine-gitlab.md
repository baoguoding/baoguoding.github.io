---
layout: post
title: Redmine与Gitlab的简单集成
pid: 139
tags: [redmine, gitlab, 软件开发]
---
这个实验成功的前提是，我们的Redmine和gitlab是安装在同一台服务器上面。

不在同一个服务器上面的我没有测试成功，希望成功的朋友联系我baoguo.ding#foxmail.com


# From Gitlab to Redmine

## 更新配置文件gitlab.yml

    [root@localhost ~]# cd /var/opt/gitlab/gitlab-rails/etc/
    [root@localhost etc]# vim gitlab.yml 

      issues_tracker:
        redmine:
          title: "Redmine"
          project_url: "http://redmine/projects/:issues_tracker_id"
          issues_url: "http://redmine/:project_id/:issues_tracker_id/:id"
          new_issue_url: "http://redmine/projects/:issues_tracker_id/issues/new"


## 重启gitlab

    [root@localhost etc]# gitlab-ctl restart

# 在Gitlab里面设置redmine来做issuetracker
1. 登录到gitlab中
2. 选中项目 >> Setting >> Services >>
3. 选择Readmine，输入基本信息，点击保存。
4. 然后，你就可以点击Issue，跳转到Redmine中。



# From Redmine to Gitlab

## 查找自己项目的git文件

    [root@localhost ~]# cd /var/opt/gitlab/gitlab-rails/etc/
    [root@localhost etc]# vim gitlab.yml   //查找一个叫repos_path的配置
    [root@localhost etc]# cd /var/opt/gitlab/git-data/repositories
    //找到自己项目的git文件。


## 将上面git文件地址配置到redmine中

    1. 登录到redmine平台http://192.168.10.37:3000
    2. 项目 >> [你自己的项目] >> 配置 >> 版本库
    3. 新增版本库
    SCM: Git
    主版本库：Yes
    标识: xxx_project
    库路径： /var/opt/gitlab/git-data/repositories/root/xxx_project.git
    4. 点击保存。
    5. 点击标识xxx_project就可以查看提交。
    6. 点击用户，就可以把Redmine中的用户与Gitlab中的用户关联。
    7. 同样，也可以在活动中看到每日和系统相关的活动。
