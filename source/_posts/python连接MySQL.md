---
title: python连接MySQL
urlname: swvg55
date: '2022-01-27 09:29:16 +0800'
tags:
  - Python
  - 数据库
  - 计算机语言
  - 计算机
categories:
  - 计算机
  - 计算机语言
  - Python
---

python 连接 MySQL

```python
#!/usr/bin/python
# -*- coding: UTF-8 -*-

import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标
cursor = db.cursor()

# 使用execute方法执行SQL语句
cursor.execute("SELECT VERSION()")

# 使用 fetchone() 方法获取一条数据
data = cursor.fetchone()

print "Database version : %s " % data

# 关闭数据库连接
db.close()
```
