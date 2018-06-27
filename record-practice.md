
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
```
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
```

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

> dist-packages VS site-packages

dist-packages是Debian的特定惯例，包括Ubuntu，如果使用软件按转管理器安装，模块就会被安装在这里；
site-packages是手动安装python包的路径。所以Windows系统看到的默认就只有site-packages （python/lib/site-packages）.

主要目的是为了减少系统安装包和用户自定义安装之间的冲突。

这段代码用来查找python的包(lib)安装路径
```python
> from distutils.sysconfig import get_python_lib
> print(get_python_lib())
```
Ubuntu会输出：/usr/lib/python3/dist-packages
还有一个办法输出python的包相关路径
```python
> import sys
> print(sys.path)
```


python源文件开头
==#!/usr/bin/env python== 
==#!/usr/bin/env python3== 

# 2 常用命令, 函数和包
 ## 2.1 命令
 - type(对象)		# 查看对象类型
 - dir(类型或者对象)		# dir(list)或dir(l1) 列出所有属性和方法
 - help(???)						# help(list.count)或help(l1.count) 查看方法帮助文档
 - vars()							# 打印python当前系统内存缓存的变量
 - __buildins__
 - __buildin__
- 单行注释以 **#** 开头
 

## 2.2 函数
[build-in Functions](https://docs.python.org/3/library/functions.html)

数据类型转换函数|解释|how to
-|-|-
int()|int('123')|123
-|int(12.34)|12
float()|float('12.34')|12.34
str()|str(12.3)|'1.23'
-|str(100)|'100'
bool()|bool(1)|True
-|bool('')|False



函数名称|解释|how to
-|-|-
int('2018')|强制转换2018|
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
> '中文'.encode('uft-8')
> b'\xe4\xb8\xad\xe6\x96\x87'
> '中文'.encode('ascii')			# 执行出错
```
- 在bytes中，无法显示为ASCII字符的字节，用`\x##`显示。
- 反过来，如果我们从网络或磁盘上读取了字节流，那么读到的数据就是`bytes`。要把`bytes`变为`str`，就需要用`decode()`方法：
```python
> b'ABC'.decode('ascii')
> u'ABC'				# 2.7.13
> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
> u'\u4e2d\u6587'		# 2.7.13
```
==Python 3.x  to be checked== 
- 如果`bytes`中包含无法解码的字节，`decode()`方法会报错
- 如果`bytes`中只有一小部分无效的字节，可以传入`errors='ignore'`忽略错误的字节
> b'\xe4\xb8\xad\xff'.decode('utf-8', errors='ignore')
- 要计算`str`包含多少个字符，可以用`len()`函数
- `len()`函数计算的是`str`的字符数，如果换成`bytes`，`len()`函数就计算字节数
==Python 3.x  to be checked==
> len('ABC')
> len(b'ABC')
> len(b'中文')
> len(b'\xe4\xb8\xad\xe6\x96\x87')
__可见，1个中文字符经过UTF-8编码后通常会占用3个字节，而1个英文字符只占用1个字节。__

在操作字符串时，我们经常遇到`str`和`bytes`的互相转换。为了避免乱码问题，应当始终坚持使用UTF-8编码对`str`和`bytes`进行转换。

由于Python源代码也是一个文本文件，所以，当你的源代码中包含中文的时候，在保存源代码时，就需要务必指定保存为UTF-8编码。当Python解释器读取源代码时，为了让它按UTF-8编码读取，我们通常在文件开头写上这两行：
```python
#!/usr/bin/env python3
#-*- coding: utf-8 -*-
```
- 第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；
- 第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。
- 申明了UTF-8编码并不意味着你的`.py`文件就是UTF-8编码的，必须并且要确保文本编辑器正在使用UTF-8 without BOM编码
- 如果`.py`文件本身使用UTF-8编码，并且也申明了`# -*- coding: utf-8 -*-`，打开命令提示符测试就可以正常显示中文


## 4.2 method
method | description | how to | output
-----|----|----|---
chr(num)	| 把数字转换为字符 | #chr(100)
ord(char)	| 把字符转换为数字 | #ord('A')
s.partition(sep) | 分割字符串 | #s.partition('y')|#('p', 'y', 'thon')
-|-|#s.partition('y')[2]|#'thon'
s.join(iterable)|把s插入iterable，并返回|s.join('ABC')|#'ApythonBpythonC'
s.replace(old, new)|用new替换s中的old，返回一个新的字符串，原来的s不变|s.replace('a', 'A')|'Abc',但是s仍为'abc'

## 4.3 format
 - s.format()					# 简单格式化输出
 - %									# 定制格式化输出

格式化方式和C语言是一致的，用`%`实现
```python
> print('Hello %s' % 'world')
> Hello world
> print('Hi, %s, you have $%s.' % ('Micheal', 1000))
> Hi, Micheal, you have $1000.
```
- %d：整数
- %f：浮点数
- %s：字符串
- %x：十六进制整数
- 格式化整数和浮点数还可以指定是否补0和整数与小数的位数
> print('%2d-%02d' % (3, 1))
> print('%.2f' % 3.1415926)

- 如果你不太确定应该用什么，`%s`永远起作用，它会把任何数据类型转换为字符串
- 有些时候，字符串里面的`%`是一个普通字符怎么办？这个时候就需要转义，用`%%`来表示一个`%`
> 'growth rate: %d %%' % 7
> 'growth rate: 7 %'

字符串的`format()`方法，它会用传入的参数依次替换字符串内的占位符`{0}`、`{1}`……，
```python
'Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)
'Hello, 小明, 成绩提升了 17.1%'
```

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
insert(index, object)|index未插入位置，object为插入值
pop(index)|# 弹出index索引的object，返回该值;index可以省略即为最后一个元素
remove(value)|# 移除list中的第一个value值
reverse(list)|翻转list|#l1.reverse()/#list.reverse(l1)
sort()|list排序|#l1.sort()
||
clear()|v3.x |
copy() | v3.x, 这里有深拷贝和浅拷贝的区别|
 - #l=ABC
 - #l*2 -> ABCABC


# 6 tuple 元组
## 6.1 definition
t = (1,1,1,1,2,3,4,5,6)
- #type(t)  -> tuple
- #len(t) -> 9
- #dir(t)  -> count, index
- tuple元组一旦初始化就不能修改
- 不可变的tuple有什么意义？因为tuple不可变，所以代码更安全。如果可能，能用tuple代替list就尽量用tuple。
- tuple所谓的“不变”是说，tuple的每个元素，指向永远不变。

## 6.2 method
method | description | how to | output
-|-|-|-
count|计算原组中指定value出现的次数|t.count(1)|4
-|-|-|t.count(10)|0
index|返回原组中第一次出现指定value的位置|t.index(5)|7
-|-|-|t.index(1)|0
-|-|-|t.index(8)|ValueError: tuple.index(x): x not in tuple
定义空元组|t = ()|t|()
定义一个元素的元组|t = (1,)|t|(1,)
-|t = (1)这里的括号会被解析为数学公式的小括号，Python规定，这时按数学公式计算 | t|1
| |

一个“可变的”tuple
```python
> t = ('a', 'b', ['A', 'B'])
> t[2][0] = 'X'
> t[2][1] = 'Y'
> t
> ('a', 'b', ['X', 'Y'])
```
这里tuple的元素是不变的，包括第三个元素的指向（指向list）也是不变的，改变的是list的元素。

# 7 dict 字典
## 7.1 Definition
#d = {'no':1, 'name':"Jack", 'age':20, 'address':"hongmei road"， ‘more’:{'topic':'software', 'experience':10}}
command | output | comments
-|-|-
#d|{'address': 'hongmei road', 'age': 20, 'more': {'experience': 10, 'topic': 'software'}, 'name': 'Jack', 'no': 1} |# 字典的键值对不会根据定义顺序，而是乱序存储
#len(d) | #5|字典键值对个数
#d['address']|'hongmei road' | 按键取值
#d['more'] | {'experience': 10, 'topic': 'software'} | 返回键值，为另一个字典
#d['more']['topic'] | 'software'|按键取值

## 7.2 method
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
 'pop'|删除键值
 'popitem'|
 'setdefault'|
 'update'|
 'values'|
 'viewitems' | 输出字典内容 | d.viewitems() | dict_items([('more', {'topic': 'software', 'experience': 10}), ('age', 20), ('address', 'hongmei road'), ('name', 'Jack'), ('no', 1)])
 'viewkeys' | 输出字典的键 | d.viewkeys() | dict_keys(['more', 'age', 'address', 'name', 'no'])
 'viewvalues' | 输出字典的值 | d.viewvalues() |  dict_values([{'topic': 'software', 'experience': 10}, 20, 'hongmei road', 'Jack', 1])

- 查找key是不是在dict的方法有二：
- 通过in判断
> 'name' in d1
- dict的方法get()
> d1.get('name')					# 如果不存在返回，返回None
> d1.get('name', -1)			# 或者返回自定义值-1

- dict的key必须是**不可变对象**
- 通过key计算位置的算法称为哈希算法（Hash）
- 

# 8 set
- set和dict类似，也是一组key的集合，但不存储value。
- 由于key不能重复，所以，在set中，没有重复的key。
- set和dict的唯一区别仅在于没有存储对应的value
- 要创建一个set，需要提供一个list作为输入集合
```python
> s = set([1, 2, 3])
> s
{1, 2, 3}
```
传入的参数`[1, 2, 3]`是一个list，而显示的`{1, 2, 3}`只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的`
- 重复元素在set中自动被过滤
- `add(key)`      方法添加元素
- `remove(key)`方法删除元素

set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集、并集等操作
```python
> s1 = set([1, 2, 3])
> s2 = set([2, 3, 4])
> s1 & s2					# & 交集
{2, 3}
> s1 | s2					# | 并集
{1, 2, 3, 4}
```

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
- beark语句，只能用在循环体中，跳出循环体
```python
> a = 10
> while a  <= 100
> if a % 3 == 0:
> break;
> else:
> print('count %s' % a)
> a += 1
```
此时只打印10，11. 当a累加到12时，对3取余为零，就满足了if判断条件，就会执行break跳出.
- 在循环过程中，也可以通过`continue`语句，跳过当前的这次循环，直接开始下一次循环
```python
n = 0
while n < 10:
    n = n + 1
    if n % 2 == 0: # 如果n是偶数，执行continue语句
        continue # continue语句会直接继续下一轮循环，后续的print()语句不会执行
    print(n)
```


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
## 11.1 定义和使用
- 功能->逻辑->抽象
- 形参，实参，位置传参


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

函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”
```python
> a = abs # 变量a指向abs函数
> a(-1) # 所以也可以通过a调用abs函数
1
```

## 11.2 参数检查
必选参数外，还可以使用默认参数、可变参数和关键字参数
### 11.2.1 位置参数
```python
def power(x, n):
  s = 1
  while n > 0:
    n = n-1
    s = s*x
  return x
```
> power (10, 5)		

### 11.2.2 默认参数
- 可以定义 __默认参数__ 作为缺省情况，如经常计算平方值
> def power(x, n=2)
- 必选参数在前，默认参数灾后
- 变化大的默认参数在前，变化小的默认参数在后
- 如果使用了参数名（即为 ==关键字参数==），那么还可以不用按顺序调用
```python
def enroll(name, gender, age=6, city='Beijing'):
> enroll('Sarah', 'F')
> enroll('Bob', 'M', 7)
> enroll('Tom', 'M', city='Shanghai')
```
- 这里有一个陷阱需要注意
```python
def add_end(L=[]):
    L.append('END')
    return L
```
正常调用（不使用默认参数）时，结果似乎不错
```python
> add_end([1, 2, 3])
[1, 2, 3, 'END']
> add_end(['x', 'y', 'z'])
['x', 'y', 'z', 'END']
```
使用默认参数调用时，一开始结果也是对的
```python
> add_end()
['END']
```
但是，再次调用`add_end()`时，结果就不对了
```python
> add_end()
['END', 'END']
> add_end()
['END', 'END', 'END']
```
原因解释如下：
Python函数在定义的时候，默认参数`L`的值就被计算出来了，即`[]`，因为默认参数`L`也是一个变量，它指向对象`[]`，每次调用该函数，如果改变了`L`的内容，则下次调用时，默认参数的内容就变了，不再是函数定义时的`[]`了。
- ==定义默认参数要牢记一点：默认参数必须指向不变对象！==
要修改上面的例子，我们可以用`None`这个不变对象来实现
```python
def add_end(L=None):
    if L is None:
        L = []
    L.append('END')
    return L
```
- 为什么要设计`str`、`None`这样的 ==不变对象== 呢？因为不变对象一旦创建，对象内部的数据就不能修改，这样就减少了由于修改数据导致的错误。
- 此外，由于对象不变，多任务环境下同时读取对象不需要加锁，同时读一点问题都没有。我们在编写程序时，如果可以设计一个不变对象，那就尽量设计成不变对象。

### 11.2.3 可变参数
可变参数就是传入的参数个数是可变的，可以是1个、2个到任意个，还可以是0个。
以给定一组数字a, b, c, ...计算a^2^+b^2^+c^2^+...
 做法一：把参数定义为list或tuple
```python
def calc(numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
```
对应的调用的时候，就需要传入list或tuple
```python
>>> calc([1, 2, 3])				# list
14
>>> calc((1, 3, 5, 7))			# tuple
84
```
如果利用可变参数，调用函数的方式可以简化成这样:
```python
>>> calc(1, 2, 3)
14
>>> calc(1, 3, 5, 7)
84
```
函数定义使用可变参数传入
```python
def calc(*numbers):
    sum = 0
    for n in numbers:
        sum = sum + n * n
    return sum
```
- 定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个`*`号。
- 在函数内部，参数`numbers`接收到的是一个tuple，因此，函数代码完全不变。
- 但是，调用该函数时，可以传入任意个参数，包括0个参数：
```python
>>> calc(1, 2)
5
>>> calc()
0
```
如果已经有一个list或者tuple，要调用一个可变参数怎么办？可以这样做：
```python
>>> nums = [1, 2, 3]
>>> calc(nums[0], nums[1], nums[2])
14
```
这种写法当然是可行的，问题是太繁琐，所以Python允许你在list或tuple前面加一个`*`号，把list或tuple的元素变成可变参数传进去：
```python
>>> nums = [1, 2, 3]
>>> calc(*nums)
14
```
- `*nums`表示把`nums`这个list的所有元素作为可变参数传进去。这种写法相当有用，而且很常见。

### 12.2.4 关键字参数
可变参数允许你传入0个或任意个参数，这些可变参数在函数调用时自动组装为一个tuple。
而 __关键字参数__ 允许你传入0个或任意个 __含参数名__ 的参数，这些关键字参数在函数内部自动组装为一个 __dict__ 。请看示例：
```python
def person(name, age, **kw):
    print('name:', name, 'age:', age, 'other:', kw)
```
函数`person`除了必选参数`name`和`age`外，还接受关键字参数`kw`。在调用该函数时，可以只传入必选参数：
```
>>> person('Michael', 30)
name: Michael age: 30 other: {}
```
也可以传入任意个数的关键字参数：
```python
>>> person('Bob', 35, city='Beijing')
name: Bob age: 35 other: {'city': 'Beijing'}
>>> person('Adam', 45, gender='M', job='Engineer')
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}
```
- 关键字参数有什么用？它可以扩展函数的功能。
比如，在`person`函数里，我们保证能接收到`name`和`age`这两个参数，但是，如果调用者愿意提供更多的参数，我们也能收到。试想你正在做一个用户注册的功能，除了用户名和年龄是必填项外，其他都是可选项，利用关键字参数来定义这个函数就能满足注册的需求。

和可变参数类似，也可以先组装出一个dict，然后，把该dict转换为关键字参数传进去：
```python
>>> extra = {'city': 'Beijing', 'job': 'Engineer'}
>>> person('Jack', 24, city=extra['city'], job=extra['job'])		# == TBC ==
name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}
```
当然，上面复杂的调用可以用简化的写法：
```python
>>> extra = {'city': 'Beijing', 'job': 'Engineer'}
>>> person('Jack', 24, **extra)
name: Jack age: 24 other: {'city': 'Beijing', 'job': 'Engineer'}
```
-  `**extra`表示把`extra`这个dict的所有key-value用关键字参数传入到函数的`**kw`参数，`kw`将获得一个dict，注意`kw`获得的dict是`extra`的一份拷贝，对`kw`的改动不会影响到函数外的`extra`。

#### 命名关键字参数
对于关键字参数，函数的调用者可以传入任意不受限制的关键字参数。至于到底传入了哪些，就需要在函数内部通过`kw`检查。
仍以`person()`函数为例，我们希望检查是否有`city`和`job`参数：
```python
def person(name, age, **kw):
    if 'city' in kw:
        # 有city参数
        pass
    if 'job' in kw:
        # 有job参数
        pass
    print('name:', name, 'age:', age, 'other:', kw)
