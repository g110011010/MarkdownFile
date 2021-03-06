---
title: 2017-10-16未命名文件 
tags: 新建,模板,小书匠
grammar_cjkRuby: true
Teacher info:
name:
email:
tel:
---


欢迎使用 **{小书匠}(xiaoshujiang)编辑器**，您可以通过==设置==里的修改模板来改变新建文章的内容。


## 第七章 映像和集合类型
### 7.1 映像类型：字典
1. 字典是Python语言中唯一的映射类型。映射对象里哈希值（键，key）和指向的对象（值，value）是一对多的关系。
2. 一个字典类型是可变的，它是一个容器类型，能够容纳任意个数的Python对象，其中也包括其他容器类型。
3. 字典类型和序列类型容器类的区别是存储和访问数据的方式不同。序列类型只能使用数值类型的键。映射类型可以使用其他对象类型做键，一般最常见的是使用字符串做键。
#### 7.1.1 创建字典并给字典赋值

``` python
>>> #创建字典
>>> a={}
>>> b={'hello':'world',a:'a dic'}

Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    b={'hello':'world',a:'a dic'}
TypeError: unhashable type: 'dict'
>>> b={'hello':'world','num':123}
>>> a
{}
>>> b
{'num': 123, 'hello': 'world'}
>>> a,b
({}, {'num': 123, 'hello': 'world'})
>>> #使用工厂方法dict()来创建字典
>>> c=dict((['x',1],['y',2]))
>>> c
{'y': 2, 'x': 1}
>>> #使用内建方法fromkeys()来创建一个默认的字典，字典中的元素具有相同的值（如果没有给出，默认为none）
>>> d={}.fromkeys(('x','y','z'),123)
>>> d
{'y': 123, 'x': 123, 'z': 123}
>>> e={}.fromkeys(('m','n'))
>>> e
{'m': None, 'n': None}
>>> 
enter code here
```
>* 不能使用字典对象作为key
>* 可以使用dict()和fromkeys()方法来创建字典

#### 7.1.2 访问字典中的值
1. 循环访问字典中的所有的值
``` python
>>> b
{'num': 123, 'hello': 'world'}
>>> for keys in b:
	print 'key=%s,value=%s' % (keys,b[keys])

	
key=num,value=123
key=hello,value=world
>>> for key in b.keys():
	print 'key=%s,value=%s' % (keys,b[keys])

	
key=hello,value=world
key=hello,value=world
>>> 
enter code here
```
2. 根据键获取某个确定的值

``` python
>>> b['num']
123
>>> b['nu']

Traceback (most recent call last):
  File "<pyshell#26>", line 1, in <module>
    b['nu']
KeyError: 'nu'
>>> 
```
3. 确定字典中是否存在某个键

``` python
>>> 'num' in b
True
>>> 'n' not in b
True
>>> b.has_key('num')
True
>>> 
```
#### 7.1.3 更新和添加字典元素

``` python
>>> b
{'num': 123, 'hello': 'world'}
>>> b['num']='hello'#更新
>>> b
{'num': 'hello', 'hello': 'world'}
>>> b['n']='append'#添加
>>> b
{'num': 'hello', 'hello': 'world', 'n': 'append'}
>>> 
```
#### 7.1.4 删除字典元素和字典

``` python
>>> b
{'num': 'hello', 'hello': 'world', 'n': 'append'}
>>> del b['num']
>>> b
{'hello': 'world', 'n': 'append'}
>>> del b
>>> b

Traceback (most recent call last):
  File "<pyshell#38>", line 1, in <module>
    b
NameError: name 'b' is not defined
>>> 
```



### 7.2 映射类型操作符
#### 7.2.1 标准类型操作符
1. 字典类型支持比较操作
#### 7.2.2 映射类型操作符
1. **字典的键查找操作符**:`[]`
2. (键)成员关系操作（in,not in）
### 7.3 映射类型的内建函数和工厂函数
#### 7.3.1 标准类型函数[type()、str()\cmp()]
1. cmp() 方法比较字典的方式：首先比较字典的大小，然后是键，然后是值
#### 7.3.2 映射类型相关的函数
1. dict():工厂函数被用来创建字典。如果不提供参数，会创建空字典

