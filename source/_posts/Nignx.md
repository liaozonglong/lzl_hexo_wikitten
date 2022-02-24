---
title: Nignx
urlname: sgvqgb
date: '2021-08-12 12:15:52 +0800'
<br />title: Nignx
tags:
  - Nignx
categories:
  - 计算机
  - 服务
  - WEB服务
---

​

apt-get install nginx #安装 Nginx
apt install spawn-fcgi #通用 FastCGI 进程管理器
apt-get install fcgiwrap # Fcgiqwrap 是另外一个 CGI 封装库，跟 Simple CGI 类似。
spawn-fcgi -a 127.0.0.1 - p 8888 -f /usr/sbin/fcgiwrap #绑定服务 IP 和端口指定 fcgiwrap 目录
netstat -tlnp | grep fcgiwrap #查看端口状态
service nginx restart #重启 Nginx
/etc/init.d/nginx stop #关闭 Nginx
/etc/init.d/nginx start   #打开 Nginx
​

参考资料：
[ubuntu 安装 nginx](https://blog.csdn.net/qq_23832313/article/details/83578836)
[nginx 重启几种方法](https://www.cnblogs.com/yadongliang/p/9212795.html)