```
但是调用者仍可以传入不受限制的关键字参数：
```python
>>> person('Jack', 24, city='Beijing', addr='Chaoyang', zipcode=123456)
```
如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收`city`和`job`作为关键字参数。这种方式定义的函数如下：
```python
def person(name, age, *, city, job):
    print(name, age, city, job)
```
和关键字参数`**kw`不同，命名关键字参数需要一个特殊分隔符`*`，`*`后面的参数被视为命名关键字参数。
调用方式如下：
```python
>>> person('Jack', 24, city='Beijing', job='Engineer')
Jack 24 Beijing Engineer
```
如果函数定义中已经有了一个可变参数，后面跟着的命名关键字参数就不再需要一个特殊分隔符`*`了：
```python
def person(name, age, *args, city, job):
    print(name, age, args, city, job)
```
命名关键字参数必须传入参数名，这和位置参数不同。如果没有传入参数名，调用将报错：
```python
>>> person('Jack', 24, 'Beijing', 'Engineer')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: person() takes 2 positional arguments but 4 were given
```
由于调用时缺少参数名`city`和`job`，Python解释器把这4个参数均视为位置参数，但`person()`函数仅接受2个位置参数。
命名关键字参数可以有缺省值，从而简化调用：
```python
def person(name, age, *, city='Beijing', job):
    print(name, age, city, job)
