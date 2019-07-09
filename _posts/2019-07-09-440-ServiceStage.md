---
layout: post
title: 在ServiceStage上一键式搭建开发环境
pid: 440
tags: [servicestage, k8s, 微服务]
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

详细步骤及解释如下：
1. 根据脚手架工程生成hellosz项目
2. 将代码推送到GitHub上面
3. 将代码从Github上面pull到ServiceStage上面，创建了一个构建环境，并做了一个构建
4. 打成jar包，再从jar打成docker的docker的镜像包
5. 将镜像包推送到华为的镜像仓库中
6. 通过容器部署系统，将镜像拉到容器集群中，进行部署。
7. 同时还正常了一个构建任务，如下图：

![](/uploads/2019/07/09-06.png)

8. 还生成了一个流水线（发布），如下图：

![](/uploads/2019/07/09-07.png)

9. 我们可以到应用列表中查看应用

![](/uploads/2019/07/09-08.png)

10. 验证一下是否发布成功

可以通过这个路径查看调用参数

基础设置\微服务引擎（CSE）\查看控制台\服务目录\hellosz\服务契约

http://122.112.159.12:12345/rest/helloworld?name=aaa




# 注意

+ K8S集群华为新用户，可以免费用3天


