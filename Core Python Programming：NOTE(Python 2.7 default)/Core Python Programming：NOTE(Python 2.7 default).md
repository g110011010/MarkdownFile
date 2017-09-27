## Chapter2
### 2.1
1. 在交互式解释器中，可以使用print var_name 或者直接使用var_name输出变量，后者输出时会用单引号将变量内容括起来。
2. 下划线（_）在解释器中表示最后一个表达式的值。
3. print 语句与字符串操作符（%）结合使用，可以实现字符串替换功能。这一点和C语言中的printf()函数很相似。
4. ![](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329583760.jpg)
###2.2
1. 使用raw_input()内建函数从用户那里获取输入。
2. 对一个函数调用help内建函数即可得到他的帮助文档

###2.3 注释
1.python中注释是以#开头，注释可以在一行的任何地方开始，解释器会忽略该行#之后的任何内容。
2. 有一种叫做文档字符串的特别注释，你可以在模块、类或者函数的起始添加一个字符串，起到在线文档的功能。文档字符串可以在运行时访问，也可以用来生成自动文档。
###2.4 操作符


操作符|描述
--|---|--
+|
-|
*|
/|传统除法，效果与java中类似
//|用作浮点除法（对结果四舍五入）
%|
**|乘方操作符
<|
>|
\>=|
<=|
==|
!=|
<>|不等于，推荐使用前者
###2.5 变量和命名
1. 命名规则：首字符是字母或者下划线，其它字符可以死字母、下划线或者数字。python大小写敏感
2. python是动态类型语言，也就是说不需要预先声明变量类型
3. python不支持自正1和自减1操作符


##内建函数


函数|描述
--|---|--
raw_input()|从用户那里获取输入数据
int（）|将字符串类型数字转化为int类型
float()|将字符串型数字转化为float型
long()|
complex()|
bool()|
###2.6
1. Python支持五种基本数字类型，其中有三种是整型类型


类型|符号|实例
--|----|--
有符号整型|int|1010 84 -123
长整型|long|423235L -5345436 0x23543DECAEE
布尔型|boolean|True False
浮点值|float|23.14159
复数|complex|2.34+4.5j 43.56+23J
2. Python中的长整型大小仅仅受限于计算机中虚拟内存的大小。
3. 布尔值被放入到数字环境当中时，TRUE会被当成整型值1，false会被当成整型值0。
###2.7
1. python中的字符串被定义为引号之间字符的集合可以使用索引操作符（[]）和切片操作符（[:]）来获得子字符串。
2. 字符串有其特定的索引规则，第一个字符串的索引为0，最后一个索引为-1。
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584554.jpg)
###2.8 列表和元组
1. 可以将列表和元组当成是普通的“数组”，但是列表和元组可以存储不同类型
2. 列表元素用[]包裹，元素的个数及元素的值可以改变
3. 元组元素用小括号包裹，不可以更改（尽管他们的内容可以），元组可以看成是只读的列表。，通过切片运算可以得到子集。
###2.9 字典
1. 字典是python中的映射数据类型，工作原理类似于PErl中的关联数组或者哈希表，由键值对构成。几乎所有的python对象类型都可以作为键，一般以数字或者字符串最常用。
2. 字典元素使用大括号包裹。

![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584528.jpg)
###2.10 代码块及缩进对齐
1. 代码块通过缩进对齐表达代码逻辑
###2.11 if语句
```python
if x<.0:
	if_suit
else:
	else_suit
```
1. print语句默认会给每一行添加一个换行符，在语句的最后添加一个逗号可以防止换行
2. range函数
3. len()函数
4. enumrate()函数
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584542.jpg)

### 2.14 列表解析
1. 表示你可以在一行中使用for循环将所有元素放入到一个列表中。
2. 列表解析还能进行挑选合适的元素放入到列表中。![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329586170.jpg)
### 2.15 文件和内建函数open(),file()
1. 打开文件方式：`handle=open(file_name,access_mode='r')`,file_name变量是我们希望打开的字符串的名称，access_mode中‘r’表示读取，‘w’表示写入，‘a’表示添加，‘+’表示读写，‘b’表示二进制访问。默认为‘r’.如果open成功，一个文件对象句柄会被返回。所有后续文件操作都必须通过此文件句柄完成。
2. 属性：属性是与数据有关的项目，属性可以使简单的数据值，也可是可执行对象，比如函数和方法
### 2.17 函数
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584762.jpg)
1. 函数参数可以提供默认值，如果调用函数的时候没有提供参数，函数将以默认值调用。
2. ![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329583707.jpg)
### 2.18 类
1. 定义类：
2. ![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584619.jpg)

