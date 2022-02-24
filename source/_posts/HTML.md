---
title: HTML
urlname: oc05vq
date: '2021-08-12 12:15:52 +0800'
<br />title: HTML
tags:
  - HTML
categories:
  - 计算机
  - 服务
  - WEB服务
---

​

action="cgi-bin/post.py" method="post" #设置传递目标与模式
import cgi, cgitb # 添加 GI 处理模块
form = cgi.FieldStorage() # 创建 FieldStorage 的实例化
str_data_1  =  form.getvalue('data_1') #获取 html 页面传递过来的数据值
[
](https://blog.csdn.net/Ikaros_521/article/details/102917453)
参考资料：
[HTML 发送表单给 python 处理](https://ikaros.blog.csdn.net/article/details/102917453?spm=1001.2101.3001.6650.6&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-6.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7Edefault-6.no_search_link)
