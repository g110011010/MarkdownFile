---
title: 2017-9-29 
tags: 
author:sf
grammar_cjkRuby: true
---
# Course 1
## Why XML?
### 因特网危机:信息交互

	1. 在互相不理解的情况下进行连接
	2. 第一步是设定元数据标准
			* 元数据:关于数据的数据,用于描述规则或者定义其它数据的数据,数据库规划和XML架构都有元数据描述
	3. 上下文语言共享,多语言支持;内容管理系统
	4. 国际化问题:一套软件在不同语言的操作系统上能够正常运行.
		* globalization(g11n)国际化
		* localization(l10n)本地化

### XML& WEB
1. WEB发展的三个阶段:

	*  World Wide Web(Web 1.0)
	*  Social Web(Web 2.0:SNS) 社会关系网,大部分使用XML文件进行管理
	*  Semantie Web(Web 3.0) 语义网 ,具有一定的按照规则进行推理功能,规则是由XML表达出来的
		*  Web services
		*  Web Science

## How XML?
 1. 计算机中的两中文件类型

	* 二进制文件
	* 文本文件 

### What's XML?
1. XML stands for EXtensible Markup Language
1. XML是用来描述数据的
2. XML是一个像HTML语言一样的标签化语言
3. 你可以在XML中定义自己的标签
4. XML使用DTD(Document Type Definition)或者XML schema(XSD)来描述数据
5. DTD最大的优点是简练,缺点是它自己有自己独特的语法
6. XSD是DTD的替代品.XSD的优点:可以根据将来的条件扩展数据模型;比DTD丰富和有用;本身使用XML书写,没有专门的语法;支持一系列数据类型(今int,float,boolean,date);支持命名空间;支持属性组.缺点:文档篇幅较大,有效载荷低..XSD的后缀名是.xsd
5. 带有DTD或者XML schema的XML是能够进行自我描述的
6. XML是由W3C公司设计的
7. 具有可扩展性
	* 可以被用于文本或者消息
	* 不像HTML,可以定义新的标签
8. 是国际化的:基于Unicode编码(缺省编码格式为UTF-8)

> **关于Unicode**
> 1. 中文编码:GB2312(GB 国标)
> 2. 中文繁体编码:Big5
> 3. 日本编码:shift-gis
> 4. ISO8859:ASCII:0~127,扩展后增加了128~255
> 5. .......
> 为了解决各国自行编码的乱像,国际协议上制定了UCS2(Unicode Character Set 2^16)后来又制定了UCS4(字符集2^32)
> 6. CJK(Chinese Japanese Karen)编码
> 7. 英文占世界信息保有量的百分之九十
> 8. UTF-8( Unicode transform )目的是解决用最小的内存完成所有编码,对不同类型的语言编码使用不同的编码格式进行编码,一次增加8位,比如英文使用8位就够,.而中文是不够的,utf-8就增加一个8位来完成这个语言的所有编码,不够的话就再增加8位,以此类推
> 9. UTF-16:工作原理与UTF-
> 10. 

## What's Not XML?
1. XML不是一种编程语言
2. XML不是一种网络传输协议
3. XML不是一个数据库
4. XML是用于定义和描述数据结构的语法.我们所全部感兴趣的是数据的机构和如何使用它
## XML与HTML之间的不同
1. XML不是HTML的取代,而是对HTML的补充
2. XML与HTML的设计目的不同:XML主要用于对数据\信息进行描述,而HTML则致力于对信息的展示
3. XML和HTML的使用标准不同:HTML的语法的严格程度远低于XML.
	
	* XML:必须适当嵌套并均衡
		* eg:`<br/>` OK 
		* eg:`<b>bold<i>and italic </i>text</b>` OK

	* HTML:
		* eg:`<b>bold<i>and italic</b>text</i>` BAD IN XML
	*XML:
		*eg:`<img src='images/test.jpg'/>`
	*HTML:
		*eg:`<img src=images/test.jps/>`
	*XML是大小写敏感的	
		
4. XML的解析器是parser,

# Course 2 XML语法

``` xml
<?xml version="1.0" encoding="IOS-8895" standalone="yes" ?><!--1.0版本是针对与阿拉伯语指定的,GB-2312国标简体中文编码,encoding缺省的时候是默认编码UTF-8.standalone表示这个文件是否能够独立存在-->
<note><!--根元素,XML只有一个根元素-->
    <to>Tove</to>
    <from>Jani</from>
    <heading>reminder</heading>
    <body>test</body>
</note>
```
### 根元素
1. 所有的XML文件都必须有而且只有一个根元素

### XML中所有的属性都必须被引号引住
### 在XML中,回车(RF)和换行(LF)统一被转换成换行来理解
1. 在Windows下,换行时系统会自动添加换行符和回车符
2. 在Unix下,只会添加换行符
3. 在Macintosh下,只会添加一个回车符
### XML元素是可扩展的
### 处理指令
### Illegal PCDATA Characters
1. CDATA:字符型数据,不一定要经过解析器解析
2. PCDATA:(代表要经过解析器解析的字符数据) 
3. 有些字符不能够直接放入到XML文档中,eg:`<`和`&`


字符|转义字符
--|---|--
&amd|&
&lt|<
&bt|>

### CADAT Character

``` xml
<example>
	<![CADATA[这个位置的除去"]"之外的所有字符都不会被解析器解析]]>
</example>
enter code here
```
### XML 命名空间
1. XML命名空间保证了命名冲突的避免 ,

### XML命名空间是如何工作的 
### URIs,URLs & URNs
1. URIs:是一种标示资源的字符串,可以有两种表达方式:URL和URN
2. URLs:http://www.baidu.com
3. URNs:eg:urn:foo:a,123,456

4. URIs仅仅是用于给命名空间一个名字,但是其本身并不具有任何含义.

### XML命名协定
1. XML中最重要的命名为元素名字,属性名字和实体名字
2. 名字里面可以包含字母,数字,杠(-),句号(.).
3. 命名不能以XML的任意形式开始(XML123,Xmlasj均不合法

## Course 3 XML DTD
1. DTD的目的:定义一个合法的XML文档块 
2. why use dtd?



### DTD 
1. DTD:是一套指导XML数据文档生成的规则
2. 
## Course 4 XSD
1. XML具有面向对象的特点

## Course 5 
1. `complexContent`:意味着当前复杂类型是在原有的复杂类型的基础上做的扩展。
2. `base`表示继承自其它复杂类型

``` xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
targetNamespace="">
    <xs:element name="persons" >
        <xs:complexType>
        <xs:sequence>
            <xs:element name="person" minOccurs="1" maxOccurs="3">
                <!--拥有属性的元素是复杂类型，应该位于complexType内部-->
                <xs:complexType>
                    <!--属性没有顺序，不应该放置在sequence内部-->
                    <!--<xs:attribute name="hello" type="xs:string"/>--><!--会报错-->
                    <xs:sequence>
                        <xs:element name="full_name" type="xs:string" />
                        <xs:element name="child_name" type="xs:string" minOccurs="0" maxOccurs="5"/>
                    </xs:sequence>
                    <xs:attribute name="id" type="xs:string"/><!--向元素添加一个属性，属性的位置只能是在这个地方，不能出现在sequences前面-->
                </xs:complexType>
            </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```