> * version是一个静态变量，它将被所有的实例以及四个方法所共享，其中每个实例可以对自己的静态变量重新赋值，赋值结果不会影响到其它的实例。通过类名调用静态变量属性对其进行赋值，效果将会影响到所有的对象。
> * 当一个类实例被创建的时候，__init__()方法会被自动调用，在类实例创建完毕后执行，类似于构造器。__init__（）可以被当做是一个构造器，但是他和其它语言的构造器不同，他并不创建实例，他仅仅是你的对象创建后执行的第一个方法。
> * self 是类实例自身的引用，其它面向对象语言通常使用一个名为this的标识符。
> 

3. 使用类：
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584820.jpg)

### 2.19 模块
1. 模块是一种组织形式，它将彼此有关系的python代码组织到一个个独立文件当中。模块可以包含可执行代码，函数或者类或者这些东西的集合。
2. 当你创建了一个python源文件，模块的名字就是一个不带.py后缀的文件名。可以在一个模块中使用import语句导入另外一个模块来使用。
3. PEP:PEP是python的增强提案（Python Enhancement Proposal），也是在新版本python中增加新特性的方式，它提供了新特性的完整描述，还有添加这些新特性的理由，如果有需要的话，还会提供新的语法，技术实现细节，向后兼容信息等。
### 2.20 实用的函数
函数|描述
--|---|--
dir([obj])|显示对象的属性，如果没有提供参数则显示全局变量的名字
help([obj])|以一种整齐美观的方式，显示对象的文档字符串，如果没有提供任何的参数，将会进入交互式帮助
int（obj）|将一个对象转化为整型
str(obj)|将一个对象转化为字符串
len(obj)|显示对象长度
open(fn,mode)|以某种方式打开一个文件
range([start],stop,[step])|返回一个整型列表，起始值为start（default=0）,终止值为stop,步进值为step。
raw_input(str)|等待用户输入一个字符串，可以提供一个可选参数str作为提示信息
type(obj)|返回对象的类型（返回值本身是一个type对象）

##Chapter 3 Python基础
### 3.1 语法和语句
1. Python 语句中一般使用换行分隔，也就是说，一行一个语句。一行过长的语句可以使用反斜杠分割成几行。
>有两种特殊情况一个语句不使用反斜杠也能跨行书写:
> * 使用闭合操作符,单一语句可以跨多行,例如:在含有小括号,中括号,花括号时可以多行书写.
>  * 三引号包含下的字符串也可以跨行书写.

2. 缩进相同的一组语句构成一个代码快,我们称之为代码组,代码组由不同的缩进分割.
3. 分号允许你在同一行中写多个语句,语句之间用分号分开,而这些语句也不能在这行开始一个新的代码块
4. 每一个python脚本文件都可以被当作是一个模块.模块以磁盘文件的形式存在.
### 3.2 变量赋值
1. Python语言中,等号(=)是主要的赋值操作符(其他的是增量赋值操作符)
2. 赋值并不是直接将一个值赋给一个变量.在Python 中,对象是通过引用传递的.在赋值时,不管对象是新创建的,还是一个已经存在的,都应该将该对象的引用赋值给变量.
3. Python 中赋值语句不会返回值,但是可以链式赋值.
4.  增量赋值:增量赋值通过使用赋值操作符,将数学运算隐藏在赋值过程当中.`+=,-=,*=,/=,&=,**=,<<=,>>=,&=,^=,|=`
5. 多元赋值:采用这种方式赋值的时候,等号两边的元素都是元组.`x,y,z=1,2,'dfs'`
###3.3 标识符
1. 标识符是计算机中允许作为名字的有效字符串集合
2. python中标识符包括保留字和"内建"的标识符集合.这些都是不能够使用的.
3. python用下划线作为变量前缀和后缀指定特殊变量.
>* _XXX 不用'from model import *' 导入
>* _xxx_ 系统定义名字
>* _xxx 类中的私有变量名.
>  建议对于普通的 变量不要使用下划线作为变量名,对于私有的变量,以下划线开头是一个好的编程风格.


