
<!--7593473-->
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script><!--插入数学公式用的脚本，在下文中使用$$数学公式$$来插入数学公式-->
博客中要分别讨论的java专题：
>* Calendar类
>* File类
>* Number类

1. 计算机中字节（byte）是最小的存储单元，1byte=8bits。
2. 内存：随机访问存储器（RAM）。内存中每一个字节都有其唯一的地址。
3. 点距是指像素之间以毫米为单位的距离，点距越小，显示效果越好。
4. 计算机能够理解的语言是机器语言，为了使用方便创建了汇编语言（低级语言）。
5. 汇编语言-->汇编器-->机器代码文件
5. 高级语言源代码-->解释器-->机器代码/虚拟机器代码-->立刻执行<br>高级语言源代码-->编译器-->机器代码文件-->执行机器代码文件
6. 多道程序设计允许多个程序通过共享CPU同时运行。<br>多线程允许单个程序同时执行多个任务<br>多处理（并行处理）是指使用两个或者多个处理器同时并行执行子任务，然后将子任务的结果合并以得到整个任务的结果。
7. java语言定义了Java的语法，Java库在java API中定义，JDK是用于开发和运行java程序的软件。IDE是快速开发程序的集成开发环境。
8. java:源程序（.java）-->编译-->字节码（.class）（+库代码）-->JVM执行-->结果
9. JVM执行字节码的过程就是将字节码中的单独的一步翻译为目标机器语言代码，然后立即执行，然后继续解释下一步字节码。
10. jvm执行一个java程序时，JVM首先会使用一个**类加载器**的程序将类中的字节码加载到内存中，如果程序中使用到了其他的类，那么类加载器会在使用它们之前动态的加载那些需要的类。当加载该类后，JVM使用一个称为**字节码验证器**的程序来检验字节码的合理性，确保字节码不会违反Java 的安全规范。
10. 命令行编译执行hello.java文件：<br>`javac hello.java`生成.class文件<br>`java hello`执行hello.class文件，注意不能写成java hello.class 否则机器会查找执行hello.class.class文件。
11. java中的错误：
错误提示|原因
--|---|--
**NoClassDefFoundError**|运行一个不存在的类时
**NoSuchMethodError**|类中没有正确的main方法
**NullPointerException**|调用值为null的引用变量上的方法时会发生此类异常
**ArrayIndexOutOfBoundsException**|访问数组下标越界时
**InputMismatchException**|用户输入类型与设定类型不匹配时

13. 程序中事物的名字称为标识符，标识符组成：<br>首字母：字母、下划线、美元符号<br>其余：字母、下划线、美元符号、数字<br>不能是保留字或者true false null<br>长度任意<br>习惯上，字符$只用于机器自动生成的代码片中
14. java数值类型：


类型名|存储大小|Scnner对象方法|最大值|最小值|直接量表示
--|---|---|---|---|---|
byte|8位带符号数|nextByte()|Byte.MAX_VALUE|Byte.MIN_VALUE|
short|16位带符号数|nextShort()|Short.MAX_VALUE|.MIN_VAULE|
int|32位带符号数|nextInt()|Integer.MAX_VALUE|Integer.MIN_VAULE|
long|64位带符号数|nextLong()|Long.MAX_VALUE|Long.MIN_VAULE|l或L(21343L)
float|32位，标准IEEE754|nextFloat()|Float.MAX_VALUE|Float.MIN_VAULE|f或F(234.45F)
double|64位，标准IEEE754|nextDouble()|Double.MAX_VALUE|Double.MIN_VAULE
引用类型|
String||next()或nextLine()|
> next()方法读取以空白字符结束的字符串（空格，\t,\r,\f,\n）
> nextLine()方法读取以回车键为结束标志的字符串
> 不要在读取数值类型的next方法（nextInt()等）和next()后使用nextLine(),以避免引发错误


15. JAVA数学运算：


运算符|名字|示例
--|---|--
+|加|
-|减|
*|乘|
/|除|
%|求余|
Math.pow(a,b)|幂运算|$$a^b$$
16.java中整型直接量表示：
>整型直接量默认是一个十进制的 int类型的数字
>浮点型直接量默认是double类型的数字
>为了提高可读性，java允许在数值直接量中两个数字之间添加下划线`long ssn=123_456L`
>引用类型直接量的默认值是null
>true和false是直接量；


进制|表示|示例
--|---|--
二进制|0b或0B|0B1100110
八进制|0|06754
十进制|无|2341
十六进制|0x或0X|0XFFFF
17.科学计数法：`123E-2`等同于$$123*10^{-2}$$
18. java中int类型与Boolean类型之间无法进行（强制）转化。
19. 布尔操作符


