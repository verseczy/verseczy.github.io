记得当初从Pascal转C的时候看了matrix67大神写的<a href="http://www.matrix67.com/blog/archives/215">C语言速成手册</a>。虽然内容很基础（只包括应付NOIP的东西：基本语句、数据类型、运算符等等，不包括面向对象部分），但是很适合已经熟练掌握过一门编程语言的人快速入门新语言。感觉这种速成手册的意义就在于能使读者先快速上手一门陌生的编程语言，其他的东西完全可以在实践当中继续学习。

寒假要做一个小project，感觉用Java可能会更加简洁一些。不过目前还没找到一本类似的Java速成手册（市面上的大部分都是给码农用的大部头），于是打算自己自制一个，也当作是Java初学笔记了。

仿照M67大神分成如下几个单元：

1.基本数据类型、输入输出、函数（方法）

2.条件、循环、语句

3.简单的类、字符串


#编程环境：eclipse

>

#Part 1


###Java中常用的数据类型：

整型（表示范围由大到小）：long、int、short、byte

小数（精度范围由大到小）：double、float

布尔型：boolean

单个字符：char            char ch='a';

声明基本数据类型举例：

<pre><code>long num=23333;</code></pre>

对于整型和小数，Java里有两个特殊值代码分别表示最大值和最小值：MAX_VALUE和MIN_VALUE

（作用相当于C语言里自己#define inf 0x3f3f3f3f）

用法如下：

<pre><code>int x=java.lang.Integer.MAX_VALUE;</code></pre>



###Java声明数组：

一维数组：

<pre><code>int score[];
score=new int[1000];
</code></pre>

二维数组：
<pre><code>int score[][];
score=new int[100][100];
</code></pre>

求数组的长度：
<pre><code>int score[]
score=new int[10][20];
int a=score.length;          //return 10
int b=score[1].length;       //return 20
</code></pre>

>

###Java里的方法：相当于C/C++里的函数

方法也可以重载，和C++里一模一样。

方法的定义：

<pre><code>public static void add(int a,int b)
{
    System.out.println(a+b)
}
//以上为无返回值（void），打印a+b的方法
public static int add(int a,int b)
{
	return (a+b);
}
//以上为返回a+b的值的方法
public static int amax(int a[])
{
	int tmp=a[0];
	for (int i=0;i<a.length();i++)
		if (tmp<a[i])	tmp=a[i];
	return tmp;
}
//数组作为方法的传入参数
</code></pre>

###例：POJ1000，最简单的A+B程序（多组输入）
<pre><code>
1 import java.util.Scanner;
2 public class Main {
3    public static void main(String[] args)
4    {
5		Scanner in=new Scanner(System.in);
6		while (in.hasNextInt())
7		{
8			int a=in.nextInt();
9			int b=in.nextInt();
10			//a=a+b;
11			System.out.println(a+b);
12		}
13	}
14 }
</code></pre>

###解释：

####Line 1.
用于包括Scanner类的Java.util包。相当于C++里面的#include<...>。

一般也可以这样写：import java.util.*，这样就把包里面所有的类都include了。

<pre>
JDK常见的包：

1.java.lang （默认已自动包含）
  包括Java的核心类，如String、Integer、Math、System、Thread
2.java.io
  包括提供输入输出功能的类
3.java.util
  包括一些实用工具类，如Scanner、日期日历函数等
</pre>

####Line3
main是每个Java程序都有的主类

public表示公有，static表示静态，void表示无返回值。

以上概念的含义和C++里面完全一样

####Line 5

创建一个Scanner类的对象in，用于输入。
可参考这里：<p> http://a475334705.iteye.com/blog/1636458 </p>

####Line 11

打印并换行。相当于cout<<....<<endl。

如果不希望换行，那么这样写：System.out.print(".....");

还可以这样用：
<pre><code>System.out.println("a+b="+(a+b));
其中(a+b)外面的那个加号表示连接两段字符串
输入：6 7
输出：a+b=13</code></pre>



#Part 2

Java中的逻辑运算符（如大于、小于、不等于、等于、and、or、not...）与C完全一样。

sum++、ans--这样的递增、递减运算符也和C完全一样。

###Java中的if语句：
<pre><code>
if (a==1)
{
	System.out.println("one");
}
else if (a==2)
{
	System.out.println("two");
}
else
{
	System.out.println("233333");
}
</code></pre>

###Java中也可以用条件运算符，和C++里面完全一样。
<pre><code> int max=(a>b)?a:b; </code></pre>

###Java中的while语句：
<pre><code>
int sum=0;
while (i<=10)
{
	sum+=i;
	i++;
}
</code></pre>

###Java中的for语句：
<pre><code>
int sum=0;
for (int i=1;i<=10;i++)
	sum+=i;
</code></pre>

###Java中的switch语句：
<pre><code>
char opr='+';
switch (opr)
{
	case '+':
		c=a+b;
		break;
	case '-':
		c=a-b;
		break;
	default:
		System.out.println("shen me gui");
}
</code></pre>

###Java中的Do-while语句：
<pre><code>
int i=0,sum=0;
Do
{
	sum+=i;
	i++;
}while (i<=10);
</code></pre>

###Java中的break、continue语句：与C完全一样。

break跳出循环体不再执行循环，continue跳出本次循环开始下一次循环。



#Part 3

###例：在Java中声明一个类

<pre><code>
1  package helloworld;
2  
3  class Person
4  {
5	int pubage;
6	private String name;
7	private int age;
8	public Person()
9	{
10		System.out.println("2333333333");
11	}
12	private void talk()
13	{
14		System.out.println("My name is "+name+" , I'm "+age+" years old. "+pubage);
15	}
16	public void say()
17	{
18		this.talk();
19	}
20	public void setName(String str)
21	{
22		name=str;
23	}
24	public void setAge(int a)
25	{
26		age=a;
27	}
28	public String getName()
29	{
30		return name;
31	}
32	public int getAge()
33	{
34		return age;
35	}
36 }
37
38 public class text
39 {
40	public static void main(String[] args)
41	{
42		Person p=new Person();
43		p.setName("Mo Ha");
44		p.setAge(80);
45		p.pubage=2333;
46		p.say();
47	}
48 }

//输出结果：
2333333333
My name is Mo Ha , I'm 80 years old. 2333
</code></pre>

###解释：
Line 3--36定义了一个类Person。Java中类名通常第一个字母大写。

Line 5--7：类的成员变量可以是公有的，也可以是私有的。同C++

Line 8：自定义的类的构造函数

Line 18：同C++里面的this指针

Line 12--35：类的成员函数。和C++一模一样

Line 42：声明了一个Person类的对象p

####对象的比较：
<pre><code>String s1=new String("java");
String s2=new String("java");
String s3=str2;
boolean a1=(s1==s2);
boolean a2=(s2==s3);
boolean a3=(s1.equals(s2));
boolean a4=(s2.equals(s3));
//结果：a1=false	a2=true
//	a3=true		a4=true
</code></pre>

==：比较内存地址

equals：比较类的内容


###字符串String: 在Java里就是一个类。