4. 代码的缩进量最好是3~7个,一般是四个,并且不建议使用tab键来进行缩进,因为在用不同的编译器打开的时候可能会出现问题.
5. 模块结构和布局:
布局|解释
--|---|--
起始行(Unix)|在类Unix系统下使用,有起始行后可以直接执行脚本,无需调用解释器
模块文档|
模块导入|
变量定义|这里定义的变量为全局变量
类定义|
函数定义|
主程序|无论这个模块是被别的模块导入还是直接执行脚本,这块的代码都会得到执行 

6. 通常只有主程序中有大量的顶级可执行代码,所有其他被导入的模块应该只有很少的顶级执行代码.
7. `__name__`指示模块应该如何被加载,如果模块是被导入,`__name__`的值为模块的名称,如果模块是被直接执行,`__name__`的值是被直接执行.
8. 在主程序中书写测试代码:当模块被直接执行的时候进行系统测试
### 3.6 第一个Python程序
1.一个写入文件的程序
```python
#encoding=utf-8
'模块文档，在此处填写模块的描述性信息'
import os
# 为属性os.linesep取一个新的别名，这样做一方面能缩短变量名，另一方面还能改善访问该变量的性能。
ls=os.linesep;
# get filename
while True:
    fname=raw_input("Enter file name:")
    # 判定当前文件是否已经存在，如果是返回true
    if os.path.exists(fname):
        print "Error,file already exists!!!"
    else:
        break;

# get file content lines
all=[]
print "\nEnter lines('.'by it self to quit)"
#loop until user terminates input
while True:
    entry=raw_input('>')
    if entry!='.':
        all.append(entry)
    else:
        break

# write lines to file with proper line-ending
# 创建一个文件对象
fobj=open(fname,'w')
# 向文件中写入数据
fobj.writelines("%s%s" % (x,ls) for x in all)
# 关闭文件对象
fobj.close();
print "DONE！！！"


```
>* 类似于`os.linesep`这样的名字需要解释器做两次查询：（1）查找os以确定他是一个模块（2）在这个模块中查找属性linesep变量。因为模块也是全局变量，我们多消耗了系统资源，如果在一个函数中频繁使用一个属性，给这个属性取一个本地变量别名。变量查找速度将会快很多——在查找全局变量之前总是先查找本地变量。
>1

1. try-catch-else语句：try子句是一段我们希望检测错误的代码，catch子句是当出现错误时处理错误的代码，else语句是try子句无误时执行的代码
2. 一个从文件中读取信息的程序
```py
#encoding=utf-8
'读取一个文件中的所有的数据并打印到控制台'
def readFile():
    fname=raw_input("Enter filename:")
    try:
        fobj=open(fname,'r')
    except IOError,e:
        print "File open erro :",e
    else:
        for eachline in fobj:
            print eachline
        fobj.close();
readFile()
```
## Chapter 4
### 4.1 python对象
1. Python使用对象模型来存储数据。构建任何类型的值都是一个对象。所有的Python对象都有三个特性：身份、类型和值
>* 身份：每一个对象都有一个唯一的身份标示自己，任何对象的身份可以使用内建函数`id()`来获取。这个值可以被认为是对象的内存地址。
>* 类型：对象的类型决定了该对象可以保存什么类型的值，可以进行什么样的操作，以及遵守什么样的规则。你可以使用内建函数`type()`来查看对象的类型，因为在python中类型也是对象，所以type返回的是对象而不是简单的字符串。
>* 值：对象表示的数据项。
上面三个特性在对象创建的时候就被赋值了，除了值之外，其它两个属性都是只读的。对于新式类型和类，对象的类型也是可以改变的，但是并不推荐这样做。
2. 对象属性：某些对象有属性、值和相关联的可执行代码，比如方法。Python使用句点（.）标记法来访问属性。属性包括响应对象的名字等。
### 4.2 标准类型


类型|Eng
--|---|--
整型|Integer
布尔型|Boolean
长整型|long integer
浮点型|Floating point real number
复数型|Complex number
字符串|String
列表|List
元组|Tuple 
字典|Dictionary
###4.3 其它内建类型
类型|
--|
Null对象(None)|
文件|
集合/固定集合|
函数/方法|
模块|
类|