操作符|名称|说明
--|---|--
！|非|逻辑非
&&|与|逻辑与
\|\||或|逻辑或
^|异或|逻辑异或
20. switch语句
```java
switch(switch 表达式){
	case vaule1:语句（组）1；
			break；
	case vaule2:语句（组）2；
			break;
	……
	default:默认情况下执行的语句组	
}
```
> * switch表达式必须能够计算出一个`char byte short 或 string` 类型的值，并且必须总是要用括号括住
> * vaule1,vaule2,……必须与switch表达式的值具有相同的数据类型，且必须为常量表达式，即不能包含变量。

21. Math 方法：

方法|描述
--|---|--
sin(radians)|返回以弧度为单位的角度的三角正弦函数值
cos(radians)|
tan(radians)|
toRadians(degree)|将以度为单位的角度转化为以弧度表示
toDegree(radians)|
asin(a)|返回以弧度为单位的角度的反三角值
acos()|
atan()|
exp(x)|返回e的x次方
log(x)|返回x的自然底数
log10(x)|返回x的以10为底的对数
pow(a,b)|返回a的b次方
sqrt(x)|对于x>=0，返回x的平方根
ceil(x)|x向上取整为他最接近的整数，返回double
floor(x)|x向下取整为他最接近的整数，返回double
rint(x)|取x最接近的整数，与两个整数距离相等时取偶数
round(x)|四舍五入，x为单精度数时返回int,双精度数时返回double
min(a,b)|返回数字最小值
max(a,b)|
abs(a)|返回数字绝对值
random()|返回0.0到1.0之间的double类型

22. Math类不需要导入，因为它在java.lang包中，在一个java程序中java.lang包中的所有类都是隐式导入的。
23. char 型数据可以被转化为任意数据类型，反之亦然。
24. 将整数转化为char型数据时只用到该数据的低16位，其余的部分都被忽略。
25. 0~FFFF内的所有十六进制正整数都可以隐式的转化为char类型。
26. Character类中的方法：


方法|描述
--|---|--
isDigit(ch)|如果指定的字符是一个数字，返回true
isLetter(ch)|如果指定的字符是一个字母，返回true
isLetterOrDigit(ch)|如果指定的字符是一个数字或字母，返回true
isLowCase(ch)|如果指定的字符是一个小写字母返回true
isUpperCase(ch)|大写字母
toLowCaese(ch)|转化为小写字母
toUpperCase(ch)|大写
27. String对象的简单方法


方法|描述
--|---|--
length()|返回字符串中的字符数
charAt(index)|返回字符串s中指定位置的字符
concat(s1)|将本字符串和s1连接，返回一个新的字符串
toUpperCase()|返回一个新的字符串，其中所有的字母大写
toLowCase()|返回一个新的字符串，其中所有的字母小写
replace（oldChar:char,newChar:char）:String|将字符串中所有匹配的字符替换成新的字符，并返回新的字符串
replaceFirst(oldString:String,newString:String):String|将字符串中第一个匹配的子字符串转换成新的子字符串，然后返回新的字符串
replaceAll(oldString:String,newString:String):String|将字符串中所有匹配的子字符串转换成新的子字符串，然后返回新的字符串
split(delimiter:String):String[]|返回一个字符串数组，其中包含被分隔符分隔的子字符串集
toCharArray()|将字符串转化为char型数组


28. 字符串对象的比较方法


