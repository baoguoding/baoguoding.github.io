---
layout: post
title: Gitlab访问出现 403 forbidden解决方案
pid: 494
tags: [gitlab, 软件开发]
---

``` shell
vim /etc/gitlab/gitlab.rb 

gitlab_rails['rack_attack_git_basic_auth'] = {
  'enabled' => true,
  'ip_whitelist' => ["127.0.0.1","101.00.125.00","333.65.12.43"],
  'maxretry' => 10,
  'findtime' => 60,
  'bantime' => 3600
}

gitlab-ctl reconfigure
history

```

进入Redis,删除被墙的IP

```shell
/opt/gitlab/embedded/bin/redis-cli -s /var/opt/gitlab/redis/redis.socket keys '*' | grep 'rack::attack' | xargs /opt/gitlab/embedded/bin/redis-cli -s /var/opt/gitlab/redis/redis.socket DEL
```


# 参考

+[Gitlab访问出现 403 forbidden解决方案](https://my.oschina.net/u/3242075/blog/1824763)
