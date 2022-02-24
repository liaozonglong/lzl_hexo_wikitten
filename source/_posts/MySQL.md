---
title: MySQL
urlname: bq6i41
date: '2022-01-27 09:41:54 +0800'
tags:
  - MySQL
  - 数据库
  - 服务
  - 计算机
categories:
  - 计算机
  - 服务
  - 数据库
---

## 安装以及配置

---

### ubuntu 下安装

sudo apt-get install mysql-client mysql-server

### 卸载 MySQL

查看 mysql：dpkg --list |grep mysql
删除 mysql：sudo apt-get remove mysql-\*
清理残留的数据 ：dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P

---

### 配置信息

#### 开放远程访问

```python
配置/etc/mysql/my.cnf

!includedir /etc/mysql/conf.d/
!includedir /etc/mysql/mysql.conf.d/
[mysqld]
# 设置3306端口
port=3306
# 设置mysql的安装目录
# basedir=/usr/local/mysql
# 设置mysql数据库的数据的存放目录
# datadir= /var/lib/mysql
# 允许最大连接数
max_connections=200
# 允许连接失败的次数。这是为了防止有人从该主机试图攻击数据库系统
max_connect_errors=10
# 服务端使用的字符集默认为UTF8
character-set-server=utf8mb4
#使用–skip-external-locking MySQL选项以避免外部锁定。该选项默认开启
external-locking = FALSE
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
# 默认使用“mysql_native_password”插件认证
default_authentication_plugin=mysql_native_password

[mysqld_safe]
log-error=error.log
#pid-file=mysqld.pid
# 定义mysql应该支持的sql语法，数据校验
sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8mb4
[client]
# 设置mysql客户端连接服务端时默认使用的端口
port=3306
default-character-set=utf8mb4
```

[

](https://www.cnblogs.com/zhongyehai/p/10695659.html)

#### 默认密码所在位置

Ubuntu18.04 安装过程中没有设置密码的环节(如果有就下面的不需要做了)
sudo cat /etc/mysql/debian.cnf
![](https://s2.loli.net/2022/01/29/gBEhdlZ5Nb4LSkx.png#crop=0&crop=0&crop=1&crop=1&id=D9HDC&originHeight=105&originWidth=299&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)

---

### 基础指令

service mysql restart #重启

---

## 基础语句

### 用户管理

---

**创建\删除\查看\修改**
use mysql; #进入 mysql 数据库

CREATE USER 'username'@'host' IDENTIFIED BY 'password'; #创建用户

drop user root; #删除用户

select host, user, authentication_string from mysql.user; #查看用户登陆主机\用户名\密码(不同版本 mysql 语句有出入)

SET PASSWORD FOR 'username'@'host' = PASSWORD('newpassword'); #设置与更改用户密码
​

flush privileges; #刷新系统权限表

---

### 权限管理

```sql
用户授权
GRANT privileges ON databasename.tablename TO 'username'@'host' 		#授权语句规则
格式：grant 权限 on 数据库.* to 用户名@登录主机 identified by "密码";　
说明:
privileges：用户的操作权限，如SELECT，INSERT，UPDATE等，如果要授予所的权限则使用ALL
databasename：数据库名
tablename：表名，如果要授予该用户对所有数据库和表的相应操作权限则可用*表示，如*.*
例子：
grant all privileges on tornado.* to 'haidon'@'%' identified by '123456';
flush privileges;
```

revoke all on tornado.\* from "haidon"@"%"; #收回用户权限
​

---

### 数据库管理

**创建\删除\查看\修改**
create database 数据库名; #创建数据库
create database article character set utf8; #创建并设置 utf8 格式

drop database <数据库名>; #删除数据库
​

show databses; #查看所有数据库

---

### 表管理

select \* from tb_info; #查看指定的表的现有数据

desc 表名; #查看指定表结构

```python
写入数据
INSERT INTO table_name ( field1, field2,...fieldN )
                        VALUES
                        ( value1, value2,...valueN );
```