```
由于命名关键字参数`city`具有默认值，调用时，可不传入`city`参数：
```python
>>> person('Jack', 24, job='Engineer')
Jack 24 Beijing Engineer
```
使用命名关键字参数时，要特别注意，如果没有可变参数，就必须加一个`*`作为特殊分隔符。如果缺少`*`，Python解释器将无法识别位置参数和命名关键字参数：
```python
def person(name, age, city, job):
    # 缺少 *，city和job被视为位置参数
    pass
```
### 12.2.5 参数组合
在Python中定义函数，可以用必选参数、默认参数、可变参数、关键字参数和命名关键字参数，这5种参数都可以组合使用。但是请注意，参数定义的顺序必须是：
- 必选参数、默认参数、可变参数、命名关键字参数和关键字参数。
比如定义一个函数，包含上述若干种参数：
```python
def f1(a, b, c=0, *args, **kw):
    print('a =', a, 'b =', b, 'c =', c, 'args =', args, 'kw =', kw)

def f2(a, b, c=0, *, d, **kw):
    print('a =', a, 'b =', b, 'c =', c, 'd =', d, 'kw =', kw)
```
在函数调用的时候，Python解释器自动按照参数位置和参数名把对应的参数传进去。
```python
>>> f1(1, 2)
a = 1 b = 2 c = 0 args = () kw = {}
>>> f1(1, 2, c=3)
a = 1 b = 2 c = 3 args = () kw = {}
>>> f1(1, 2, 3, 'a', 'b')
a = 1 b = 2 c = 3 args = ('a', 'b') kw = {}
>>> f1(1, 2, 3, 'a', 'b', x=99)
a = 1 b = 2 c = 3 args = ('a', 'b') kw = {'x': 99}
>>> f2(1, 2, d=99, ext=None)
a = 1 b = 2 c = 0 d = 99 kw = {'ext': None}
```
最神奇的是通过一个tuple和dict，你也可以调用上述函数：


















```python
# 自定义取绝对值函数
def aabs(x):
  if x >= 0:
    return x
  else:
    return -x
