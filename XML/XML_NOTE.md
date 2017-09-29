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
4. XML使用DTD(Document Type Definition)或者XML schema来描述数据
5. 带有DTD或者XML schema的XML是能够进行自我描述的
6. XML是由W3C公司设计的
7. 具有可扩展性

	* 可以被用于文本或者消息
	* 不像HTML,可以定义新的标签
8. 是国家化的:基于Unicode编码

> **关于Unicode**
> 1. 中文编码:GB2312(GB 国标)
> 2. 中文繁体编码:Big5
> 3. 日本编码:shift-gis
> 4. ISO8859:ASCII:0~127,扩展后增加了128~255
> 5. .......
> 为了解决各国自行编码的乱像,国际协议上制定了UCS2(Unicode Character Set 2^6)后来又制定了UCS4
> 6. CJK(Chinese Japanese Karen)编码
> 7. 英文占世界信息保有量的百分之九十
> 8. UTF-8( Unicode transform )目的是解决用最小的内存完成所有编码,对不同类型的语言编码使用不同的编码格式进行编码,一次增加8位,比如英文使用8位就够,而中文是不够的,utf-8就增加一个8位来完成这个语言的所有编码,不够的话就再增加8位,以此类推
> 9. UTF-16:工作原理与UTF-