
> # Python record in Windows
Jian@Harman

# 1 Installation
** python, pip, virtualenv, ipython **
## 1.1 Windows
### 1.1.1 python
download python from python.org, and pip was installed as default
python website[www.python.org]

default python 解析器 CPython是官方默认的，安装好之后就已经有了。
ipython是基于CPython的交互式解析器

交互模式和执行模式

### 1.1.2 pip
#pip install virtualenv						# 安装最新版本
#pip install virtualenv==version		# 指定安装版本
#pip list
#pip freeze

也到pypi下载所需要的包到本地，进入目录，通过pip对whl安装
#pip install virtualenv-15.1.0-py2.py3-none-any.whl


### 1.1.3 virtualenv
#virtualenv envp
#cd C:\Users\jikang\envp\Scripts
#active.bat
(envp)#pip -V
(envp)#pip install ipython
(envp)#ipython -V
(envp)#ipython
In [1]:print("hello world")
hello world
In [2]:exit()
(envp) #C:\Users\jikang\envp\Scripts>deactivate.bat
C:\Users\jikang\envp\Scripts>

[# windows下搭建virtualenv、virtualenvwrapper虚拟环境](https://blog.csdn.net/shaququ/article/details/54292043)
[# virtualenv和virtualenvwrapper插件的使用](https://www.jianshu.com/p/6a3ff66cb8d3)
[# Virtualenv和Virtualenvwrapper的配置使用](https://blog.csdn.net/leafage_m/article/details/72854559)
[# virtualenvwrapper详解](https://blog.csdn.net/taiyangdao/article/details/53890580)

### 1.1.4 ipython
to be updated
[ipython常用方法说明](https://blog.csdn.net/u013358302/article/details/51436079)
[笔记:IPython基础](https://www.jianshu.com/p/bbd44c7b99cf)

> %env          										# display environment including OS, python and ipython
> #cls													# clear screen
> #%save filename.py   n1-nx         	# save script to file
> 

### 1.1.5 installed location
**python** @: C:\Python27
**package** @: C:\Python27\Scripts		# including easy_install, pip and virtualenv
**envp** @: C:\Users\jikang\envp\Scripts, 因为在cmd默认路径C:\Users\jikang执行的



## 1.2 Linux
to be updated
### virtualenv 
- active, 
- deactive, 
- source 
- rm -rf project

安装路径
- lib: ??
- site-packages: ??

python源文件开头
==#!/usr/bin/env python== 

# 2 常用命令, 函数和包
 ## 2.1 命令
 - type(对象)		# 查看对象类型
 - dir(类型或者对象)		# dir(list)或dir(l1) 列出所有属性和方法
 - help(???)						# help(list.count)或help(l1.count) 查看方法帮助文档
 - s.format()					# 简单格式化输出
 - %									# 定制格式化输出
 - vars()							# 打印python当前系统内存缓存的变量
 - __buildins__
 - __buildin__
- 单行注释以 **#** 开头
 

## 2.2 函数
函数名称|解释|how to
-|-|-
int(100)|强制转换100|
len(对象)	| 求对象的长度 | #len(s1) / #len(l1)
id() | 查看对象的指针 | #id(s1) / #id(l1)
range(start, stop[, step])|返回start到stop-1的数字，start default 0|range(100),range(5,20),range(12, 1000, 8)

- 内定函数locals()

 ## 2.3 包
**numpy** : 科学计算
**pandas**：
**scipy**：
**matplotlib**：
**random**: 产生随机数
**sys**: 
- import MODULE
- import MODULE1, MODULE2, ...
> import math
> math.pi

- from MODULE import <method> /<方法>
> from math import pi
> pi

- import MODULE as short-name
- ==import function ???==


[how to use **random** module](http://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)

## 2.4 常用数据传输格式
- JSON： 网络传输
- csv：报表
- XML：多用于传输过程中
- 

## 2.5 Regulations
PEP8: 

## 2.6 术语中英对照
English | Chinese
---------|-------
class | 类别
dict | 字典
identity | ???
iterable |迭代
method | 方法
object | 对象
?? | 属性
shallow copy | 浅拷贝
type | 类型
tuple | 元组

- 弱变量语言
- 对象 **.** 属性
- 对象 **.** 方法 **()**

# 3 数据类型和变量
数据类型|描述
-|-
整数|正数，负数，0；十进制，十六进制(0x/0X)，八进制(0o/0O)
浮点数| 常规，科学计数法1.23e8,-1.23e8, 1.23e08, -1.12e-8, e同样可以是E
字符串|'' or "", "" to cover string with ' like "I'm OK"
-|转义字符'\\', \n:换行, \t:制表符, 
- | 字符串前添加 __r__ 用来表示字符串内的单或双引号不转义
- | 字符串包含多行，可以用三引号 ‘’‘ 括起来引用，也可以是三双引号"""
_ | 当然r和三引号可以组合使用
布尔值|True, False
-|运算：and, or, not(与，或，非)
空值|None, None不是0
除法|'/'和'//'两种：前为浮点除，哪怕结果为整数仍得到浮点结果，如9/3，结果为3.0(__python 3.x版本__)

弱变量语言：
```python
> a = 10		# a为整数
> print (a)
> a = 'ABC'		# a为字符串
> print(a)
```
这种变量本身类型不固定的语言称之为 __==动态语言==__，与之对应的是 __静态语言__。静态语言在定义变量时必须指定变量类型，如果赋值的时候类型不匹配，就会报错。

常量：在Python中，通常用全部大写的变量名表示常量。

# 4 string
## 4.1 Definition
s = "Hello world"
- sample code: #print("hello world")或#print(s)
- Windows下路径反转，可以在string前加上**r**
- #print(r"C:\Users\jikang\envp\Scripts>")
- 多行string用三个引号括起来 **"""**


以#s="python"为例的一些命令和结果
command | output
-|-
#type(s)|str
#len(s)|6
#s[0]|'p'
#s[0:4]|'pyth'
#s[0:4:2]|'pt'
#s[6]	|IndexError: string index out of range
#s[:-1]	|'pytho'        # -1为str的最后一个
#s[:] |'python'
#s*2 | 'pythonpython'

- python 2.x 只支持ASCII字符
- python 3.x支持Unicode，即中文字符
```python
> ord('A')
> 65
> ord('中')
> 20013
> chr(66)
> 'B'
> chr(25991)
> '文'
> #如果知道字符的整数编码，还可以用十六进制写
> '\u4e2d\u6587'
> '中文'
```
- bytes数据类型用带 __b__ 的单引号或双引号表示
```python
> x = b'ABC'
```
- Unicode表示的字符串可以用encode()编码为指定的bytes
```python
> 'ABC'.encode('ascii')
> b'ABC'
```''

## 4.2 method
method | description | how to | output
-----|----|----|---
chr(num)	| 把数字转换为字符 | #chr(100)
ord(char)	| 把字符转换为数字 | #ord('A')
s.partition(sep) | 分割字符串 | #s.partition('y')|#('p', 'y', 'thon')
-|-|#s.partition('y')[2]|#'thon'
s.join(iterable)|把s插入iterable，并返回|s.join('ABC')|#'ApythonBpythonC'

# 5 List
## 5.1 Definition
#l1 = [1, 2, 3, 4, 5, 6]
#len(l1)
6
## 5.2 method
- python 2.7，list有9个method
- python 3.x，有11个method
- 同样的method，在不同的python版本有不同的用法和含义

method | description | how to
 - | :- | :-
append() | 
count() |
extend() |
index(object) |# 查找并返回第一个匹配object的索引值 | 
insert(index, object)|
pop(index)|# 弹出index索引的object，返回该值
remove(value)|# 移除list中的第一个value值
reverse(list)|翻转list|#l1.reverse()/#list.reverse(l1)
sort()|list排序|#l1.sort()
||
clear()|v3.x |
copy() | v3.x, 这里有深拷贝和浅拷贝的区别|
 - #l=ABC
 - #l*2 -> ABCABC


# 6 dict
## 6.1 Definition
#d = {'no':1, 'name':"Jack", 'age':20, 'address':"hongmei road"， ‘more’:{'topic':'software', 'experience':10}}
command | output | comments
-|-|-
#d|{'address': 'hongmei road', 'age': 20, 'more': {'experience': 10, 'topic': 'software'}, 'name': 'Jack', 'no': 1} |# 字典的键值对不会根据定义顺序，而是乱序存储
#len(d) | #5|字典键值对个数
#d['address']|'hongmei road' | 按键取值
#d['more'] | {'experience': 10, 'topic': 'software'} | 返回键值，为另一个字典
#d['more']['topic'] | 'software'|按键取值

## 6.2 method
method | description | how to | output
-|-|-|-
 'clear' | 
 'copy' | shallow copy | d1=d.copy() | d1指向d同一片内存区域？？？
 'fromkeys' |
 'get' |
 'has_key' |
 'items'|
 'iteritems'|
 'iterkeys'|
 'itervalues'|
 'keys'|
 'pop'|
 'popitem'|
 'setdefault'|
 'update'|
 'values'|
 'viewitems' | 输出字典内容 | d.viewitems() | dict_items([('more', {'topic': 'software', 'experience': 10}), ('age', 20), ('address', 'hongmei road'), ('name', 'Jack'), ('no', 1)])
 'viewkeys' | 输出字典的键 | d.viewkeys() | dict_keys(['more', 'age', 'address', 'name', 'no'])
 'viewvalues' | 输出字典的值 | d.viewvalues() |  dict_values([{'topic': 'software', 'experience': 10}, 20, 'hongmei road', 'Jack', 1])

# 7 tuple
## 7.1 definition
t = (1,1,1,1,2,3,4,5,6)
- #type(t)  -> tuple
- #len(t) -> 9
- #dir(t)  -> count, index
- 原组定义好之后不可变

## 7.2 method
method | description | how to | output
-|-|-|-
count|计算原组中指定value出现的次数|t.count(1)|4
-|-|-|t.count(10)|0
index|返回原组中第一次出现指定value的位置|t.index(5)|7
-|-|-|t.index(1)|0
-|-|-|t.index(8)|ValueError: tuple.index(x): x not in tuple

# 8 control flow
## 8.1 if
6种判断条件：<, <=, >, >=, ==, !=
True和False
条件语句
复合语句

`if <test>:
	handle`

`if <test>:
	pass
else:
	pass`

`if <test>:
	pass
elif <test>:
	pass
else:
	pass`

## 8.2 for and while
- for 为已知循环次数

> for i in range(100):
>   print(i)
将会打印0到99个数字
- while为未知条件判断
> a = 10
> while a <= 100:
> print('count %s' % a)
> a += 1
会打印从10开始的3累加到100的数字
- beark语句，只能用在循环体中
> a = 10
> while a  <= 100
> if a % 3 == 0:
> break;
> else:
> print('count %s' % a)
> a += 1
此时只打印10，11. 当a累加到12时，对3取余为零，就满足了if判断条件，就会执行break跳出.

# 9 file access
- 判断文件是否存在：
> import os
> os.path.exists(filepath)

- 打开文件
> open(path, mode)|path: mode: r/w/x/a/b|

打开不需显式关闭，用后系统自动close文件的用法：
> with open(filepath, mode) as f:

- 读文件：
> read
> readline
> readlines

- write





Windows因为路径反转，需要在路径前加上r，如
> filepath="C:\Users\jikang\envp\Scripts\ipython-help.txt"

method | description | example
-|-|-

 'close'|
 'closed'|
 'encoding'|
 'errors'|
 'fileno',
 'flush',
 'isatty',
 'mode',
 'name',
 'newlines',
 'next',
 'read',
 'readinto',
 'readline',
 'readlines',
 'seek',
 'softspace',
 'tell',
 'truncate',
 'write',
 'writelines',
 'xreadlines']

> filepath="C:\Users\jikang\envp\Scripts\ipython-help.txt"
> import os
> if os.path.exists(filepath):
> open(filepath, 'r')
> print(readline(100))
> print(readlines(100))

# 10 input and output
 - python 2.x: 用户输入什么，类型就是什么 
 - python 3.x: 均为str

- print
- ==input??==

# 11 函数
- 功能->逻辑->抽象
- 形参，实参，位置传参
- 函数嵌套
- ==内定函数locals(), return sum, locals() ??==

```python
> def func(y, x=10):
> func(y=20, x=50)		# 调用OK, 关键字参数

> def func2(*args):
> print(type(args))
> return args[0]
> 
> func2(1,2,3,4,5,6,7,8)
> <type 'tuple'>
> 1

> *args			# tuple, 参数不定长
> **args		# dict

> def func(*args, x)
> #func(1,2,3, x=100)		# 显式指定关键字参数

- 函数嵌套
> def external(1):
	def intenal(y):
		return X*y
	return local
```
- 变量作用域：LEGB (Local, EEEEE, GLobal, Buildin:本地，嵌套，全局，内置)

- 装饰器@
- 

# OOP


# python file purpose
- execution
- import as module
- 

# IDE, Tools, Books, Websites, etc....
## IDE
pycharm
Atom

==列表推导式==
- [i for i in 'abcdefg']
- (i for i in range(100))


# practice
## Poker

## mysql access


# Markdown rules


_ABC_
__ABC__
==ABC==
~~ABC~~
> ABC

- ABC
- XYZ

* ABC
* XYZ

+ ABC
+ XYZ

1. ABC
2. XYZ
3. TTT

- [ ] ABC
- [x] ABC

> quoted text

some `inline code`
```
multi lines code 1
mutli lines code 2
```

```python
specified code language: python
s = "Hello worrld"
print(s)
```
```c
specified code language: c
str[] = "Hello world";
printf("%s", str);
```
== H-2-O is ==
2^10^ is 1024
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NDMwMTg1NzcsLTQ2MTMxOTA4OSwxNT
g4NzgzOTU2LC0yMjYxMjgyNzUsLTEwMTAxNTA0OTAsOTgyNDY2
NjExLC04MjQxNjMxOTQsLTIwMDg5NDQxNDAsOTc0NTE5NjQ3LD
M0NTYyMzYyNiwtNzE0MjUyNzk4LC0xNDU1MDMwMDAsMzE2NTQ5
MjYyLC0yMDcwMDgyMDY0LDE3MTUyNzMyMzAsLTY4MTk5MjE0Ni
wxMTA3ODg3MjM1LDIwNzQ3MzYsLTczODkzNjE5Nyw5NjEzMzM4
MjBdfQ==
-->