方法|描述
--|---|--
equals(s1)|如果该字符串的内容与s1的相同，返回true
equalsIgnoreCase(s1)|如果该字符串的内容与s1的相同，返回true;不区分大小写
29. 声明数组变量：
```java
elementType[] arrayRefVar;//仅仅声明一个数组变量，并不在内存中给数组分配任何空间，只是创建一个对数组的引用的存储位置。
elementType arrayRefVar[];//作用同上，C/C++风格
arrayRefVar=new elementType[arraySize]//创建数组，并将数组的引用赋值给数组变量
//当创建数组后，它的元素会被赋予默认值，其中数值型基本数据类型的默认值为0，char型的基本数据类型为'\u0000',boolean型的默认值为false，String型的默认初始值为null(因为String变量是引用类型，默认值为null)
```
30. 
```java
public class test {
    public static void main(String[] args) {
        int[] a=new int[]{1,2,3,4,5};
        int[] b=a;//传递的是一个引用，a与b同时指向同一个对象
        a[0]=9;
        System.out.println(a[0]);//9
        System.out.println(b[0]);//9
    }
}
```
31. 数组的复制
有三种方法：
* 使用循环语句逐个的复制数组元素
* 使用System类中的静态方法arraycopy
* 使用clone方法复制数组
```java
int[] a={1,2,3,4,5,6,7,8};
        int[] b=a;//a与b 指向同一个数组对象
        //使用循环语句逐个的复制数组中的元素
        int[] c=new int[a.length];
        for(int i=0;i<a.length;i++){
            c[i]=a[i];
        }
        //使用System类中的静态方法arraycopy复制数组
        int srcPoint=0;//源数组中复制元素的起始位置
        int tarPoint=0;//目标数组中复制元素的起始位置
        int length=a.length;//从源数组中复制元素的个数
        int[] d=new int[a.length];
        System.arraycopy(a,srcPoint,d,tarPoint,length);
        //使用clone方法
        int[] e=new int[a.length];
        e=a.clone();
```
32. java中调用方法在向方法中传递参数时：
* 对于基本数据类型，是按照值传递进行的
* 对于数组类型参数，传递的是数组的引用（地址传递）
33. 可变长参数列表：具有同样类型的可变长度的参数可以传递给方法，并将作为数组对代。形式`elementType...varArray`变量类型和数组名，其中一个方法中只能有一个可变长度参数列表，且只能在参数列表的最后声明。
```java
package Chapter7;

/**
 * Created by sf on 2017/8/20.
 */

public class test {
    /**
     *将数组中的元素打印输出
     *@param array 要打印的数组
     *@author sf
     */
    public static void printArray(int...array){
        for(int e:array){
            System.out.print(e+" ");
        }
        System.out.println();
    }
    public static void main(String[] args) {
        test.printArray(1,2,3,4,5);
        test.printArray(11,22,3,44,55,667,8);
        int[] a={6,7,8,9,0};
        test.printArray(a);
        test.printArray(11,22,3,44,55,667,8);
    }
}
```

34. java.util.Arrays类
方法|描述|示例
--|---|--
sort()|对整个数组或者数组的一部分进行排序
parallelSort()|对整个数组或者数组的一部分进行排序，计算机有多个处理器时，这种方法更加高效
binarySearch()|使用二分法查找数组
equals()|判断两个数组中对应位置的内容是否相同
fill()|填充整个或者部分数组
toString()|返回一个包含数组中所有元素的字符串
```java
package Chapter7;

import java.util.Arrays;

/**
 * Created by sf on 2017/8/20.
 */

public class test {
    /**
     *将数组中的元素打印输出
     *@param array 要打印的数组
     *@author sf
     */
    public static void printArray(int...array){
        for(int e:array){
            System.out.print(e+" ");
        }
        System.out.println();
    }
    public static void main(String[] args) {
       int[] a={1,4,2,5,2,6,3,67,23,523,62,46,7};
        System.out.println("Array a:"+ Arrays.toString(a));
        int[] b=a.clone();
//        对整个数组进行排序
        Arrays.sort(b);
        System.out.println("Array b:"+Arrays.toString(b));
        int[] c=a.clone();
//        对数组进行部分排序
        Arrays.sort(c,2,7);
        System.out.println("Array c:"+Arrays.toString(c));
        int[] d=a.clone();

        //        对整个数组进行排序
        Arrays.parallelSort(d);//使用与sort()方法类似，但是当电脑有多个处理器的时候，这种方法更加高效
        System.out.println("Array b:"+Arrays.toString(d));
        int[] e=a.clone();
//        对数组进行部分排序
        Arrays.parallelSort(e,2,7);
        System.out.println("Array c:"+Arrays.toString(e));
//        二分查找数组中的关键字
        System.out.println(Arrays.binarySearch(a,2));
        int[] f=a.clone();
        System.out.println(Arrays.equals(a,f));//true
        System.out.println(Arrays.equals(a,e));//false

        int[] g=new int[8];
        int[] h=g.clone();
        Arrays.fill(g,8);//将8填充满整个的数组
        System.out.println(Arrays.toString(g));
        Arrays.fill(h,2,5,6);//将8填充到数组2,3,4位置上
        System.out.println(Arrays.toString(h));
    }
}

```
35. 在运行程序时，可以向main方法传递参数，参数将会被存储在数组args中，传入的所有参数均将作为字符串来进行处理。java解释器会根据传入的参数的数目来创建对应的数组存储参数，如果传入数组中的数据个数为n,那么解释器将会执行`args=new String[n]`,如果在运行时没有参数传入main方法,那么使用`new String[0]`创建数组，在这种情况下该数组时长度为0的空数组，args是对这个数组的引用。因此args不是null但是args.length=0
36. 二维数组的每一行本身也是一个数组，因此各行的长度可以是不相同的，这样的数组称为锯齿数组，创建锯齿数组：
```java
     int[][] a={
                {1,2,3,4,5},
                {1,2,3,},
                {1,2,3,4},
                {1,2,3},
                {1,2}
        };
        int[][] b=new int[3][];//第一个下标是必须指定的，否则会产生语法错误
        b[0]=new int[5];
        b[1]=new int[6];
        b[2]=new int[3];
```
37. 构造方法在使用new操作符创建对象的时候被调用
* 构造方法必须具备与所在类相同的名字
* 构造方法没有返回值类型，甚至连void都没有
* 构造方法是在创建一个对象使用new操作符的时候被调用，构造方法的作用是初始化对象
38. 一个类可以不定义构造方法，这种情况下，类中隐含定义了一个方法体为空的无参构造方法。这种构造方法称为默认构造方法。
39. 对象是通过对象引用变量来访问的。对象引用变量中只包含了对对象的引用。（与数组变量类似，实际上，数组变量也是一个对象引用变量）
40.  对象成员可以使用（.）操作符来调用对象的数据域和方法，该操作符也被称为对象成员引用操作符。
41. 可以创建一个对象而不将它明确的赋值给一个变量。这种方式创建的对象称为匿名对象.
42. 如果一个引用类型的数据域没有引用任何对象，那么这个数据域就有一个特殊的java值null。
43. 对基本类型变量来说，对应内存所存储的值是基本类型值。对于引用类型变量来说，对应内存所存储的值是一个引用。
44. Date类：


