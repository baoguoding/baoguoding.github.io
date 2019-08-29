---
layout: post
title: 微服务：Config Server
pid: 458
tags: [微服务]
---

Spring Cloud Config为服务端和客户端提供了分布式系统的外部化配置支持。配置服务器为各应用的所有环境提供了一个中心化的外部配置。它实现了对服务端和客户端对Spring Environment和PropertySource抽象的映射，所以它除了适用于Spring构建的应用程序，也可以在任何其他语言运行的应用程序中使用。作为一个应用可以通过部署管道来进行测试或者投入生产，我们可以分别为这些环境创建配置，并且在需要迁移环境的时候获取对应环境的配置来运行。

配置服务器默认采用git来存储配置信息，这样就有助于对环境配置进行版本管理，并且可以通过git客户端工具来方便的管理和访问配置内容。当然他也提供本地化文件系统的存储方式，下面从这两方面介绍如何使用分布式配置来存储微服务应用多环境的配置内容。

![](/uploads/2019/08/15-01.png)

+ 首先我们需要一个远程的Git仓库，自己学习可以直接用GitHub，在在实际生产环境中，需要自己搭建一个Git服务器，远程Git仓库的作用主要是用来保存我们的配置文件
+ 除了远程Git仓库之外，我们还需要一个本地Git仓库，每当Config Server访问远程Git仓库时，都会保存一份到本地，这样当远程仓库无法连接时，就直接使用本地存储的配置信息
+ 至于微服务A、微服务B则是我们具体的应用，这些应用在启动的时候会从Config Server中来加载相应的配置信息
+ 当微服务A/B尝试去从Config Server中加载配置信息的时候，Config Server会先通过git clone命令克隆一份配置文件保存到本地
+ 由于配置文件是存储在Git仓库中，所以配置文件天然的具备版本管理功能，Git中的Hook功能可以实时监控配置文件的修改



+ [创建Config Server项目](https://start.spring.io/)
+ 添加注解 EnableConfigServer

```java
package com.baoguoding.configcenter;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.cloud.config.server.EnableConfigServer;

@EnableConfigServer
@SpringBootApplication
public class ConfigcenterApplication {

	public static void main(String[] args) {
		SpringApplication.run(ConfigcenterApplication.class, args);
	}

}
```

+ 更新 application.properties

```config
spring.application.name=config-server
server.port=7001

spring.cloud.config.server.git.uri=https://github.com/baoguoding/springcloud
spring.cloud.config.server.git.searchPaths=config-server
spring.cloud.config.server.git.username=******
spring.cloud.config.server.git.password=******
```

+ 访问 http://127.0.0.1:7001/center/dev/master
+ 新建 Config Client项目

+ 更新 application.properties

```properties
server.port=7002
```

+ 新增配置文件bootstrap.properties

```properties
spring.application.name=center
spring.cloud.config.profile=dev
spring.cloud.config.label=master
spring.cloud.config.uri=http://127.0.0.1:7001/
management.endpoints.web.exposure.include=*
```

+ 访问 http://127.0.0.1:7002/from

+ 自动刷新 http://127.0.0.1:7002/actuator/refresh
+ 健康检查 http://127.0.0.1:7002/actuator/health

# 参考
+ [分布式配置中心config server介绍](https://www.cnblogs.com/duanxz/p/3512408.html)
+ [Spring cloud config Server源码分析](https://www.cnblogs.com/duanxz/p/3510159.html)
+ [config-server因为server端和client端的健康检查导致服务超时阻塞问题](https://www.cnblogs.com/duanxz/p/11272215.html)
+ [示例1](https://github.com/baoguoding/springcloud)
+ [示例2](https://github.com/baoguoding/config-server)