1. 对象的一系列的固有属性和特性都必须事先定义好。从这个角度看，类型正是保存这些信息的最佳位置。描述一种类型所需要的信息不可能使用一个字符串来搞定，所以类型不能是一个简单的字符串，这些信息不能也不应该和数据保存在一起，所以我们将类型定义为对象。
2. 所有类型对象的类型都是type.
3. Python有一个特殊的类型，被称为none对象或者noneType。它只是一个值，那就是None.它不支持任何运算也没有任何内建方法。，None没有任何有用的属性，它的布尔值为false。
4. 布尔值：所有对象类型均可以用于布尔测试，同类型的对象之间可以比较大小，每个对象天生具有布尔TRUE或FALSE值，空对象，值为0的任何数字或者null对象》None的布尔值都是false。
对象|解释
--|---|--
代码对象|代码对象是编译过的Python源代码片段，它是可执行对象。通过调用内建函数compile()可以得到代码对象。代码对象可以被exec命令或者eval()内建函数来执行。代码对象本身不会包含任何执行环境信息。
帧对象|帧对象表示Python中的执行帧栈。帧对象包含了Python解释器在执行时所需要的所有的所有的信息。
跟踪记录对象|当异常发生的时候一个包含了针对异常的栈跟踪信息的跟踪记录对象会被创建。如果一个异常有自己的处理程序，那么处理程序就可以访问这个跟踪记录对象。
切片对象|当使用Python扩展的切片语法的时候，就会获得切片对象。
省略对象|省略对象用于扩展切片语法中用于记号
XRange对象|调用内建函数xrange()会产生一个XRange对象，用于需要节省内存使用或者range()无法完成的超大数据集合场合。
### 4.5 标准类型操作符
1. 对象值的比较：比较操作符用来判断同类型的对象是否相等，所有的内建对象均支持比较运算。比较运算符返回布尔值TRUE或者FALSE
2. Python提供了is 和 is not 来判断两个变量是否指向同一个对象`a is b`等价于`id(a)==id(b)`
3. 布尔操作符 `and`,`or`,`not`
### 4.6 标准类型内建函数
函数|功能
--|---|--
cmp(obj1,obj2)|比较obj1和obj2，根据比较结果返回整型值
repr(obj)|返回一个对象的字符串表示，通常可以使用该字符串重新获得一个对象（使用eval()内建函数）
str(obj)|返回对象适合可读性好的字符串表示
type(obj)|得到一个对象的类型，返回的是一个type对象

![][1]
1. 内建函数str(),repr(),或反引号操作符（``）可以方便的以字符串的方式获取对象的内容，类型，数值属性等信息。
```python
def displayNumberType(num):
    print num,"is",
    if isinstance(num,(int,long,float,complex)):
        print 'a number of type:',type(num).__name__
    else:
        print 'not a number at all'

displayNumberType(12)
displayNumberType(12.3)
displayNumberType(2+3j)
displayNumberType(1211111111111111111111111111111L)
```
## Chapter 5 数字
1. Python支持多种数值类型:整型,长整型,布尔型,双精度浮点型,十进制浮点型和复数
2. 数值对象是不可改变对象,更新数值对象是生成一个新的数值对象,并得到他的引用.
3. 可以使用del语句删除一个对象的引用.
4. 复数的内建属性:


属性|描述
--|---|--
num.real|该复数的实部(float)
num.image|该复数的虚部(float)
num.conjugate()|返回该复数的共轭复数(complex)
5. 对于存在多种数值类型的操作数的算术表达式,将首先将所有表达式转化为统一类型后计算,转换的优先级:复数 浮点数 长整型 整型.
6. 下列操作符,从上到下,优先级依次降低:


操作符|描述
--|--
**|幂运算
+|正号
-|负号
*|
/|
//|
%|
+|
-|

7. 位操作符(只适用于整型),负数会被当做正数的二进制补码来进行处理


