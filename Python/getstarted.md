### 标识符
1. Python里，标识符有字母、数字、下划线组成；
2. Python中，所有标识符可以包括英文、数字以及下划线`_`，但不能以数字开头；
3. Python中的标识符是区分大小写的；
4. 以下划线开头的标识符是有特殊意义的。以单下划线开头`_foo`的代表不能直接访问的类属性，
需通过类提供的接口进行访问，不能用`from xxx import *`而导入；
5. 以双下划线开头的`__foo`代表类的私有成员；以双下划线开头和结尾的`__foo__`
代表Python里特殊方法专用的标识，如`__init__()`代表类的构造函数。

### 关键字
<table>
<tbody>
<tr><td>and</td><td>exec</td><td>not</td></tr>
<tr><td>assert</td><td>finally</td><td>or</td></tr>
<tr><td>break</td><td>for</td><td>pass</td></tr>
<tr><td>class</td><td>from</td><td>print</td></tr>
<tr><td>continue</td><td>global</td><td>raise</td></tr>
<tr><td>def</td><td>if</td><td>return</td></tr>
<tr><td>del</td><td>import</td><td>try</td></tr>
<tr><td>elif</td><td>in</td><td>while</td></tr>
<tr><td>else</td><td>is</td><td>with </td></tr>
<tr><td>except</td><td>lambda</td><td>yield</td></tr>
</tbody>
</table>

> 注意：这些保留字不能用作常数或变数，或任何其他标识符名称。所有Python的关键字只包含小写字母。

### 输入输出
`input()`和`print()`是在命令行下面最基本的输入和输出。
```python
>>> name = input()
alpha
>>> name
'alpha'
>>> print(name)
alpha
>>>
```
> `print()`会依次打印每个字符串，遇到逗号`,`会输出一个空格。

#### 其他
* Python 与其他语言最大的区别就是，Python的代码块不使用大括号`{}`来控制类、函数以及其他逻辑判断。python 最具特色的就是用缩进来写模块。
  > 缩进的空白数量是可变的，但是所有代码块语句必须包含相同的缩进空白数量，这个必须严格执行。
      # 错误的缩进
      1 if True:
      2     print "True"
      3 else:
      4   print "False"
  >
      # 执行错误提醒
      File "test.py", line 4
        print "False"
        ^
      IndentationError: unexpected indent
  > 注：建议你在每个缩进层次使用单个制表符或两个空格或四个空格，切记不能混用。

* Python语句中一般以新行作为为语句的结束符。但是我们可以使用斜杠`\`将一行的语句分为多行显示，若语句中包含`[]`,`{}`或`()`括号就不需要使用多行连接符。
```python
>>> total = elem_one + \
... elem_two + \
... elem_three
>>> days = ['Monday', 'Tuesday', 'Wednesday',
... 'Thursday', 'Friday']
>>>
```
* Python 可以使用引号`'`、双引号`"`、三引号`'''或"""`来表示字符串，引号的开始与结束必须的相同类型的。其中三引号可以由多行组成，编写多行文本的快捷语法，常用于文档字符串，在文件的特定地点，被当做注释。
```python
>>> '我是字符'
'我是字符'
>>> "我是字符串"
'我是字符串'
>>> '''我是字符串'''
'我是字符串'
>>> """我是字符串"""
'我是字符串'
>>> '''I am
... a
... good
... boy.
... '''
'I am \na \ngood \nboy.\n'
>>>
```
* python中单行注释采用`#`开头。
```python
#!/usr/bin/env python
# 这是注释
>>> name = "Madisetti" # 这是一个注释
>>> name
'Madisetti'
>>>
```
* 函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。类和函数入口之间也用一行空行分隔，
以突出函数入口的开始。空行与代码缩进不同，空行并不是Python语法的一部分。书写时不插入空行，
Python解释器运行也不会出错。但是空行的作用在于分隔两段不同功能或含义的代码，
便于日后代码的维护或重构。
> ''空行也是程序代码的一部分。''
