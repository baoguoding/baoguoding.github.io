---
layout: post
title: 微服务云应用平台ServiceStage
pid: 440
tags: [k8s, 微服务]
---

有幸参加《华为云开发者沙龙》，接触到ServiceStage相关的内容，现将相关内容整理如下：

+ [什么是ServiceStage？](https://support.huaweicloud.com/productdesc-servicestage/ss_productdesc_0001.html)

# 步骤如下

+ 打开[huaweicloud](https://www.huaweicloud.com)并进行实名认证
+ 打开[ServiceStage](https://console.huaweicloud.com/servicestage)
+ 点击持续交付，工程，创建云上工程
+ 选择基于模板创建
+ 选择语言 Java 8
+ 选择框架 CSE-Java(SpringMVC)
+ 选择部署系统 云容器引擎CCE
+ 填写配置信息
  + 项目名称： hellosz
  + 代码来源： GitHub
    + 用户名/组织： baoguoding
	+ 仓库名称： hellosz -- 代码仓库地址
  + 仓库组织： baoguo -- 镜像仓库地址
  + 部署集群：cc3-demo464644 -- 实际部署的物理机或者虚拟机
  + 集群命名空间：default -- 默认，如果为了区分，可以放dev，uat等等
  + 高级配置
    + 设置访问方式
	  + 服务名称：test
	  + 访问方式：公网
	  + 访问类型：负载均衡
	  + 端口映射：
	    + 容器端口： 8080
		+ 访问端口： 12345
+ 点击部署

在上面的步骤中，我们创建了
+ 购买集群

![](/uploads/2019/07/09-01.png)

+ K8S集群 CCE

![](/uploads/2019/07/09-02.png)

+ 负载均衡器

![](/uploads/2019/07/09-03.png)

+ 云上工程

![](/uploads/2019/07/09-04.png)

+ GitHub创建的源码

![](/uploads/2019/07/09-05.png)

基本上，到了这一步，整个微服务的开发环境，就创建好了。

可以将源代码clone到本地，查看一下。



# 注意

+ K8S集群华为新用户，可以免费用3天


