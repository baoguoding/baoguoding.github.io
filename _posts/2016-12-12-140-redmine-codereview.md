---
layout: post
title: Redmine安装插件codereview
pid: 140
tags: [redmine, codereview]
---


http://www.redmine.org/plugins/codereview

https://bitbucket.org/haru_iida/redmine_code_review/downloads/redmine_code_review-0.7.0.zip


# 操作步骤
      1. Copy the plugin directory into the plugins directory
      2. Migrate plugin:
         rake redmine:plugins:migrate RAILS_ENV=production
      3. Start Redmine
      4. Add code review module into your project.
      5. Go to code review setting tab in the project setting page and select tracker.


      [root@localhost ~]# cd /opt/redmine/plugins/
      [root@localhost plugins]# unzip redmine_code_review-0.7.0.zip 
      [root@localhost plugins]# rake redmine:plugins:migrate RAILS_ENV=production
      [root@localhost plugins]# cd /opt/redmine/
      [root@localhost redmine]# ./bin/rails server -p3000 -b0.0.0.0 -e production -d


      管理 >> 跟踪标签 >>　建一个 Code Review 的标签
      管理 >> 项目 >> xxx 项目 >> 配置 >>　模块 >>　启用代码评审， 点击保存



# 错误信息

      ActiveRecord::StatementInvalid (Mysql2::Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ':conditions=>["project_id = ? and issue_id is NOT NULL", 1]}) FROM `code_reviews' at line 1: SELECT COUNT({:conditions=>["project_id = ? and issue_id is NOT NULL", 1]}) FROM `code_reviews`):
        plugins/redmine_code_review/app/controllers/code_review_controller.rb:40:in `index'
        lib/redmine/sudo_mode.rb:63:in `sudo_mode'

  
  
    @review_count = CodeReview.count(:conditions => ['project_id = ? and issue_id is NOT NULL', @project.id])
    @all_review_count = CodeReview.count(:conditions => ['project_id = ?', @project.id])


改成

    @review_count = CodeReview.count("project_id = " + @project.id.to_s + " and issue_id is NOT NULL")
    @all_review_count = CodeReview.count("project_id = " + @project.id.to_s)




# 参考资料

1. [使用Redmine 作为issue管理系统](http://blog.csdn.net/csfreebird/article/details/12947039)
2. [Redmine 插件：使用 Gitlab 账号登录](https://www.testwo.com/blog/7728)
3. [基于jenkins+gitlab+redmine构建持续集成环境（一）](http://www.simlinux.com/archives/542.html)
4. [Gitlab OAuth2 Application简明教程](https://afoo.me/posts/2015-12-17-create-a-gitlab-oauth2-application.html)
5. [redmine + gitlab (github) 整合、同步更新](http://tech-tacolin.blogspot.com/2013/06/redmine-gitlab-github.html)
6. [Redmine 插件安装](https://my.oschina.net/farces/blog/296514)
7. [500 Error on plugin from recent installation](https://bitbucket.org/haru_iida/redmine_code_review/issues?status=new&status=open)
