---
title: 2017-10-17未命名文件 
tags: 新建,模板,小书匠
grammar_cjkRuby: true
Teacher info:
name:
email:
tel:
---


欢迎使用 **{小书匠}(xiaoshujiang)编辑器**，您可以通过==设置==里的修改模板来改变新建文章的内容。

序列类型|创建|赋值|更新|访问|删除成员|删除集合
--|---|---|---|---|---|---|--
集合|`s=set('hello')`<br>`t=frozenset(''hello)`|同创建|`s.add('z')`<br>`s.update('pipe)`<br>`s.remove('h')`<br>`s-=set('llo')`|`'k' in s`<br>`for i in s:print i`|见更新|`del s`

### 7.7 集合类型操作符
1. in，not in
2. 子集/超集
3. 联合（|），交集（&），差集（-），对称差分（^）

``` python
Python 2.7.14 (v2.7.14:84471935ed, Sep 16 2017, 20:25:58) [MSC v.1500 64 bit (AMD64)] on win32
Type "copyright", "credits" or "license()" for more information.
>>> s=set('hello world')
>>> s
set([' ', 'e', 'd', 'h', 'l', 'o', 'r', 'w'])
>>> len(s)
8
>>> s.add('!')
>>> s
set(['!', ' ', 'e', 'd', 'h', 'l', 'o', 'r', 'w'])
>>> s.add('!!')
>>> s
set(['!', ' ', 'e', 'd', 'h', 'l', 'o', 'r', 'w', '!!'])
>>> s.update('!!!')
>>> s
set(['!', ' ', 'e', 'd', 'h', 'l', 'o', 'r', 'w', '!!'])
>>> s.update('test')
>>> s
set(['!', ' ', 'e', 'd', 'h', 'l', 'o', 's', 'r', 't', 'w', '!!'])
>>> 'd' in s
True
>>> s|'abcdefg'

Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    s|'abcdefg'
TypeError: unsupported operand type(s) for |: 'set' and 'str'
>>> s|set('abcdefg')
set(['!', ' ', 'c', 'b', 'e', 'd', 'g', 'f', 'h', 'a', 'l', 'o', 's', 'r', 't', 'w', '!!'])
>>> s&set('hello!!!)
      
SyntaxError: EOL while scanning string literal
>>> s&set('hello!!!')
set(['!', 'h', 'e', 'l', 'o'])
>>> s-set('hello!!!')
set(['!!', ' ', 'd', 's', 'r', 't', 'w'])
>>> 
enter code here
```