方法|描述
--|---|--
Date（）|为当前时间创建一个date对象
Date（elapseTime：long）|使用一个给定的时间创建Date对象
toString（）|返回一个代表时间和日期的字符串
gettime（）|返回对象中的给定时间
setTime(elapseTime：long)|在对象中设置一个新的流逝时间
45. Random类
方法|描述
--|---|--
Random()|以当前时间作为种子创建一个Random对象
Random(seed:long)|以一个特定的值作为种子创建一个Random对象
nextInt()|返回一个随机的int值
nextInt(n:int)|返回一个0到n之间的随机int类型值
nextLong()|返回一个随机的 long值
nextDouble()|返回一个0.0到1.0之间的double型变量
nextFloat()|返回一个0到1之间的随机float型值
nextBoolean（）|返回一个随机的double值
>创建一个Random对象时，必须指定一个种子或者使用默认的种子。种子是一个用于初始化一个随机数字生成器的数字。无参数构造方法使用当前已经逝去的时间作为种子。如果两个Random对象有相同的种子，那他们将产生相同的数列。

46. Point2D类
方法|描述
--|---|--
Point2D(x:double,y:double)|用给定的x和y坐标来创建一个对象
distance(x:double,y:double)|返回该点到给顶点（x,y）之间的距离
distance(p:point2D):double|返回操作
getX()|返回该点的x坐标
getY()|返回该点的y坐标
toString()|返回该点的字符串表示
47. 静态变量被类中的所有实例共享。静态方法不能访问类中的实例成员
48. 静态变量将变量值存储在一个公共的内存空间，如果某一个类修改了静态变量的值，那么该类的所有对象都将受到影响
49. 在UML图中，静态变量和静态方法都是用下划线标注的
50. 静态方法能调用静态方法，访问静态数据域，不能调用实例方法和实例数据域
51. 如果一个变量或方法依赖于类的某一个具体实例，那就应该将它定义为实例方法或实例变量，否则就定义为静态方法或静态变量。
52. 可见性修饰符：可见性修饰符可以用于确定一个类以及它的成员的可见性


修饰符|在同一类内可访问|在同一包内可访问|在子类内可访问|在不同包内可访问
--|---|--
public|√|√|√|√
protected|√|√|√
默认/空修饰符|√|√
provite|√

> 子类可以重写它父类中protected方法，并将它的可见性改为public。但是子类不能削弱父类中定义方法的可访问性。例如：如果父类中的方法定义为public，在子类中重写时也必须定义为public。
53. 向方法传递对象参数，是将对象的引用传递给方法
54. 数组既可以存储基本类型值，也可以存储对象。
55.  实例变量和静态变量的作用域是整个类，无论变量在哪个地方声明
56. 如果一个局部变量和一个类变量具有同样的名字，那么局部变量优先。
57. 关键字this引用自身，它也可以用于在构造方法内部调用同一个类的其它的构造方法。
58. 在引用隐藏数据域以及调用一个重载的构造方法时，必须使用this关键字。
59. Java要求在构造方法中，this应在其它任何可执行语句之前出现。
```java
public class Test {
    Test(int a){
        System.out.println("hello,"+a);
    }
    Test(double a){
        System.out.println("hello,"+a);
    }
    Test(){
        this(1);//必须是第一个语句，所以在一个构造方法中只能调用本类的一个重载构造方法
    }
    public static void main(String[] args) {
       Test test=new Test();
    }
}
```