```
- 参数个数不对，Python解释器会自动检查出来，并抛出`TypeError`
> TypeError: abs() takes exactly one argument (2 given)
> TypeError: aabs() takes exactly 1 argument (2 given)
- 但是解析器不会检查参数类型，如果参数类型不对的时候，会出现不同的情况
```python
> abs('A')
> TypeError: bad operand type for abs(): 'str'
> aabs('A')
> 'A'		# python 2.x可以通过
```


## 11.3 import调用
- import MODULE
- import MODULE1, MODULE2, ...
```python
> import math
> math.pi
```
- from MODULE import <method> /<方法>
```python
> from math import pi
> pi
```
- import MODULE as short-name
- from file_name import function
> file_name.py定义了函数function
> file2.py调用：from file_name import function

- 空函数和pass语句
```python
> def nop():
    pass
```
`pass`可以用来作为占位符，比如现在还没想好怎么写函数的代码，就可以先放一个`pass`，让代码能运行起来。

- 函数嵌套
- ==内定函数locals(), return sum, locals() ??==
- 变量作用域：LEGB (Local, EEEEE, GLobal, Buildin:本地，嵌套，全局，内置)

- 装饰器@
- 
## 11.4 返回多个值
```python
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny
```
```python
>>> x, y = move(100, 100, 60, math.pi / 6)
>>> print(x, y)
151.96152422706632 70.0
```
但其实这只是一种假象，Python函数返回的仍然是单一值：
```
>>> r = move(100, 100, 60, math.pi / 6)
>>> print(r)
(151.96152422706632, 70.0)
```
原来返回值是一个tuple！但是，在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。

==ax^2^ + bx + c = 0 练习==


# OOP


# GUI
> Tkinter on python 2.x
> tkinter on python 3.x

> import Tkinter
> Tkinter._test()


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
eyJoaXN0b3J5IjpbODg0MTExMTc4LDg1Mjg2MzM4OCwxMDQxMD
U3NTQ4LC0xNTM4ODczMzgyLDIzODIzODAyMCwtMjY2MjMyODQ4
LC03MDExNDI0NTQsLTkxMjY0NDI5MCwtMTI1Mjk4Mjc3NiwxMD
Q2OTY4OTU1LDE2ODA2OTcwNTcsLTM3MDk4MjA3MywxMjMwMTcy
NzM2LDE1NzUyMzk2ODIsLTkxMzgyMjQyNiwxNjg1MTA4MTgzLC
00MTg1NTIzNyw5NTY4Njg3OCwxNTMzODU5MDU3LDIwNzc5MDkz
NjNdfQ==
-->