---
title: python语句
urlname: lp1g3v
date: '2021-08-12 12:15:52 +0800'
<br />title: python语句
toc: true
tags:
  - python语句
  - python
  - 计算机
  - 计算机语言
categories:
  - 计算机
  - 计算机语言
  - Python
---

​

程序是什么：一个指令的序列，来告诉机器如何进行一组运算
专注于编程，而不是编程语言
​

- 运算符

运算符：+-\*/  \*\* (乘方) ^（异或）

## 1. 值和类型

```python
>>> type(2)
<class 'int'> #整形
>>> type(42.0)
<class 'float'> #浮点型
>>> type('Hello, World!')
<class 'str'>  #字符型
```

## 2. 变量，表达式，语句

### 2.1   赋值语句

```python
x = xxx #第一个x是变量名，xxx是需要赋值的对象
```

变量名不限制长度，不能数字开头，对大小敏感。支持下划线\_，例子 your_name。特殊关键词不能作为变量名
​

### 2.2   表达式和语句

```python
b = n + 25
```

表达式是数值,变量和操作符的组合。单个值或变量都如此
语句是一组具有某些效果的代码，比如创建变量，或者显示值。
语句是可以单独出结果的，而表达式是被语句包含的，得出某个结果，交给语句处理。换句话说，解释器执行语句
​

### 2.3   运算符优先级

```python
();**;*/;+-
```

从左往右，每个分隔符代表一个优先级；同级从左往右，乘方除外。可以用括号明确提级
3.2 字符串操作

```python
+：字符串拼接
*：字符串重复和拼接
```

### 2.3   注释

```python
#来开头。注释多是要解释这样做的目的是什么。
```

### 2.4   文档字符串

```python
def number():
"""
这是一段文档字符串
这个函数用于输出hello字符
"""
	print('Hello!')
number()
```

文档字符串是指：在函数开头部位，解释函数的交互界面的字符串，doc 是文档 documentation 的缩写

### 2.5   调试

- _语法错误：程序的结构和规则出错_
- _运行错误（异常）：直到运行的时候才会出现的错误_
- _语义错误：指你的程序运行没问题，也不产生错误信息，但不能正确工作_

## 3. 函数

### 3.1   函数调用

```python
>>> type(42)  #type即使一个函数，括号内即函数的参数
<class 'int'>
```

函数都要“传入”一个参数，“返回”一个结果。结果也被叫做返回值
​

### 3.2  Math functions（数学模块）

```python
import math #导入模块
具体变量名百度找
```

_模块：模块就是一系列相关函数的集合成的文件。_
_​_

### 3.3   添加新函数

```python
def print_lyrics():
	print("I'm a lumberjack, and I'm okay.")
```

def 表示在定义一个函数，随后跟函数名，括号代表函数的参数，空就是不需要，末尾必须冒号。这些组成头部，剩下叫做函数体

> 单引号和双引号效果一样，一般都是用单引号，除非字符串中已经出现

​

### 3.4   运行流程

- 一个 Python 程序都是从第一个语句开始运行的。从首至尾，每次运行一个语句
- 函数定义不会改变流程顺序，函数体语句只有在函数被调用才运行
- 调用函数就跳入函数体，然后从离开的地方继续执行

​

### 3.5   形式参数和实际参数

_实际参数：就是调用函数时候传给他的那个参数_
_形式参数：函数内部定义用的参数_

> 函数内部变量和形参都是局部的

​

### 3.6   栈图

![](https://raw.githubusercontent.com/liaozonglong/photo/main/img/202108301042947.png#id=phtsO&originHeight=188&originWidth=340&originalType=binary∶=1&status=done&style=none#crop=0&crop=0&crop=1&crop=1&id=Ep0T3&originHeight=188&originWidth=340&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)
每个函数都用一个框架来表示。框架的边上要标明函数的名字，框内填写函数内部的形参和变量。一个栈中的这些框也表示了函数调用的关系等等
**_main_：属于最外层框架，也被叫做主函数。当在所有函数外定义一个函数时，这个变量就属于主函数所有**
_​_

### 3.7   有返回值的函数和无返回值的函数

如果是脚本模式，你运行一个有返回值的函数，但没有利用这个返回值，这个返回值就会永远丢失了

### 3.8   封装

```python
def number():
	print('Hello!')
number()
```

代码定义到一个函数里面，然后调用这个函数

### 3.9   泛化

```python
def number(a):
    for i in range(a):
		print('Hello!')
number(x) #此处x输入数字
```

给函数添加一个参数

### 3.10   重构

```python
def number(a):
	shuzi = 1
	for i in range(a):
		print(shuzi)
		shuzi = shuzi + 1
number(x) #此处x输入数字
```

改进了界面设计，增强了代码再利用，这就叫做重构

## 4.   模块

### 4.1   乌龟模块

```python
import turtle
bob = turtle.Turtle()
```

## 5.   语句

### 5.1   地板除法

```python
minutes = 105
hours = minutes // 60
1
```

会把运算结果的小数位舍弃，返回整值

### 5.2   求模运算符

```python
minutes = 105
remainder = minutes % 60
remainder
45   #求余数
```

### 5.3   布尔表达式

```python
5 == 5
True
5 == 6
False
x != y #二者相等
x > y #前者更大
x < y #前者更小
x >= y #大于等于
x <= y #小于等于
```

只有两个值，true（真）或者 false（假）

### 5.4   逻辑运算符

```python
x > 0 and x < 10 #x仅在0-10之间才为真——且
n%2 == 0 or n%3 == 0  #一个条件为真就为真——或
not (x > y) #当x>y成立，则本条件为假，反之相反
```

逻辑运算符有三种：且，或以及非

### 5.5   条件执行

#### 5.5.1  if 语句

```python
if x > 0:
    print('x is positive')
```

if 背后是布尔表达式，条件为真，缩进语句即执行，反之相反

#### 5.5.2   选择执行

```python
if x % 2 == 0:
	print('x is even')
else:
	print('x is odd')
```

存在两种备选语句，根据条件来判断。这些选择也叫【分支】

#### 5.5.3   链式条件

```python
if x < y:
    print('x is less than y')
elif x > y:
    print('x     is greater than y')
else:
    print('x and y are equal')
```

第一个为假，第二个就会被检查，以此类推。如果有一个为真，相应语句就会运行，条件判断也就结束。如果有多个条件为真，只有第一个会运行

#### 5.5.4   嵌套条件

```python
if x == y:
    print('x and y are equal')
else:
    if x < y:
        print('x is less than y')
    else:
        print('x is greater than y')
```

#### 5.5.5   递归运算

```python
def countdown(n):
    if n <= 0:
        print('Blastoff!')
	else:
    	print(n)
    	countdown(n-1)
```

函数来调用自己也是允许的。这就是递归

#### 5.5.6   无穷递归

如果一个递归一直都不能到达基准条件，那就会持续不断地进行自我调用，程序也就永远不会终止了。这就叫无穷递归

#### 5.5.7   键盘输入

```python
name = input('What...is your name?\n')
What...is your name?
Arthur, King of the Britons!
name
Arthur, King of the Britons
```

了内置的一个函数，名叫 input

### 5.6   循环语句

#### 5.6.1  for 语句

```python
for i in range(4):
	print('Hello!')
```

_​_
