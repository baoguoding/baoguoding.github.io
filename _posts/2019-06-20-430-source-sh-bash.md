---
layout: post
title: linux里source、sh、bash 有什么区别
pid: 430
tags: [centos, linux, k8s]
---

使用fork方式运行script时， 就是让shell(parent process)产生一个child process去执行该script，当child process结束后，会返回parent process，但parent process的环境是不会因child process的改变而改变的。

使用source方式运行script时， 就是让script在当前process内执行， 而不是产生一个child process来执行。由于所有执行结果均于当前process内完成，若script的环境有所改变， 当然也会改变当前process环境了。

使用exec方式运行script时， 它和source一样，也是让script在当前process内执行，但是process内的原代码剩下部分将被终止。同样，process内的环境随script改变而改变。


# 参考

+ [linux里source、sh、bash、有什么区别](https://www.cnblogs.com/pcat/p/5467188.html)