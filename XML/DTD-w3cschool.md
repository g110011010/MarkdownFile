---
title: 2017-10-25未命名文件 
tags: 新建,模板,小书匠
grammar_cjkRuby: true
Teacher info:
name:
email:
tel:
---


欢迎使用 **{小书匠}(xiaoshujiang)编辑器**，您可以通过==设置==里的修改模板来改变新建文章的内容。
> DTD(文档类型定义)的作用是定义XML文档的合法构建模块。它使用一系列的合法元素来定义文档结构。

## DTD 简介
1. 文档类型定义（DTD）可以定义合法的XML文档构建模块。它使用一系列合法的元素来定义文档的结构。
2. DTD可以被成行的定义于XML文档中，也可以作为一个外部引用。
3. 内部的DOCTYPE声明：假如DTD被包含于您的XML源文件中，它应该通过下面的语法被包装在一个DOCTYPE声明中：`<!DOCTYPE 根元素 [元素声明]>`

``` xml
<?xml version="1.0">
<!DOCTYPE note [<!--定义此文档是note类型文档-->
	<!ELEMENT note (to,from,heading,body)><!--定义note有四个元素-->
	<!ELEMENT to (#PCDATA)><!--定义to元素为#PCDATA类型-->
	<!ELEMENT from (#PCDATA)>
	<!ELEMENT heading (#PCDATA)>
	<!ELEMENT body (#PCDATA)>
]>
<note>
	<to>George</to>
	<from>John</from>
	<heading>Reminder</heading>
	<body>Don't forget the meeting!</body>
</note>
```
4. 外部文档声明：假如DTD位于XML源文件的外部，那么它应该通过下面的语法被封装在一个DOCTYPE定义中`<!DOCTYPE 根元素 SYSTEM "文件名（note.dtd）">`
5. 为什么使用DTD：
	* 通过DTD每一个XML文件均可携带一个有关其自身格式的描述
	* 通过DTD，独立的团队可以一致的使用某个标准的DTD来交换数据
	* 个人的应用程序可以使用DTD来验证从外部接收到的数据。
	* 可以使用DTD来验证自身的数据。

## DTD-XML构建模块
1. XML以及HTML文档的主要构建模块是类似`<body>...</body>`这样的标签。
### XML文档构建模块
> 所有的XML文档以及HTML文档均有一下简单的构建模块构成：

1. 元素：元素是XML以及HTML文档的主要构建模块
2. 属性：可以提供有关元素的额外信息
3. 实体：是用来定义普通文本的变量。实体引用是对实体的引用
4. PCDATA（parsed character data）：意思是被解析的字符数据。可以把字符数据相像成开始标签与结束标签之间的文本。
	> PCDATA是会被解析器解析的文本。这些文本将被解析器检查实体以及标记。文本中的标签会被当做标记来处理，而实体会被展开。
5. CDATA（character data）：是字符数据。CDATA是不会被解析器解析的文本。在这些文本中标签不会被当做标签对待，其中的实体也不会被展开。

## DTD-元素
1. 在一个DTD中，元素通过元素声明来进行声明。
2. 声明一个元素：

``` xml
<!ELEMENT 元素名称 类别>
<!ELEMENT 元素名称 (元素内容)>
```
3. 元素及标示

元素|描述|声明关键字|形式
--|---|---|--
空元素|空元素通过类别关键词EMPTY进行声明|EMPTY|`<!ELEMENT 元素名称 EMPTY>`
只有PCDATA的元素|通过圆括号中的#PCDATA进行声明|(#PCDATA)|`<!ELEMENT 元素名称 (#PCDATA)`
带有任何内容的元素|通过类别关键词ANY声明|ANY|`<!ELEMENT 元素名称 ANY>`
带有子元素(序列)的元素|带有一个或多个子元素的元素通过圆括号中的子元素名进行声明|(子元素1,子元素2...),当子元素按照由逗号分开的序列进行声明时,这些子元素必须按照相同的顺序出现在文档中|`<!ELEMENT 元素名称 (子元素名称1,子元素名称2,...)>`
4. 声明出现限定次数的元素

``` xml
<!--出现一次-->
<!ELEMENT note (message)>
<!--至少出现一次-->
<!ELEMENT note (message+)>

<!--出现零次或多次-->
<!ELEMENT note (message*)>

<!--出现一次或零次-->
<!ELEMENT note (message?)>
<!--note元素必须包含to from header子元素,包含message和body元素中的一个-->
<!ELEMENT note (to,from,header,(message|body))>
<!--声明混合型内容:"note" 元素可包含出现零次或多次的 PCDATA、"to"、"from"、"header" 或者 "message"。-->


<!ELEMENT note (#PCDATA|to|from|header|message)*>

``` xml
<!ELEMENT br EMPTY>
```
XML例子:

``` xml
<br/>
```


## DTD-属性
1. 在DTD中,属性通过ATTLIST声明来进行声明 
2. 声明属性使用下列语法:`<!ATTLIST 元素名称 属性名称 属性类型 默认值>`