位操作符|功能
--|---|--
~num|单目运算,对数的每一位取反,结果是-(num+1)
num1<<num2|num1左移num2位
num1>>num2|
num1&num2|num1与num2按位与
num1^num2|num1与num2按位异或
num1|num2|num1与num2按位或
8. 功能函数:
函数|功能
--|---|--
abs(num)|返回num的绝对值
coerce(num1,num2)|将num1与num2转换位相同类型(向上转型)之后,以一个元组的形式返回
divmod(num1,num2)|返回num1/num2的结果及余数
pow(num1,num2,mod=1)|取num1的num2次方,如果提供了mod再对结果进行取余运算.
round(fit,ndig=1)|取一个浮点数并对其四舍五入,保留ndig位小数
9. 仅适用于整型的内建函数
函数|描述
--|---|--
hex(num)|将数值转化位16进制形式并以字符串形式返回
oct(num)|将数值转化位8进制形式并以字符串形式返回
chr(num)|将数值num转化为ASCII字符,范围只能是0<=num<=255
ord(chr)|上面函数的逆过程
unichr(num)|接受Unicode码值,返回其对应的Unicode字符.
10. random模块
函数|描述
--|---|--
randint()|两个整型参数,返回两个之间的随机整数
randrange()|接受和range()函数一样的参数,随机返回range()结果中的一项
uniform()|与randint类似,只不过返回的是浮点数
random()|与uniform类似,只不过上限为1.0,下限为0.0
choice()|随机返回给定序列中的一个元素

## Chapter 6 序列：字符创、列表和元组
### 6.1 序列
1. 序列类型有着相同的访问模式：它的每一个元素可以通过指定一个偏移量来找到，而多个元素可以通过切片操作的方式一次性得到。
2. 序列类型操作符：
序列操作符|作用
--|---|--
seq[ind]|获取序列中的第ind个元素
seq[ind1:ind2]|获取序列中第ind1到第ind2之前的所有元素
seq*expr|序列重复expr次
seq1+seq2|链接两个序列为一个序列（注1）
obj in seq|判断元素是否在序列中
> 注1：这种操作符并不是最快或者说是最有效的，对于列表，可以使用extend（）方法合并两个列表
> 对于字符串可以使用一个join方法。

使用：
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584809.jpg)

使用extend方法合并字符串
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584666.jpg)
进行翻转的切片操作：
![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584512.jpg)

![这里写图片描述](https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329584406.jpg)

3. 内建函数BIF:
	1. 序列本身就包含了迭代的概念，之所以会这样，是因为迭代这个概念就是从序列，迭代器，或者其他支持迭代操作的对象中泛化得来的。
	2. 序列类型转换工程函数

		函数|含义
	--|--|--
	list(iter)|把可迭代对象转化为列表
	str（obj）|把obj对象转化为字符串
	unicode(obj)|把对象转换为Unicode字符串（使用默认编码）
	tuple(iter)|把一个可迭代对象转化为一个元组对象。
	3. 序列类型内建函数


	函数名|功能
	--|---|--
	enumerate(iter)|接受一个可迭代对象作为参数，返回一个enumerate对象（同时也是一个迭代器），该对象生成由item每个元素的index值和item值组成的元组
	len(seq)|返回一个seq的长度
	max(item,key=None) or<br/>max(arg0,arg1....,key==None)|返回item中的最大值，如果指定了key这个key必须是可以传递给sort()方法的，用于比较的回调函数
	min(item,key=None) or<br/>min(arg0,arg1.....,key=None)|最小值
	reversed(seq)|接受一个序列作为参数，返回一个以逆序访问的迭代器
	sorted(iter)|返回一个可迭代对象作为参数，返回一个有序的列表
	还有两个，以后添加


----------


### 6.2 字符串
1. Python中单引号和双引号的作用是一样的。
2. Python中没有字符这个类型，而是用长度为1的字符串来表示这个概念。
3. 字符串也是一种序列，可以执行序列的切片操作。
4. 跟数字类型一样，字符串类型也是不可变的，所以你要改变一个字符串就必须创建一个新的串的方式来实现。


----------


### 6.3 字符串和操作符
#### 6.3.1 标准类型操作符

``` python
>>> a='abc'
>>> b="lmn"
>>> c='xyz'
>>> a<b
True
>>> b==c
False
>>> a<c and c=='xyz'
True
```
#### 6.3.2 序列操作符切片
1. 正向索引：索引值开始于0（第一个字符），结束于总长度减一
2. 反向索引：索引值开始于-1（最后一个字符），结束于负的总长度（第一个字符）
3. 默认索引：如果第一个值和最后一个值都没有指定的话，则分别以字符串的第一个和最后一个索引值作为默认值。
4. ![enter description here][2]


  5. 成员操作符（in，not in）用于判断一个字符或者一个子串（中的字符）是否出现在另一个字符串中。出现则返回TRUE，否则返回FALSE
  6. ![enter description here][3]


  [1]: https://www.github.com/g110011010/MarkdownFile/raw/master/Image/1506329583176.jpg
  [2]: ./images/1506331053218.jpg
  [3]: ./images/1506331340088.jpg
  
  7. String 模块中预定义的字符串：
  