60. 类的抽象是指将类的实现和类的使用分隔开，实现的细节被封装并且对用户隐藏，这被称为是类的封装。
61. 类中间的关系通常是关联、聚合、组合以及继承。
62. 关联：
* 关联由两个类之间的实线表示，可以有一个可选的标签描述关系
* 关系中的而每一个类可以有一个角色名称，描述在该关系中担当的角色。关联中涉及的每一个类可以给定一个多重性，放置在类的边上用于给定UML图中关系所涉及类的对象数。
63. 聚集（1对多）和组合（1对1）：
* 聚集是关联的一种特殊形式，代表了两个对象之间的归属关系。聚集建模has-a关系。
* 一个对象可以被多个其它的聚集对象所拥有。如果一个对象只归属于一个聚集对象，那么它和聚集对象之间的关系成为组合。
64. 如果一个基本类型值出现在一个需要对象的环境中，编译器会将基本类型值自动装箱。如果一个对象出现在需要基本类型值得环境中，编译器会将对象进行自动开箱。
65. BigInteger和BigDecimal类：可以用于表示任意大小和精度的整数或者十进制数
66. String对象是不可改变的。字符串一旦创建，内容就不能再更改。
```java
package Chapter10;

/**
 * Created by sf on 2017/8/22.
 */
public class Test {


    public static void main(String[] args) {
       //创建一个字符串

//        使用字符串直接量创建,如果内存中已经有相同字符串的实例，那么此字符串直接引用内存中字符串对象而不创建新的对象。
        String s1="Welcome";//将其看作是String对象
//        创建String对象，直接创建一个新的对象，并将对象引用返回给字符串变量
        String s2=new String("Welcome");
//        使用字符数组创建一个字符串
        char[] charArray={'W','e','l','c','o','m','e'};
        String s3=new String(charArray);
        String s4="Welcome";
        System.out.println(s1==s2);//false
        System.out.println(s1==s3);//false
        System.out.println(s1==s4);//true
    }
}
```
67.  String格式化字符串：使用format方法
与printf()方法的使用很类似
String.format(format,item1,item2,...,itemk)
`     String s1=String.format("%5d%4f,%7s",123,23.4,"herllo");`
68. StringBuilder和StringBuffer类：类似于String类，区别在于String类是不可改变的。只要是使用字符串的地方都可以只用这两个类。区别在于这两个类可以实现追加，插入，等操作，更加灵活。StringBuffer中修改缓冲区的方法是同步的，如果是多任务并发访问，就使用StringBuffer,如果是单任务访问，就使StringBuilder，因为BufferBuilder更加高效。
69. StringBuilder方法：


方法|描述
--|---|--
append（）|追加元素到字符串构造器
delete（int startIndex，int endIndex）|删除从start到index-1位置的字符串
insert（）|向构建器中插入数据
replace()|将指定位置的子字符串替换为新的字符串
reverse()|倒置构建器中的字符
setCharAt（）|将构建器中指定索引位置设置为新的字符
toString（）|返回一个字符串对象
capacity()|返回该字符串构建器的容量
charAt()|返回指定位置的字符
length（）|返回该构造器中实际字符的数目
setLength()|设置构造器的容量，如果小于字符串长度，则多余部分会被剪切掉
subString()|返回一个子字符串
trimToSize()|减少用于字符串构建器的存储大小
70. 面向对象编程允许你从已经存在的类中定义新的类，这称为继承
71. 关于继承应该注意的几个关键点：
> * 子类并不是父类的一个子集，实际上，一个子类往往包含比父类更多的方法和信息。
> * 不是所有的是一种（is-a）关系都该用继承，正方形是一种矩形，但正方形继承矩形并不合适
> * 继承是用来为是一种（is-a）关系建模的。不要仅仅为了重用代码这一个原因而盲目的扩展一个类。父类和子类之间必须存在（is-a）关系。
> * 在java中，一个类只能继承自唯一的一个类，这种继承被称为单一继承。


