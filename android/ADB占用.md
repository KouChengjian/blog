---
layout: post
title:  "ADB端口被占用"
date:   2017-01-19 14:00:00 +0800
categories: Android
tag: ADB
#excerpt: Jekyll是一个静态网站生成工具。它允许用户使用HTML、Markdown或Textile来建立静态页面，然后通过模板引擎Liquid（Liquid Templating Engine）来运行.
---

* content
{:toc}

在pc下经常会发生adb端口被占用，遇到这种情况只要找到那个服务kill掉就好了<br/>
（经常是豌豆荚或者酷狗，运行jekyll时候4000端口经常被Foxmail的一个服务占用/(ㄒoㄒ)/~~）





### 5037为adb默认端口 查看该端口情况如下：

      netstat -aon|findstr "5037"
      TCP    127.0.0.1:5037         0.0.0.0:0              LISTENING       6540
      
### 发现6540占用了 5037端口，继续查看6540的task，发现是wandoujia  .如下所示

        tasklist|findstr "6540"
        wandoujia_daemon.exe          6540 Console                    1      4,276 K