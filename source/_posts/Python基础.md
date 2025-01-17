---
title: Python基础
date: 2017-08-30 08:40:36
tags: Note
categories: Python
---

# Python基础

>Python是一种解释型、面向对象、动态数据类型的高级程序设计语言。目前，Python已经成为最受欢迎的语言之一。人生苦短，我用Python。

<!--more-->

基本语法规则

* 以#开头的语句时注释
* 当语句以:号结尾时，缩进的语句视为代码块
* 缩进按照约定俗成的管理为4个空格
* Python时大小写敏感的

## 数据类型和变量

1. 整型：在程序中和数学上的写法一致，当使用十六进制表示整数时，用*0x*前缀和0～9，a～f表示

2. 浮点数：浮点数也就是小数，对于很大或很小的浮点数，使用科学计数法表示，把10用e替代，1.23*e9表示1.23乘以10的九次方，0.000012可以写成1.2e-5

3. 字符串：字符串以'或"括起来的任意文本，''或""本身是一种表示方式，不是字符串的一部分，如果'或"也是字符的一部分，可以用""或''括起来，若内部包含'和"，可以用\\来表示，如果字符串有很多字符都需要转义，可以使用r''...''表示内部的字符默认不转义，如果字符串内部有很多换行，可以使用'''...'''表示多行内容（\n表示换行，\t表示制表符，\\\\表示\）

4. 布尔值：布尔值只有True和False两种值（注意大小写），布尔值也可以用and、or和not运算
5. 空值：空值是Python里的一个特殊的值，用None表示。None不能理解为0，因为0是有意义的，而None是一个特殊的空值

6. 变量：变量在程序中用一个变量名表示，变量名必须是大小写英文、数字和_的组合，且不能用数字开头，在Python中，可以把热议数据类型赋值个变量，同一个变量可以反复赋值，而且可以是不同类型的变量。这种变量类型不固定的语言称之为动态语言

7. 常量：所谓常量就是不能变的变量，用全部大写的变量名表示出常量只是一个习惯上的用法。在Python中有两种除法，一种除法是/，/除法计算结果是浮点数，即使是两个整数恰好相除，结果也是浮点数，还有一种除法是//，称为地板除，两个整数的除法仍然是整数：

```python
>>> 10 / 3
3.333333333333

>>> 6 / 3
3.0

>>> 10 // 3
3
```

## 字符串和编码

### 字符编码

因为计算机只能处理数字，如果要处理文本，需要先把文本转化为数字才能处理。中国汉字编码`GB2312`。
Python中默认的编码模式是ASCII格式，需要在Python文件开头加入
`# -*- coding: UTF-8 -*-`或`#coding=utf-8`即可

### Python字符串

1. 在Python中，字符串是以Unicode编码的，对于单个字符的编码Python提供了ord()函数获取字符的整数表示，char()函数把编码转换为对应的字符

    ```python
    >>>ord('A')
    65
    >>>chr(26460)
    '杜'
    ```

    十六进制

    ```python
    >>>'\u4e2d\u6587'
    '中文'
    ```

2. 由于Python的字符串类型是str，在内存中以Unicode表示，一个字符对应若干个字节。如果要在网络上传输，或者保存到磁盘上，就需要把str变为以字节为单位的bytes。'ABC'是字符串

    ```python
    >>>x = b'ABC'
    >>>y = 'ABC'
    >>>print(x == y)
    False
    ```

3. 以Unicode表示的str通过encode()方法可以编码为指定的bytes，例如：

    ```python
    >>> '中文'.encode('utf-8')
    b'\xe4\xb8\xad\xe6\x96\x87'
    ```

4. 纯英文的str可以用ASCII编码为bytes，内容是一样的，含有中文的str可以用UTF-8编码为bytes。含有中文的str无法用ASCII编码，因为中文编码的范围超过了ASCII编码的范围，Python会报错。

    反过来，如果我们从网络或磁盘上读取了字节流，那么读到的数据就是bytes。要把bytes变为str，就需要用decode()方法：

    ```python
    >>> b'ABC'.decode('ascii')
    'ABC'
    >>> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
    '中文'
    ```

5. len()函数可以用来要计算str包含的字符数也可以计算bytes的字节数

    ```python
    >>>len('ABC')
    3
    >>>len('中文')
    2
    >>>len(b'ABC')
    3
    >>>len('中文'.encode('utf-8'))
    ```

    1个中文字符经过UTF-8编码后通常会占用3个字节，而1个英文字符只占用1个字节。

    ```python
    #!/usr/bin/env python3 #linux/OS X系统下为可执行程序
    # -*- coding: utf-8 -*- #按UTF-8读取源代码
    ```

6. 格式化

    在Python中格式化的方式和C一样使用%输出格式化字符
    %运算符就是用来格式化字符串的。在字符串内部，%s表示用字符串替换，%f表示用浮点数替换，%x表示用十六进制替换，%d表示用整数替换，有几个%?占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个%?，括号可以省略。

    ```python
    #!/usr/bin/env python3
    # -*- coding: utf-8 -*-
    s1 = int(input('去年的成绩：'))
    s2 = int(input('今年的成绩：'))
    r = (s2 - s1) / s1 * 100
    if s1 > s2:
        print('下降了：''%.1f %%' % r)
    else:
        print('提升了：''%.1f %%' % r)
    ```

## 使用list和tuple

### list

Python内置的一种数据类型是列表：list。list是一种有序的集合，可以随时添加和删除其中的元素。索引从0开始，超出列表长度时会报错，最后一个元素的索引是len(list)-1，还以用len[-1]直接获取最后一个元素，list中元素类型可以不同。