``` python
>>> import string
>>> string.uppercase
'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
>>> string.lowercase
'abcdefghijklmnopqrstuvwxyz'
>>> string.letters
'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz'
>>> string.digits
'0123456789'
```
8. for-else语句和while-else语句：当for循环或者while循环正常执行完毕的时候，else块中的语句将会得到执行，否则else语句不会得到执行：

``` python
def forElse(char,str):
    for c in str:
        if char == c:
            print 'catch'
            break
    else:
        print 'no \'d\'in a'
a='abcdefg'
c1='f'
c2='h'
print 'test1:'
# for循环未能正常执行完毕，break退出循环
forElse(c1,a)
print 'test2:'
# for 循环正常执行完毕，else中语句被执行
forElse(c2,a)


输出：
test1:
catch
test2:
no 'd'in a
```
``` python
#encoding=utf-8
def whileElse(char,str):
    length=0
    while length<len(str):
        # 这种写法比较低效，因为每次循环都要计算一次长度。最好先计算一次长度然后做一下保存
        if char==str[length]:
            print 'catch'
            break
        length+=1
    else:
        print 'no \'d\'in a'
a='abcdefg'
c1='f'
c2='h'
whileElse(c1,a)
whileElse(c2,a)

输出：
catch
no 'd'in a
```
==关于变量作用域的发现==

``` python
def test():
    for c in a:
        print c
a='abcdef'
test()

输出：
a
b
c
d
e
f
```
``` python 
def test():
    a='fsdgfd'
    for c in a:
        print c
a='abcdef'
test()

输出：
f
s
d
g
f
d

```
1. python 中没有块级域。在if，while或者其他地方定义的变量，在if或者while"块“的外面仍然能够使用。

``` python
for a in range(1):
    name="Hello"
print name
```
2. 局部作用域：函数块有着自己的局部作用域，（应该是在调用某个函数的时候，在栈中为这个函数开辟一个作用域，也就是函数入栈，然后函数在执行的过程中，使用的变量从本作用域中的查找，如果本作用域中没有，就到调用它的那个作用域中去查找，以此类推，直到最后查找失败报错。当函数执行完毕，本作用域从栈中移除，域中的所有变量丢失，所以在返回到父作用域中执行后，将无法再访问该作用域中的内容）
3. 作用域链：，Python中有作用域链，变量会由内到外找，先去自己作用域去找，自己没有再去上级去找，直到找不到报错。在函数未执行之前，作用域已经形成了，作用域链也生成了。

``` python

name = "lzl"

def f1():
    print(name)

def f2():
    name = "eric"
    f1()

f2()

输出：
lzl
作用域链是在函数执行前形成的
```
9. 字符串连接：

``` python
>>> a='hello'+' '+'world'
>>> a
'hello world'
>>> b='hello'' ''world'
>>> b
'hello world'
>>> c="hello"' '"world"
>>> c
'hello world'
```
10. 如果一个普通字符串和一个Unicode字符串做连接处理。Python会在连接操作前首先把普通字符串转化为Unicode字符串。

  
###   只适用于字符串的操作符
#### 格式化操作符(%)
1. 字符串格式化操作符

| 格式化字符 | 转换方式                        |
| ---------- | ------------------------------- |
| %c         | 转换成字符(ASCII码值)           |
| %r         | 优先用repr()函数进行字符串转换  |
| %s         | 优先使用str()函数进行字符串转换 |
| %d/%i      | 转成有符号十进制数              |
| %u         | 转成无符号十进制数              |
| %o         | 转成无符号八进制数              |
| %x/%X      | 转成无符号十六进制数            |
| %e/%E      | 转成科学计数法                  |
| %f/%F      | 转成浮点型                      |
| %g/%G      |  %e和%f%E和%F的缩写                               |
|%%|输出%|
2. 格式化操作符辅助指令

符号|作用
--|---|--
*|定义宽度或者小数点精度
-|用作左对齐
+|在正数前面显示加号(+)
<sp>|在正数前面显示空格
#|在八进制前面显示零,在十六进制前面显示'0x'或者'0X'
0|显示的数字前面填充的是0而不是默认的空格
%|'%%'输出单一的'%'
(var)|映射变量(字典参数)
m.n|m是显示的最小宽度,n是小数点后的位数


#### 字符串模板:更简单的替代品