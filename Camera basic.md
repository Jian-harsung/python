
> # Python record in Windows
> Jian@Harman

# 1 Installation
** python, pip, virtualenv, ipython **
## 1.1 Windows
### 1.1.1 python
download python from python.org, and pip was installed as default
python website[www.python.org]

### 1.1.2 pip
#pip install virtualenv						# 安装最新版本
#pip install virtualenv==version		# 指定安装版本
#pip list
#pip freeze

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

(envp) #%save    # how to use

### 1.1.4 ipython
to be updated

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

python源文件开头
#!/usr/bin/env python

# 2 常用命令, 函数和包
 ## 2.1 命令
 - type(对象)		# 查看对象类型
 - dir(类型或者对象)		# dir(list)或dir(l1) 列出所有属性和方法
 - help(???)						# help(list.count)或help(l1.count) 查看方法帮助文档
 - s.format()			# 简单格式化输出
 - %							# 定制格式化输出
 

## 2.2 函数
函数名称|解释|how to
-|-|-
int(100)|强制转换100|
chr(num)	| 把数字转换为字符 | #chr(100)
ord(char)	| 把字符转换为数字 | #ord('A')
len(对象)	| 求对象的长度 | #len(s1) / #len(l1)
id() | 查看对象的指针 | #id(s1) / #id(l1)

 ## 2.3 包
**numpy** : 科学计算
**pandas**：
**scipy**：
**matplotlib**：

- import MODULE
- import MODULE as short-name
- import function 

## 2.4 常用数据传输格式
- JSON： 网络传输
- csv：报表
- XML：多用于传输过程中
- 
# 3 术语中英对照
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
- 

# 4 string
## 4.1 Definition
s = "Hello world"
- sample code: #print("hello world")或#print(s)
- Windows下路径反转，可以在string前加上**r**
- #print(r"C:\Users\jikang\envp\Scripts>")
- 单行注释以 **#** 开头
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

## 4.2 method
method | description | how to | output
-----|----|----|---
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
t = (1, 2,3,4,5,6)
- #type(t)  -> tuple
- #len(t) -> 6
- #dir(t)  -> count, index

## 7.2 method
method | description | how to | output
-|-|-|-
count|
index|



# IDE, Tools, Books, Websites, etc....
## IDE
pycharm
Atom
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MjEyMDc5MDRdfQ==
-->