```python
>>>len(list)      #可以获得list列表的长度
>>>list.appen()   #追加元素到list的末尾
>>>list.insert(i) #插入元素到指定位置
>>>list.pop(i)    #删除末尾的元素，用pop()，使用pop(i)删除指定位置的元素
                  #若要替换元素，则直接赋值给对应的索引位置
>>> list = []
>>> len(list)
0
```

### tuple

另一种有序列表叫元组：tuple。tuple和list非常类似，但是tuple一旦初始化就不能修改。
定义tuple时，tuple的元素必须被确定下来

```python
>>>t = (1,2)
>>>t
(1,2)
>>>t = ()
>>>t
()
>>>t = (1,)
>>>t
(1,)
```

若tuple中包含list，则该tuple中的list元素可变，tuple所谓的“不变”是说，tuple的每个元素，指向永远不变。即指向'a'，就不能改成指向'b'，指向一个list，就不能改成指向其他对象，但指向的这个list本身是可变的！

## 条件判断

```python
#if语句的完整形式
if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
    <执行3>
else:
    <执行4>

if x:
    print("True") #只要x是非零数值、非空字符串、非空list等，就判断为True，否则为False
```

## 循环

1. for循环


    for x in ...循环就是把每个元素代入变量x，然后执行缩进块的语句。
    range()函数可以生成一个整数序列，通过list()函数装换为list。

    ```python
    list(range(5))
    [0,1,2,3,4,]
    ```

2. while循环

    while循环，只要条件满足，就不断循环，条件不满足时退出循环。

    ```python
    while ...  #条件
        ...    #条件满足时执行
    print()    #条件不满足执行
    ```

3. break和continue

    在循环中，在满足break语句前的if语句条件时执行，可以提前退出循环。
    continue的作用是提前结束本轮循环，不会执行满足if条件时的语句，直接开始下一轮循环。
    *注意*：不要滥用break和continue语句。break和continue会造成代码执行逻辑分叉过多，容易出错。大多数循环并不需要用到break和continue语句，上面的两个例子，都可以通过改写循环条件或者修改循环逻辑，去掉break和continue语句。

## 使用dict和set

### dict

dict在其他语言中也称为map，使用键-值存储，具有极快的查找速度，一个key只能对应一个value，多次对一个key放入value，后面的值会把前面的值替换掉。若key不存在，则dict报错，可以通过in或get方法判断key是否存在。dict的key必须是*不可变对象*。

```python
>>>'abc' in s
False
>>>d.get('abc')
>>>d.get('abc',x)
x
```

可以通过pop(key)方法删除对应的key，dict内部存放的顺序和key放入的顺序无关。
list相比，dict特点：

1. 查找和插入的速度快，不会是UI这key的增加而增加
2. 占用大量内存，浪费内存

list相反：

1. 查找和插入的时间随着元素的增加而增加
2. 占用空间小，浪费内存少

### set

set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，*没有重复*的key。
注意：传入的参数[1, 2, 3]是一个list，而显示的{1, 2, 3}只是告诉你这个set内部有1，2，3这3个元素，显示的顺序也不表示set是有序的。
要创建一个set，需要提供一个list作为输入集合：

```python
>>>s = set([1,2,3])
>>>s
{1,2,3}
>>>x = set([1,1,2,2,3,3])
>>>x
{1,2,3}
>>>s.add(4)
>>>s
{1,2,3,4}
>>>x.remove(3)
>>>x
{1,2}
#set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集、并集等
>>>s & x
{1,2}
>>>s | x
{1,2,3,4}
```

# 函数

>函数是最基本的一种代码抽象的方式

## 调用函数

[官方文档](http://docs.python.org/3/library/functions.html)

要调用函数首先要知道函数的名称和参数。

```python
abs(100)
100
abs(-100)
100
```

若传参个数或类型错误，都会报TypeError错误

## 数据类型转换

Python内指定额常用函数还包括数据类型转寒函数

```python
>>> int('123')
123
>>> int(12.34)
12
>>> float('12.34')
12.34
>>> str(1.23)
'1.23'
>>> str(100)
'100'
>>> bool(1)
True
>>> bool('')
False
```

函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”：

```python
>>> a = abs # 变量a指向abs函数
>>> a(-1) # 所以也可以通过a调用abs函数
1
```

## 定义函数

在Python中，定义一个函数使用def语句
def name(args):
    return 执行语句
若没有return语句，则返回None。return None == return
`from x import y`用来导入x.py文件中定义的y函数。

### 空函数

```python
dep nop():
    pass

if age >= 18
    pass
```

pass语句什么也不做，但是可以用来作为占位符

### 参数检查

内置函数会检查出参数错误，而我们定义的函数没有参数检查，两种同样的错误就会导致语句中出错的原因不同。可以用isinstance()做参数数据类型检查。

```python
def people(name,age):
    if not isinstance(name,(str)):
        raise TypeError('bad operand type')
    return print(name,age)
```

### 返回多个值

```python
import math

def move(x, y, step, angle=0):
    nx = x + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny

>>> x, y = move(100, 100, 60, math.pi / 6)
>>> print(x, y)
151.96152422706632 70.0
#返回值放在一个tuple中

>>> r = move(100, 100, 60, math.pi / 6)
>>> print(r)
(151.96152422706632, 70.0)
```

### 函数的参数

1. 位置参数

```python
dep power(x):
    return x * x
```

对于power(x)函数，参数x就是一个位置参数。
当调用power函数时，必须传入有且仅有的一个参数x

### 递归函数

参考教程：
[Python教程,廖雪峰的官方网站](https://www.liaoxuefeng.com/wiki/0014316089557264a6b348958f449949df42a6d3a2e542c000)