``` python
>>> x=dict()
>>> x
{}
>>> type(x)
<type 'dict'>
>>> x=dict([('xy'[i-1],i) for i in range(2,4)])

Traceback (most recent call last):
  File "<pyshell#3>", line 1, in <module>
    x=dict([('xy'[i-1],i) for i in range(2,4)])
IndexError: string index out of range
>>> y=dict([('xy'[i-1],i) for i in range(1,3)])
>>> y
{'y': 2, 'x': 1}
>>> z=dict(a=2,b=3)
>>> z
{'a': 2, 'b': 3}
>>> m=dict(z)
>>> m
{'a': 2, 'b': 3}
>>> n=dict(**z)
>>> n
{'a': 2, 'b': 3}
>>> f=z.copy()
>>> f
{'a': 2, 'b': 3}
>>> #z.copy()方法比dict(z)的效率更高
>>> 
```
2. hash():内建函数hash本来不是为字典设计的方法，但是它可以判断某个方法是否适合用来做一个字典的键。只有一个对象是可哈希的，才可以作为字典的键（函数的返回值是整形，不产生错误或异常）


### 7.4 映射类型内建方法
方法名称|操作
--|---|--
dict.clear()|删除字典中的所有元素
dict clear()|返回字典（浅复制）的一个副本（不知道怎么用）
dict.fromkeys()|创建并返回一个新字典，以seq作为该字典的键，val作为该字典中所有键对应的初始值，如果没有提供初始值，则默认为none
dict.get(key,default=None)|对字典中的键key，返回它的对应的值value，如果字典中不存在此键，则返回default值，默认为None
dict.has_key(key)|如果键在字典中存在，返回true，否则返回false。现在已经被in和not  in 替代
dict.items()|返回一个列表中键值对元组的列表
dict.iter*()|方法iteritems(),iterkeys(),itervalues(),与他们的对应的非迭代方法一样，不同的是他们返回一个迭代子，而不是一个列表
dict.pop(key[,default])|和方法get() 相似，如果字典中key键存在，删除并返回dict[key]:如果key键不存在。返回default，没定义default时报错
dict.setdefault()|和方法set()相似，如果字典中不存在key键，由dict[key]=default为它赋值
dict.update(dict2)|将字典dict2中的值添加到字典dict中
dict.values()|返回一个包含字符中所有值的列表



``` python,get()
>>> a
{1: [4, 5, 6], 2: [4, 5, 6], 3: [4, 5, 6]}
>>> a.get(1)
[4, 5, 6]
>>> a.get(5)
>>> a.get(6,"no this key")
'no this key'
>>> 
enter code here
```


----------

``` python,has_key(),items()
>>> a.has_key(12)
False
>>> 12 in a
False
>>> a.items
<built-in method items of dict object at 0x0000000003EF1E18>
>>> b=a.items()
>>> b
[(1, [4, 5, 6]), (2, [4, 5, 6]), (3, [4, 5, 6])]
>>> type(b)
<type 'list'>
>>> 
```


----------

``` python,iter*()
>>> b=a.itervalues()
>>> b
<dictionary-valueiterator object at 0x0000000003FC15E8>
>>> type(b)
<type 'dictionary-valueiterator'>
>>> c=a.iterkeys()
>>> c
<dictionary-keyiterator object at 0x0000000003FC1638>
>>> type(c)
<type 'dictionary-keyiterator'>
>>> d=a.iteritems()
>>> d
<dictionary-itemiterator object at 0x0000000003FC1688>
>>> type(d)
<type 'dictionary-itemiterator'>
>>> 
```


----------

``` python
>>> d=a.pop(1)
>>> d
[4, 5, 6]
>>> a
{2: [4, 5, 6], 3: [4, 5, 6]}
>>> d=a.pop(4)

Traceback (most recent call last):
  File "<pyshell#57>", line 1, in <module>
    d=a.pop(4)
KeyError: 4
>>> d=a.pop(5,'no thiskey')
>>> d
'no thiskey'
>>> 
enter code here
```


### 7.5 字典的键
1. 不允许一个键对应多个值
2. 键必须是可哈希的
3. hashable(可哈希性)：An object is hashable if it has a hash value which never changes during its lifetime (it needs a __hash__() method), and can be compared to other objects (it needs an __eq__() or __cmp__() method). Hashable objects which compare equal must have the same hash value.

    (如果一个对象是可哈希的,那么在它的生存期内必须不可变(需要一个哈希函数),而且可以和其他对象比较(需要比较方法).比较值相同的对象一定有相同的哈希值)

翻译的比较生硬...简单的说就是生存期内可变的对象不可以哈希,就是说改变时候其id()是不变的.基本就是说列表,字典,集合了.
### 7.6 集合类型
### 7.7 集合类型操作符
### 7.8 内建函数
### 7.9 集合类型内建函数
### 7.10 集合类型总结表
### 7.11 相关模块
### 7.12 练习
