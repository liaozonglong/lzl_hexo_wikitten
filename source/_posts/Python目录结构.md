---
title: Python目录结构
urlname: uq6l7u
date: '2022-01-25 15:20:41 +0800'
tags:
  - Python目录结构
  - Python
  - 计算机语言
  - 计算机
categories:
  - 计算机
  - 计算机语言
  - Python
---

/
**--docs————说明文档**
**--db————数据库相关**
**--projectname————源代码**
----**pycache**————标注该目录为模块
--tests————测试文件目录
--main.py————主程序入口
--README.md————项目版本说明文件
--readme.txt————项目说明文件
--requirements.txt——依赖包记录

```python
pip freeze > requirements.txt   #生成requirements.txt文件
```

--setup——脚本安装
--test_main.py——测试程序
