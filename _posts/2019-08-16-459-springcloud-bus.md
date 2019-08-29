---
layout: post
title: 微服务：Spring Cloud Bus
pid: 459
tags: [微服务]
---

+ 给项目configclient增加依赖

```pom
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-bus</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-bus-amqp</artifactId>
</dependency>
```

+ 在配置文件中增加关于RabbitMQ的连接和用户信息
```config
spring.rabbitmq.host=localhost
spring.rabbitmq.port=5672
spring.rabbitmq.username=springcloud
spring.rabbitmq.password=123456
```

+ 启动configclient

```
java -jar .\target\configclient-0.0.1-SNAPSHOT.jar --spring.profiles.active=c1
java -jar .\target\configclient-0.0.1-SNAPSHOT.jar --spring.profiles.active=c2
```

+ 访问 

```
http://127.0.0.1:7002/from
http://127.0.0.1:7003/from
```

+ 刷新bus

```
http://127.0.0.1:7002/actuator/bus-refresh
或者
http://127.0.0.1:7003/actuator/bus-refresh
```

# 原理

![](/uploads/2019/08/17-01.png)

整个方案的架构如上图所示，其中包含了Git仓库、Config Server、以及微服务“Service A”的三个实例，这三个实例中都引入了Spring Cloud Bus，所以他们都连接到了RabbitMQ的消息总线上。

当我们将系统启动起来之后，“Service A”的三个实例会请求Config Server以获取配置信息，Config Server根据应用配置的规则从Git仓库中获取配置信息并返回。

此时，若我们需要修改“Service A”的属性。首先，通过Git管理工具去仓库中修改对应的属性值，但是这个修改并不会触发“Service A”实例的属性更新。我们向“Service A”的实例3发送POST请求，访问/bus/refresh接口。此时，“Service A”的实例3就会将刷新请求发送到消息总线中，该消息事件会被“Service A”的实例1和实例2从总线中获取到，并重新从Config Server中获取他们的配置信息，从而实现配置信息的动态更新。

而从Git仓库中配置的修改到发起/bus-refresh的POST请求这一步可以通过Git仓库的Web Hook来自动触发。由于所有连接到消息总线上的应用都会接受到更新请求，所以在Web Hook中就不需要维护所有节点内容来进行更新，从而解决了通过Web Hook来逐个进行刷新的问题。

# 架构优化

既然Spring Cloud Bus的/bus/refresh接口提供了针对服务和实例进行配置更新的参数，那么我们的架构也相应的可以做出一些调整。在之前的架构中，服务的配置更新需要通过向具体服务中的某个实例发送请求，再触发对整个服务集群的配置更新。虽然能实现功能，但是这样的结果是，我们指定的应用实例就会不同于集群中的其他应用实例，这样会增加集群内部的复杂度，不利于将来的运维工作，比如：我们需要对服务实例进行迁移，那么我们不得不修改Web Hook中的配置等。所以我们要尽可能的让服务集群中的各个节点是对等的。

因此，我们将之前的架构做了一些调整，如下图所示：

![](/uploads/2019/08/17-02.png)

我们主要做了这些改动：

+ 在Config Server中也引入Spring Cloud Bus，将配置服务端也加入到消息总线中来。
+ /bus-refresh请求不在发送到具体服务实例上，而是发送给Config Server，并通过destination参数来指定需要更新配置的服务或实例。

通过上面的改动，我们的服务实例就不需要再承担触发配置更新的职责。同时，对于Git的触发等配置都只需要针对Config Server即可，从而简化了集群上的一些维护工作。

+ 刷新 http://127.0.0.1:7001/actuator/bus-refresh

# 参考

+ [Spring Cloud构建微服务架构（七）消息总线](https://www.cnblogs.com/duanxz/p/6678545.html)
+ [使用用户认证后 刷新配置端点bus-refresh](https://www.oschina.net/question/3877992_2281549?sort=time)
+ [401](https://www.twblogs.net/a/5b8160802b71772165ac5168/zh-cn)