72. 关键字super可以被用于两种用途：调用父类的构造方法，调用父类的方法
73. 父类的构造方法不会被子类继承
74. 语句super（）必须出现在子类构造方法的第一行。
75. 如果父类的构造方法在子类构造方法中没有被显式的调用，那么编译器会在子类的构造方法中第一句添加上`super()`;
76. 在任何情况下，调用一个类的实例时，都会沿着继承链调用所有父类的构造方法。
77. 如果要设计一个可以被继承的类，最好提供一个无参构造函数以避免程序出错。
78. 子类从父类中继承方法。有时子类需要修改父类中定义的方法实现，这称作`方法重写(method overriding)`
79. 方法重写：要重写一个方法，需要在子类中使用和父类一样的签名以及一样的返回值类型来对该方法进行定义。
80. 实例方法被重写之后，其将沿着继承链覆盖父类中的方法，也就是说如果父类中有方法使用了该重写方法，那么父类调用的方法将是在子类中重写之后的方法。（仅当实例方法是可以访问时，它才能够被覆盖。因为私有方法在它的类本身以外是不能够被访问的，如果子类中定义了和父类中私有方法完全一样的方法。那么这两个方法没有半毛钱关系）
81. 静态方法也能够被继承，但是不能够被覆盖。如果父类中定义的静态方法在子类中被重新定义，那么父类中定义的静态方法将被隐藏。可以使用父类名.静态方法名调用隐藏的静态方法。
82. 重载意味着使用同样的名字但是不同的签名定义多个方法。重写意味着在子类中提供一个对方方法的新的实现。
83. 重写发生在通过继承而相关的不同类中，重载可以发生在同一类中，也可以发生在由于继承而相关的不同类中。
84. java中所有的类都继承自java.lang.Object类
85. 调用一个对象的toString（）会返回描述该对象的字符串。默认情况下，它返回一个由该对象所属的类名、at符号（@）以及该对象十六进制形式内存地址组成的字符串
```java
System.out.println(Object);//隐式调用Object.toString()
```
86. 使用父类对象的地方都可以使用子类对象。这就是通常所说的多态。简单的说，多态意味着父类型的变量可以引用子类型的对象。这种变量不能够调用子类型中特有的方法。
87. 方法可以在沿着继承链的多个类中实现。JVM决定运行的时候调用哪一个。
88. 声明类型：一个变量必须被声明为某一种类型。变量的这一中类型称为它的声明类型。
实际类型：变量的实际类型是被变量引用的对象的实际类。
> 引用类型调用方法时，它所调用的方法由它的实际类型决定。这称为动态绑定。

> 动态绑定的工作机制：假设`Object o=new C1();o.method();`（中间存在着隐式类型转化）类C1是C2的子类，C2是C3的子类。。。Cn-1是Cn的子类。也就是说C1是最特殊的类，Cn是最通用的类（在java中是Object类），(如果o是C1的实例，那么他也是C2,C3.......Cn的实例),如果对象o调用一个方法method()，那么JVM回依次在类C1,C2,...,Cn中查找方法method（）的实现，知道找到为止。一旦找到这个实现，就会停止然后调用这个首先找到的实现。
89. 总是可以将子类型的实例转化为父类型的实例变量，称为向上转换，因为子类的实例永远是他父类的实例。当把一个父类实例转换为它的子类变量（称为向下转换），必须使用转换标记“（子类名）“进行显示转换。
90. 个人理解向下转换的使用：
```java
public class Test {
    public static void main(String[] args) {
        Test1 t=new Test2();
        if(t instanceof Test2) {
            Test2 t2 = (Test2) t;
            t2.function1();
        }
    }
}
class Test1{
    public Test1(){
//        this.toString1();
    }
    public  String toString(){
        System.out.println("Test1.toString");
        return null;
    }
    public void function1(){
        System.out.println("Test1.function1");
    }
}
class Test2 extends Test1{
    public Test2(){
//        this.toString1();
    }
    public  String toString(){
        System.out.println("Test2.toString");
        return null;
    }
    public void function1(){
        System.out.println("Test2.function1");
    }
}
class Test3 extends Test2{
    public Test3(){
//        toString1();
    }
    public  String toString1(){
        System.out.println("Test3.toString");
        return null;
    }
}
```
> 为了能够进行通用程序设计，一个好的经验是把变量定义为父类型，这样，它就能够接受任何子类型的值
91. 如同toString（）方法，equal（Object）方法是定义在Object类中的另一个有用的方法。Object类中的实现是使用“==”判定两个变量是否指向同一个对象。因此一般要在自己的类中重写equal()方法。
92. ArrayList对象可以存储一个对象列表。


方法|描述
--|---|--
ArrayList（）|创建一个空的列表
add（）|添加一个新的元素到该列表的末尾，或者指定下标处
clear()|清空列表中的所有元素
contains（）|如果列表中包含某一特定的元素，返回true	
get()|返回列表中指定下标位置的元素
indexOf()|返回列表中第一个匹配元素的下标
isEmpty()|如果列表为空返回true
lastIndexOf()|返回列表中最后一个元素的下标
remove()|去除列在表中的第一个元素，去除成功则返回true
size()|返回列表中元素的个数
set|设置指定下标位的元素

