---
title: Apache2
urlname: fxqlwl
date: '2021-08-12 12:15:52 +0800'
<br />title: Apache2
tags:
  - Apache2
categories:
  - 计算机
  - 服务
  - WEB服务
---

sudo apt install apache2 -y #安装
vim /etc/apache2/sites-available/000-default.conf #修改默认路径

>

```
ServerAdmin webmaster@localhost
DocumentRoot /var/www/html    // 一般我们默认为这个作为网站的根目录
```

sudo apache2ctl -k restart #重启 Apache
​

​

​

参考文章：
[Ubuntu 18.04 下使用 Apache 搭建一个 web 服务器](https://blog.csdn.net/weixin_39212776/article/details/81192847)
