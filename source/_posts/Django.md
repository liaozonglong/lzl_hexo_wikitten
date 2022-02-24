---
title: Django
urlname: vakykz
date: '2021-08-12 12:15:52 +0800'
<br />title: Django
tags:
  - Django
  - python
  - 计算机
  - 计算机语言
categories:
  - 计算机
  - 计算机语言
  - Python
---

## 基础命令

pip install django #安装 Django
django-admin.py startproject testdj #创建 django 项目
python3 manage.py runserver #运行 django 项目
​

参考：
[Django 安装](https://www.runoob.com/django/django-install.html)
[Django 创建第一个项目](https://www.runoob.com/django/django-first-app.html)

## 网站规则

>

## 修改网站路径：

> ![](https://i.loli.net/2021/11/15/ndXEWmatS41s3Gb.png#id=rnetn&originHeight=385&originWidth=622&originalType=binary∶=1&status=done&style=none#crop=0&crop=0&crop=1&crop=1&id=TeN5w&originHeight=385&originWidth=622&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)
> 项目中如果代码有改动，服务器会自动监测代码的改动并自动重新载入，所以如果你已经启动了服务器则不需手动重启。

>

## 修改模板文件的路径

> 修改 HelloWorld/settings.py，修改 TEMPLATES 中的 DIRS 为 **[os.path.join(BASE_DIR, 'templates')]**
> ![](https://i.loli.net/2021/11/15/ZE2wpJoI9fTYdnu.png#id=czyzP&originHeight=191&originWidth=562&originalType=binary∶=1&status=done&style=none#crop=0&crop=0&crop=1&crop=1&id=NFYKh&originHeight=191&originWidth=562&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)

[

]([https://www.runoob.com/django/django-first-app.html](https://www.runoob.com/django/django-first-app.html))

## 分离文档的表现形式和内容

```
HelloWorld/templates/runoob.html 文件代码：
<h1>{{ hello }}</h1>
```

```
修改 views.py，增加一个新的对象，用于向模板提交数据
from django.shortcuts import render

def runoob(request):
    context          = {}
    context['hello'] = 'Hello World!'
    return render(request, 'runoob.html', context)
```

```
向Django说明模板文件的路径，修改HelloWorld/settings.py，
修改 TEMPLATES 中的 DIRS 为 [os.path.join(BASE_DIR, 'templates')]
代码头引入OS,import OS；
```

参考：
[Django 模板](https://www.runoob.com/django/django-template.html)

## 数据库

sudo pip3 install pymysql # 安装 mysql 驱动  （必须）
create database runoob default charset=utf8;   # 创建一个名为 runoob 数据库，编码指定为 utf8：

---

**项目的 settings.py 文件中找到 DATABASES 配置项 #修改数据库连接信息：（必须）**

```
DATABASES = {
    'default':
    {
        'ENGINE': 'django.db.backends.mysql',    # 数据库引擎
        'NAME': 'runoob', # 数据库名称
        'HOST': '127.0.0.1', # 数据库地址，本机 ip 地址 127.0.0.1
        'PORT': 3306, # 端口
        'USER': 'root',  # 数据库用户名
        'PASSWORD': '123456', # 数据库密码
    }
}
```

---

** 告诉 Django 使用 pymysql 模块连接 mysql 数据库：   #修改连接模块（必须）**

```
# 在与 settings.py 同级目录下的 __init__.py 中引入模块和进行配置
import pymysql
pymysql.install_as_MySQLdb()
```

---

### 定义模型

#### 创建 APP

> Django 规定，如果要使用模型，必须要创建一个 app

django-admin.py startapp TestModel # 创建一个 TestModel 的 app （必须）
create database 数据库名称 default charset=utf8; # 防止编码问题，指定为 utf8

---

**修改 TestModel/models.py 文件  **

```
# models.py
from django.db import models

class Test(models.Model):
    name = models.CharField(max_length=20)
```

> 以上的类名代表了数据库表名，且继承了 models.Model，类里面的字段代表数据表中的字段(name)，数据类型则由 CharField（相当于 varchar）、DateField（相当于 datetime）， max_length 参数限定长度。

## [django--orm models 字段类型说明](https://www.cnblogs.com/lutt/p/13734813.html)

>

---

settings.py 中找到 INSTALLED_APPS 这一项，如下：   #添加 APP

```
INSTALLED_APPS = (
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'TestModel',               # 添加此项
)
```

### 完成配置后的命令

```
$ python3 manage.py migrate   # 创建表结构
$ python3 manage.py makemigrations TestModel  # 让 Django 知道我们在我们的模型有一些变更
$ python3 manage.py migrate TestModel   # 创建表结构
```

### 数据库操作

testdb.py 中写增删改查语句，urls 中写链接。详见[数据库配置](https://www.runoob.com/django/django-model.html)
​

参考：
[数据库配置](https://www.runoob.com/django/django-model.html)
​[django--orm models 字段类型说明](https://www.cnblogs.com/lutt/p/13734813.html)
​

## 表单

GET 方法：
POST 方法（提交数据时更常用） ：

```
<body>
    <form action="/search-post/" method="post">
        {% csrf_token %}		#csrf 全称是 Cross Site Request Forgery；Django提供的防止伪装提交请求的功能。POST 方法提交的表格，必须有此标签。
        <input type="text" name="q">
        <input type="submit" value="搜索">
    </form>

    <p>{{ rlt }}</p> 	# rlt 记号，为表格处理结果预留位置
</body>
```

​

参考：
[Django 表](https://www.runoob.com/django/django-form.html)
​

## 视图

### 视图层

> 一个视图函数，简称视图，是一个简单的 Python 函数，它接受 Web 请求并且返回 Web 响应。
> 响应可以是一个 HTML 页面、一个 404 错误页面、重定向页面、XML 文档、或者一张图片...
> 无论视图本身包含什么逻辑，都要返回响应。代码写在哪里都可以，只要在 Python 目录下面，一般放在项目的 views.py 文件中。
> 每个视图函数都负责返回一个 HttpResponse 对象，对象中包含生成的响应。
> 视图层中有两个重要的对象：请求对象(request)与响应对象(HttpResponse)。

### 请求对象: HttpRequest 对象（简称 request 对象）

#### 1、GET

取值格式：对象.方法。
get()：返回字符串，如果该键对应有多个值，取出该键的最后一个值。

```
def runoob(request):
    name = request.GET.get("name")
    return HttpResponse('姓名：{}'.format(name))
```

![](https://i.loli.net/2021/11/24/fCVnQ6ADSKBGa84.png#id=wudKG&originHeight=139&originWidth=584&originalType=binary∶=1&status=done&style=none#crop=0&crop=0&crop=1&crop=1&id=apIzg&originHeight=139&originWidth=584&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)

#### 2、POST

数据类型是 QueryDict，一个类似于字典的对象，包含 HTTP POST 的所有参数。

```
def runoob(request):
    name = request.POST.get("name")
    return HttpResponse('姓名：{}'.format(name))
```

![](https://i.loli.net/2021/11/24/ZCS8wjhrTABM2X6.png#id=Ns36f&originHeight=369&originWidth=1460&originalType=binary∶=1&status=done&style=none#crop=0&crop=0&crop=1&crop=1&id=wubRb&originHeight=369&originWidth=1460&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)

#### 3、body

数据类型是二进制字节流，是原生请求体里的参数内容，在 HTTP 中用于 POST，因为 GET 没有请求体。
在 HTTP 中不常用，而在处理非 HTTP 形式的报文时非常有用，例如：二进制图片、XML、Json 等。

```
def runoob(request):
    name = request.body
    print(name)
    return HttpResponse("菜鸟教程")
```

### 响应对象：HttpResponse 对象

响应对象主要有三种形式：HttpResponse()、render()、redirect()。
**HttpResponse():** 返回文本，参数为字符串，字符串中写文本内容。如果参数为字符串里含有 html 标签，也可以渲染。

```
def runoob(request):
    # return HttpResponse("菜鸟教程")
    return HttpResponse("<a href='https://www.runoob.com/'>菜鸟教程</a>")
```

**render()：** 第一个参数为 request，第二个参数为字符串（页面名称），第三个参数为字典（可选参数，向页面传递的参数：键为页面参数名，值为 views 参数名）。

```
def runoob(request):
    name ="菜鸟教程"
    return render(request,"runoob.html",{"name":name})
```

**redirect()。** 重定向，跳转新页面。参数为字符串，字符串中填写页面路径。一般用于 form 表单提交后，跳转到新页面。

```
def runoob(request):
    return redirect("/index/")
```

参考：
[Django 视图](https://www.runoob.com/django/django-views.html)
​

### 路由

参考：
[Django 路由](https://www.runoob.com/django/django-routers.html)