93. 异常处理使得程序可以处理非预期的情景，并且持续正常的处理。
94. 异常是从方法中抛出的。方法的调用者可以捕获以及处理该异常。
```java
public class QuotientWothException {
    public static int quotient(int number1,int number2){
        if(number2==0){
//            抛出的值“new ArithmeticException("Divisor can't be zero!")”称为一个异常。throw
//            语句的执行称为抛出一个异常
//            异常就是从异常类中创建的一个对象
//            当异常被抛出的时候，正常执行的流程会被中断。
//            异常被catch块所捕获，catch块中的代码得以执行以处理异常
//            之后catch块外剩下的代码得以执行
//            throw语句类似于方法的调用，但不同于调用方法的是，它调用的是catch块。
//            从某种意义上来讲，catch块就像带参数的方法定义，这些参数匹配抛出的值的类型
            throw new ArithmeticException("Divisor can't be zero!");
        }
        return number1/number2;
    }

    public static void main(String[] args) {
        Scanner input=new Scanner(System.in);
        try {
            System.out.println(quotient(input.nextInt(), input.nextInt()));
        }
//        标识符ex的作用很像方法中的参数。所以这个参数称为catch块中的参数。
//        ex之前的类型称为指定的catch块可以捕获的异常的类型
//        一个异常可以通过try块中的throw语句直接抛出，或者通过在块中调用一个可能会抛出异常的方法来抛出
        catch (ArithmeticException ex){
            System.out.println(ex.getMessage());
        }
    }
}

```

