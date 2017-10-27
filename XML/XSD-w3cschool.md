---
title: 2017-10-27未命名文件 
tags: 新建,模板,小书匠
grammar_cjkRuby: true
Teacher info:
name:
email:
tel:
---


欢迎使用 **{小书匠}(xiaoshujiang)编辑器**，您可以通过==设置==里的修改模板来改变新建文章的内容。
## XSD 简介
1. XSD相对于DTD的优势：
	* 可以针对未来的需求进行扩展
	* XSD更完善，功能更强大
	* 支持数据类型
	* 支持命名空间

2. XML Scheam是基于XML的DTD的替代者，作用是定义XML的合法构建模块
3. XSD是XML SCheam的扩展名，以后用XSD代指XML Scheam
## 学习XML Scheam的理由
1. XSD支持数据类型：
	* 可以更容易的描述允许的文档内容
	* 可以更容易的验证数据的正确性
	* 可以更容易的与来自数据库的数据一并工作
	* 可以更容易的定义数据约束
	* 可以更容易的定义数据模型
	* 可以更容易的在不同数据类型之间转换数据

2. XML可以保护数据通讯

## 如何使用XSD

## XSD简单元素
1. 简单元素是指只包含文本的元素。它不会包含任何其他元素或者属性
2. 定义简单元素的语法：

``` xml
<xs:element name="xxx" type="yyy"/>
```
3. 上面的yyy是指数据类型，XSD 有很多内置的数据类型：
	* `xs:string`
	* `xs:decimal`
	* `xs:integer`
	* `xs:boolean`
	* `xs:data`
	* `xs:time`

4. 简易元素的默认值和固定值
	* 默认值：`<xs:element name='color' type='xs:string' default='red'>`
	* 固定值：`<xs:element name='color' type='xs:string' fixed='red'>`

## XSD 属性
1. 简易元素无法拥有属性。如果一个元素拥有属性，它就会被当做某种复合类型。但属性本身总是可以被当做简易类型被声明。
2. 定义属性：`<xs:attribute name='xxx' type='yyy'>`
3. 属性的数据类型同上
4. 属性的默认值与固定值的定义方法与简易元素的定义方法相同
5. 属性的可选和必须性定义：缺省情况下，属性是可选的；如需规定属性是必选的，请使用`use`属性。`<xs:attribute name='lang' type='xs:string' use='required'>`
## XSD 限定/Facets
1. 限定（restriction）用于为XML元素或者属性定义可接受的值。
2. 对值进行限定：

``` xml
<xs:element name="age">
<xs:simpleType>
	<xs:restriction base="xs:integer">
		<xs:minInclusive value="0"/>
		<xs:maxInclusive value="140"/>
	</xs:restriction>
</xs:simpleType>
</xs:element>
```
3. 对一组值进行限定：

``` xml
<xs:element name="car">
<xs:simpleType>
	<xs:restriction base="xs:string">
		<xs:enumeration value="Audi"/>
		<xs:enumeration value="Golf"/>
		<xs:enumeration value="BMW"/>
	</xs:restriction>
</xs:simpleType>
</xs:element>
```
上面的也可以这样写，好处是限定规则可以被其他的元素复用。

## XSD复合元素
1. 复合元素是指包含其它元素及/或属性的XML元素。
2. 有四种类型的复合元素（均可包含属性）：
	* 空元素
	* 仅包含其它元素的元素
	* 仅包含文本的元素
	* 包含元素和文本的元素
3. 