96. 异常处理最重要的优势就是将检测错误从处理错误中分理出来
97. 异常类型：
![这里写图片描述](http://img.blog.csdn.net/20170823200536497?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvZzExMDAxMTAxMA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
> * 这些异常可以分为三类：系统错误，异常和运行时错误
> * 系统错误是由java虚拟机抛出的。用error类表示。error类描述的是内部系统错误。
> * 异常是用Exception类表示的，它描述的是由程序和外部环境造成的错误。
> * 运行时异常是用RuntimeException表示的它描述的是程序的设计错误，例如，错误的类型转换，访问一个越界数组等
> * RuntimeException和Error以及他们的子类都被称为免疫异常。所有其他异常都被称为必检异常，意思是编译器会强制程序员检查并通过try-catch块处理他们
> * 在大多数情况下，免疫异常都会反映出程序设计上不可恢复的逻辑错误。


98.  异常处理器是通过从当前方开始，沿着方法的调用链，按照异常的反向传播方向找到的。
99.  java的异常处理模型基于三种操作：声明一个异常，抛出一个异常和捕获一个异常。
> 声明异常：每个方法都必须在方法头中显式声明它可能抛出的必检异常的类型。这称为声明异常。
> 如果方法没有在父类中声明异常，那么就不能在子类中对其进行继承来声明异常。
> throw关键字用于抛出异常，throws关键字用于声明异常

100.捕获异常：如果try块中的某一条语句捕获了一个异常，java就会跳过try块中的剩余的语句，然后开始查找处理这个异常的代码的过程。处理这个异常的代码称为异常处理器。
可以从当前的方法开始，沿着方法的调用链，按照异常的反向传播方向找到合适的异常处理器。从第一个到最后一个逐个的检查catch块，判断catch筷子中的异常类型是否是该语句块的异常类型。如果是，就将该异常对象赋值给所声明的变量，然后执行catch块中的代码，如果不是，就退出当前方法，将异常传递给调用这个方法的方法。继续同样的过程来查找处理器。
如果在调用的方法链中找不到对象的处理器，程序就会终止并且在控制台中打印出错误信息。

101. 从一个 通用的父类可以派生出各种异常类。如果一个catch块可以捕获一个父类的异常对象，他就能捕获那个父类的所有子类的异常对象。
102. 在catch块中异常的指定顺序是非常重要的，如果父类的catch块出现在子类的catch块之前，就会导致编译错误。
103. Throwable类中的方法：


对象|方法
--|---|--
getMessage()|返回描述该异常对象的信息
toString()|返回三个字符串的连接，异常类的全名 : getMessage()方法
printStackTrace()|在控制台上打印Throwable对象和他的调用堆栈信息
StackTraceElement[]|返回和该异常对象相关的代表堆栈跟踪一个堆栈跟踪元素的数组
104. 在异常事件中程序仍然可以执行，如果处理器没有捕获到这个异常，程序就会突然中止。
105. finally子句，无论异常是否发生，finally子句总是会被执行。
106. try-catch-finally语句执行的流程图
```flow
s=>start: 开始
e=>end：结束
code=>condition: 有无异常抛出？
try=>operation: 执行try块
finally=>operation: 执行finally块
finally1=>operation: 执行finally块
finally2=>operation: 执行finally块
catch=>operation: 执行catch块
throw=>operation: 传递异常给调用者
iscatched=>condition: 是否被捕获

s->try->code
code(yes)->iscatched
code(no)->finally
iscatched(yes)->catch
iscatched(no)->finally1->throw
catch->finally2->

```
107. 当错误需要被方法的调用者处理的时候，方法应该抛出一个异常
108. 如果异常处理器不能处理一个异常，或者只是简单的希望它的调用者注意到该异常，java允许该异常处理器重新抛出异常
109. 链式异常：和其它异常一起抛出一个异常，构成了链式异常。
110. 对java异常处理机制的理解：在try块中，根据虚拟机或者程序的处理逻辑，若发现程序执行问题，则throw出一个异常对象，这个异常对象包含了异常发生的类型，异常调用栈等信息。同时try块中的程序终止继续执行，开始在各个catch块中寻找能够处理该异常对象的catch块（就是根据catch块中的参数类型与抛出的异常对象类型是否匹配，匹配则catch成功，执行此catch块中继续执行错误处理程序，这也解释了为什么父类catch块为什么不能出现在子类catch块前面，因为子类catch块的对象也是父类catch块的对象，能够同时被父类catch块和子类catch块接受，所以要求子类catch块必须出现在父类catch块的前面，以避免造成代码处理混乱（暂时只想到这一个不良影响）），如果catch不成功，则执行本方法中的finally块（如果有的话），然后将这个异常throw给本方法的调用者，交由调用者处理这个异常。
111. File类：FIle类包含了获取一个文件、目录的属性，以及对文件/目录进行改名和删除的方法。
112. 创建一个File实例并不会在机器上创建一个文件。不管文件是否存在，都可以创建任意文件名的实例。
```java
public class TestFileClass {
    public static void main(String[] args) throws IOException {
        File file=new File("/demo");
        System.out.println(file.exists());//如果文件或者文件路径存在，返回true
        System.out.println(file.getAbsolutePath());//获取文件或者文件路径的绝对路径
        System.out.println(file.isDirectory());//file对象存在且代表一个目录时，返回true
        System.out.println(file.isFile());//file对象存在且代表一个文件时，返回true
        File file1=new File(file,"test.txt");//file为一个路径，在file路径下创建一个子路径
        System.out.println(file1.getAbsolutePath());
        System.out.println(new Date(file1.lastModified()).toString());//返回文件最后一次被修改的时间
        System.out.println(file1.isFile());
        System.out.println(file1.isAbsolute());//file1是用绝对路径创建时返回true
        System.out.println(file1.isHidden());//file1对象代表的文件是隐藏文件时返回true
        System.out.println(file1.getCanonicalPath());//和getAboulutePath()相同，除了从路径名中去除了一些亢余字符
        System.out.println(file1.getName());//返回file对象代表的目录和文件名单的最后文件名
        File file2=new File("fileTest/test.txt");
        System.out.println(file2.exists());//false
        System.out.println(file2.mkdir());
        System.out.println(file2.exists());
        System.out.println(file2.getAbsolutePath());
    }
}

```
113. 使用Scanner类从文件中读取文本数据，使用PrintWriter类向文本文件中写入数据。
114. 父类中定义了相关子类的共同行为。接口可以用于定义类的共同行为（包括非相关的类）
115. 抽象类：抽象类不可以用于创建对象。抽象类可以包含抽象方法，这些方法将在具体的子类中实现。
116. 包含了抽象方法的类是抽象类，抽象类中可以有非抽象方法。
117. 抽象类的构造方法定义为protected，因为它只能够被子类使用。
118. 抽象方法可以让虚拟机在运行时决定使用哪一个子类实现。
119. 关于抽象类的几点说明：
>* 抽象方法不能包含在子抽象类中，如果抽象类的子类不能实现父类的所有抽象方法，那么子类也应该定义为抽象的。
>* 抽象方法是非静态的
>* 抽象类是不能够使用new操作符来实例化的。但是仍然可以定义它的构造方法，这个构造方法在他的子类的构造方法中使用。
>* 包含抽象方法的类必然是抽象的，但是可以定义一个不包含抽象方法的抽象类。在这种情况下同样不能使用new操作符创建抽象类的实例。
>* 子类 可以覆盖父类的构造方法并将它定义为abstract.
>* 即使子类的父类是具体的子类也可以是抽象的。

117. UML类图使用：
>* 抽象类、抽象方法使用斜体表示
>* 接口名字和方法使用斜体，并且接口名字出应注明"《interface》",
>* 可见性修饰符表示：private（-），public（+），protected（#）
>* 静态方法，静态成员加下划线表示
>* 父类的方法在子类中通常是被忽略的
>* 实线和空心三角形用于表示指向父类
>* 虚线和空心三角形用于表示指向接口

118. 接口：接口是一种与类类似的结构，只包含常量和抽象方法。
119. 类和接口之间的关系成为接口继承
120. 接口中所有的数据域都是public static final，而且所有的方法都是public abstract，所以java允许忽略这些修饰符。
121. 这些东西真的不会损失的么