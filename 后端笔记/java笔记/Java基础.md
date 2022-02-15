## 一.Java入门

#### 1.Java是什么?

Java是编程语言



c--管理的是底层

Java--安卓开发/大数据分析平台

#### 2.java的发展历史

jvm--java虚拟机,只要安装了这个环境平台,在任何条件下都能运行java程序(等于不要看操作系统,屏蔽了底层系统差别)

![image-20210515235926306](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515235926306.png)



2.1JDK JAVA DEVELOPMENT KIT

2.2JRE JAVA ROUNTUME ENVIRONMENT(运行环境)

2.3JVM JAVA VIRTUAL MACHINE(虚拟机)

#### 3.安装开发环境

##### 3.1 JDK下载和安装

- 百度搜索JDK8,下载

- 同意协议

- 下载对应电脑系统的版本

- 记住安装路径

- 配置环境变量

  1. 我的电脑-右键-属性-高级系统设置-环境变量

  2. 环境变量-在系统变量中新建JAVA_HOME变量值输入对应的路径

     ![image-20210516165132235](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516165132235.png)

  3. 配置两个path(系统变量中)

     ```
     %JAVA_HOME%\bin
     
     两个百分号代表引用地址
     
     %JAVA_HOME%\jre\bin
     
     jre是java运行时环境
     ```

     

  4. 新建classpath
  
     ```
     CLASSPATH
     
     .;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar
     ```

     

  5. 检查JDK是否安装成功(查看java的版本)
  
     ```
     在cmd中输入
     java -version
     ```

     ![image-20210516165737402](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516165737402.png)
  
     

##### 3.2 卸载jdk

		- 在环境变量中找到javahome,找到path下关于java文件删除jdk
		- 之后删除环境变量中的JAVA_HOME
		- 最后cmd中java -version检查

##### 3.3 java文件夹

![image-20210516170251266](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516170251266.png)

#### 4.第一个java文件

##### 4.1 创建java文件

- 先新建一个java文件

```java
public class hello{
    public static void main(String[] args) {
        System.out.print("hello,world");
    }
}
//注意 文件名hello需要和 类名hello一致
//每个单词大小写区分,java是很严格的
//符号需要英文符号,比如 ;
```

- 在控制台输入javac +文件,会编译出对应名称的class文件(文件名.class)

![image-20210516173340917](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516173340917.png)

##### 4.2 java程序运行机制

- 编译型:把计算机源程序变为可以执行的代码(一次性完成),负责编译的程序称为编译器(c,c++)

- 解释型:根据需要逐句的解释源程序,边执行边解释,负责解释的程序叫解释器(JavaScript)
- 而java介于两者之间,因为它**预编译**了字节码文件(但不是编译型直接生成的机械码文件),字节码文件则会放到虚拟机的装载器,用**解释**的方法告诉操作系统

![image-20210516190839801](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516190839801.png)

#### 5.java的开发工具-IDEA

#### 5.1 ide是什么

集成开发环境（IDE，Integrated Development Environment ）,用于提供程序开发环境的应用程序.

一般包括代码编辑器、[编译器](https://baike.baidu.com/item/编译器/8853067)、[调试器](https://baike.baidu.com/item/调试器/3351943)和[图形用户界面](https://baike.baidu.com/item/图形用户界面/3352324)等工具。

#### 5.2 idea的使用

###### 1.新建模块![image-20210516193247973](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516193247973.png)

###### 2.在idea中设置java的环境和版本

###### 3.修改idea中文字颜色

​	idea-setting-editor-color-scheme-java

###### 4.配置java地址(如果爆红)

![image-20210516201308516](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516201308516.png)

![image-20210516201434325](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516201434325.png)



#### 5.3 idea 的界面栏

![image-20210518171256344](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518171256344.png)



####  5.4 常见问题与操作

##### 1.project项目栏界面

![image-20210518171832259](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518171832259.png)

##### 2.如何让package分层显示

![image-20210518172107921](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518172107921.png)

##### 3.优化idea使用

- 修改背景色![image-20210516202246826](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516202246826.png)

##### 4.如何重命名文件

refactor :重构 

![image-20210518172908889](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518172908889.png)

##### 5.package的命名规范

```java
个人发起项目(公开开源项目)
    indi.作者名称.项目名称.模块名称
    
个人练习项目(不公开的,学习用)
    pers.作者名称.项目名称.模块名称
    
公司项目
    com.公司名.项目名.模块名
```

##### 6.debug模式操作

![image-20210518222106589](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518222106589.png)

##### 7.java常见报错

###### 7.1 java.lang.ArrayIndexOutOfBoundsException 数组越界

产生原因:调用了超出数组范围的index

##### 6.idea代码书写技巧

###### 	1.psvm + enter

```java
psvm + enter

public class hello {
    public static void main(String[] args) {
    //直接生成  
    }
}

```

![image-20210516202739772](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516202739772.png)

---

###### 2.sout +enter

```java
sout + enter
    System.out.println();
```

###### 3.Ctrl +d 

```java
ctrl D
    复制当前行到下一行
```

###### 4.a++ ++a 

```java
int a = 3;
int b = a++; // a++  a =a + 1; 
//先执行 b = a(3)
//再给a赋值 a = a++ = 3+ =4
//此时输出a a=4

int c = ++a; // c = 5
//先给a 赋值 a = a++ =4+1=5;
//再给c 赋值 c =  a = 5;

```

###### 5.长按ctrl + 双击 (获取类的详细信息)

```java
长按ctrl + 双击
    点击structure 查看方法
```

###### 6.ctrl + alt + shift +s (打开当前项目结构)

​	或者file ->project structure

![image-20210518195847008](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518195847008.png)

###### 7.ctrl alt L 全局自动缩进*

###### 8.alt enter 创建对象/自动生成类方法*

```java
new demo4() +alt enter 创建对应对象
    demo4 demo4 = new demo4();
```

```java
  // alt + insert enter

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }
```

###### 9.ctrl + h 在父类查看继承树

```java
ctrl + h 
```

###### 10.ctrl 长按 再点击,可以跳转对应代码*

###### 11.如何调整文件所在目录

ctrl+左键点击文件

![image-20210522230138413](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522230138413.png)

##### 7.idea操作规范

- 点击绿色三角测试运行![image-20210516203216647](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516203216647.png)
- 变量的输出必须初始化![image-20210516205404741](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516205404741.png)
- int 占4个字节 大概+-21亿
- 调试图标

![image-20210516220302310](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516220302310.png)

- 进制的表示

| 2进制 | 8进制0 | 10进制 | 16进制0X |
| ----- | ------ | ------ | -------- |
| 1010  | 012    | 10     | 0xA      |

- java 判断语句的书写格式

```java
 // 布尔值扩展
        boolean flag = true;
        if(flag==true) {

        } //新手x

        if(flag){
        //这两种写法是等价的,默认进行true判断
        }
	//使用第二种判断方法!!
```



- 阿里巴巴规范手册
- 点击structure可以查看类下属的属性,;方法
- 双击类

#### 5.5intelli IDEDA 的发展

> JetBrains旗下的产品

- IntelliJ IDEA偏重于Java开发(但是插件可以支持WebStorm和PhpStorm所有的功能)
- PhpStorm侧重于PHP开发
- WebStorm侧重于JS开发
- RubyMine侧重于Ruby和Rails开发
- PyCharm侧重于Python和Djanjo开发

#作为前端开发来说:WebStorm与IntelliJ IDEA相比，功能少，集中于JS开发这一块，更加轻量级，新项目配置起来更简单。

## 二.java基础

#### 1.注释,标识符,关键字

##### 1.1注释

​	名称:comments

​	定义:类似上课写的笔记,帮助之后阅读代码

​	分类:

	- 单行注释

```java
//单行注释 line comments
```

 - 多行注释

```java
/*
	多行注释 block comments
	多行注释
*/
```

 - 多行注释

```java
/** 开头
* @Description helloworld
* 结尾
*/
```

##### 1.2标识符

​	   定义:表示符是程序员定义的名称,给java组成部分名字

​	   分类:

- 变量名

- 类名

- 函数名(包括方法名)

- 参数名

  

  标识符命名规则(强类型语言java)

  ```java
          String Ahello = "允许大写开头";
          String ahello = "允许小写开头";
          String _hello = "允许下划线开头";
          String $hello = "允许美元开头";
  //只限制首字母,之后可以加数字
  //其他 数字/#/特殊符号/ 都会报错
  //关键字也不允许使用为开头
  //大小写敏感!!
  ```

  ---

  

##### 1.3关键字

​	定义:系统定义好的具有特定功能的单词

![image-20210516203725792](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516203725792.png)

##### 1.4 字面量

​	字面值是指在程序中无需变量保存，可直接表示为一个具体的数字或字符串的值

```java
int b =3 ;
int a = b * 2 ; //2 就是一个字面量,它本身就是具体的值

```



#### 2.数据转换

​	java是一种强类型语言(变量的使用必须严格符合规定,需要先定义变量类型才能使用,不进行转换就永远是定义类型)

​	相反javascript就是弱类型语言,他可以存储任意类型的数据并直接使用

​	#分类

	- 基本类型(primitive type)

```java
      //八大基本数据类型
        //1 整数
        int num1 = 10;
        byte num2 = 127; //最大127,一个字节
        short num3 = 25;
        long num4 =54L;

        //2小数
        float num5 = 2.3f; //需要加f
		//少使用浮点数进行比较
		//少使用浮点数进行比较
		//少使用浮点数进行比较
        double num6 =3.1456;

        //3字符
        char name ='a';
        //4字符串(类)
        String charname = "nice nature";

        //5.布尔值
        boolean flag = true;//false
```

	- 引用类型(reference type)
	- ![image-20210516205129912](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516205129912.png)

#### 3.类型转换

##### 	3.1强制类型转换的原理

​	本质是转换为Unicode对应编码值

​	Unicode表示方法

```java
char c3 = '\u0061'; 
//会输出 a
```



![image-20210516221014350](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516221014350.png)

##### 3.2转义字符

```java
//转义字符
        // \t 制表符
        // \n 换行符
```

##### 3.3运算和转换

​	在运算中,不同类型的数据线转换为同一类型,再进行运算

​	方法 数据前加 (类型名称)变量名

###### #1.强制转换/自动转换

```java
1.强制转换//(类型名称)变量名 高---低
int i = 128;
byte b =(byte)i; //内存溢出,因为转换超过了允许范围

2.自动转换 // 低--高
double b1 = i;

/*
1.不能对布尔值进行转换
2.不能把对象转换为不相干的类型
3.再将高容量变为低容量时要强制转换
4.转换可能会内存溢出/精度问题
*/
```

###### #2.精度问题

```java
//精度问题
 System.out.println((int)23.7); // 23
 System.out.println((int)-45.89f); // -45
```

###### #3.内存溢出问题与解决

```java
//内存溢出问题
//jdk7新特性 数字(尤其大数字)之间可以用下划线分割,不影响输出
int money = 10_0000_0000;
int year = 20;
int total = year * money;  // 计算结果溢出了为-1474836480
System.out.println(money); 

long total2 =year * money; // 不行,因为右边先计算再赋值.是两个int计算完之后的结果,还是int,显示是溢出的负值,所以等于还是给 total2赋值错误的结果

long total3 = money*((long)year) // 正确解决方法:先把一个数转换long类型(先扩大一个数范围),再计算,就能得到正确结果
```



#### 4..变量,常量

##### 4.1变量的基本概念	

​	定义 变量就是可以变化的量

​	它的组成为 数据类型 变量名 = 值;

​	它的要素包括 变量名,作用域,变量类型

![image-20210516214225825](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516214225825.png)

###### 	@1.变量的命名规范

![image-20210516235638193](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516235638193.png)

##### 4.2变量的分类

```java
       class Person {
           public int age = 10 // 定义在类中的字段
       } //类成员变量

        public void method(){
            int i =0; // 局部变量
        }
```



- 类成员变量

  定义在类{}中

- 局部变量

  定义在方法中,方法的形参,构造器形参,构造器内部变量,代码块

##### 4.3常量的概念



![image-20210516235430534](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516235430534.png)

##### 4.4变量的作用域

##### 4.5初始化值

尤其注意形参实在函数方法调用时才初始化的



![image-20220108200536759](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220108200536759.png)

#### 5.运算符

5.1 位运算

```
  a= 0011 1100
  b= 0000 1101
   ---------------------------
  a&b= 0000 1100 (同1为1 ,其余为0)
  a|b= 0011 1101 (同0为0 ,其余为1)
  a^b= 0011 0001 (相同为0 ,其余为1)
  ~b = 1111 0010 (取反)
      
  位运算的拆分
  2*8 最快计算方法 拆为2*2*2*2
  
  
 >> << 左移/右移
 0000 0000 0
 0000 0001 1
 0000 0010 2
 0000 0011 3
 0000 0100 8
 0001 0000 16
 << 左移*2
 >> 右移/2
```

5.2 扩展运算符

```java
int a =10;
int b =20;
a+=b a=a+b
a-=b a=a-b 
    
//字符串连接符号 + 
    加法运算中,只要有一个字符串,字符串之后的数据转换为字符串形式
    (""+a+b)// 等于1020 ,在字符串后面10和20变为字符串拼接
    (a+b+"")// 等于30 在字符串前面,数值运算依旧正常进行,但最后还是字符串形式输出
   
```

5.3三元运算符

```java
?:
x?y:Z
    int score;
    String type = score<5?"不及格":"及格";
    if(x)
  		return y
    else
        return z
        
```



#### 6.包机制,javaDoc

##### 6.1package

 包的本质就是文件夹

![image-20210518153135086](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518153135086.png)

```java
注意:
import com.kuang.base.*;
//*为通配符,他会导入这个包下所有的类

//1.导入的包import 必须在package之下.否则会报错
//2.调用原生的函数DATE等需要导入对应的类
//3.package 放在句首
//4.包名设置一定要规范,倒置,放置命名空间重置
```

##### 6.2 javaDOC

#作用:用来生成自己的API文档(自己的类)

![image-20210518154406126](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518154406126.png)

## 三.java流程控制

#### 1.用户交互scanner

##### 1.1 Scanner 对象

```java
#构建一个scanner 对象
Scanner s =new Scanner(System.in);


#调用接收方法:
scanner.next()
scanner.nextline()
    
  例 :
 	String str = scanner.nextLine();//用来接收用户的输入存储到变量中

#两者区别
    #next()
    1.一定要读取到有效字符后才可以结束输入(必须要输入,否则程序不停止)
    2.如果输入遇到空白(空格),会自动去掉,也就是空格之后全部舍去了
    比如hello world 只会得到hello
    3.但是有效字符之前的空格会被自动无视
    比如  hello world 输出hello hello前面的空格被无视
    
    #nextline()
    1.以回车符号为结束符,回车前的所有字符都被接收
    2.可以获得空白
```



java.util.Scanner 通过java类来获取用户的输入



##### 1.2 scanner 进阶

![image-20210518175313331](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518175313331.png)

1. hasNextInt()方法

   ```java
   #特性
       1.首先hasNextInt()方法返回的结果是布尔值
       true和false
       //System.out.println(scanner.hasNextFloat()); 输出为true和false
   	
       //这也会为什么它会被用作if()判断语句中条件的原因
       
       2.  float f = 0.0f;
       	System.out.println("请输入小数");
           if(scanner.hasNextFloat()) {
              	System.out.println(scanner.hasNextFloat());
               f = scanner.nextFloat();
               System.out.println("小数数据:" + f);
           }
           else {
               System.out.println("输入非小数");
               System.out.println(f);
           }
   
   		/* if(scanner.hasNextFloat()的作用只有判断
              数据接收和赋值是块中的 f = scanner.nextFloat();语句执行的
              
              
              因为当输入 "非小数"时,else显示f结果为0.0 还是原来的值,也就是并没有被赋值,显然判断语句没有赋值作用
              
              当输入0.5时,f输出为0.5,这表示确实是f = scanner.nextFloat()接收了数据,并且给f进行赋值
             
           */
   ```

2. nextDouble()方法

```java
#nextDouble() 
    //用来接收用户输入的double类型数据,
    //本质上为一个容器变量,调用它等价于调用接收到的数据
    //它返回的也是double类型数据,这和hasnextdouble()返回布尔值有着本质区别
    
       double x = scanner.nextDouble();
```



#### 2.顺序结构

​	#最简单的算法结构,从上往下顺序执行

​	#基本的结构

![image-20210518193028479](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518193028479.png)



#### 3.选择结构

##### 3.1ifd单选结构

​	#条件成立执行{}内容,否则跳过该语句

![image-20210518193150233](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518193150233.png)

##### 3.2 if双选择结构

​		#条件成立执行i后{}内容,失败执行else后内容

​		#二者必取1

![image-20210518193649267](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518193649267.png)

##### 3.3 if多选择结构

​		#if else if 

![image-20210518193904365](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518193904365.png)

##### 3.4 switch 多选择结构

​		#匹配一个值,然后检查是否有break来判断继续输出

![image-20210518195107436](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518195107436.png)

###### 		#判断分支为字符串 (java 7特性 )

```java
public class demoswitchstring {
    public static void main(String[] args) {
        String name ="关羽"; 

        switch (name) {//可以用字符串做条件判断
            case "张飞":
                System.out.println("张飞");
                break;
            case "关羽":
                System.out.println("我是关羽");
                break;
            case "赵云":
                System.out.println("赵云");
                break;
            case "黄忠":
                System.out.println("黄忠");
                break;
            default:
                System.out.println("马彩虹");
        }
    }
}

//字符串判断的本质还是数值判断,使用hash值进行判断

//学会查看class文件,反编译
```

![image-20210518200348694](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518200348694.png)

​		#判断分支,如果和分支值相等就执行对应选项,减少了很多if的判断流程

​	![image-20210518194156987](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518194156987.png)



###### 		#case 穿透问题

~~~java
//如果case选项中没有break,它会一直执行,知道break为止
    
 public class demoswitch {
    public static void main(String[] args) {
        char grade = 'c';

        switch (grade){
            case'a':
                System.out.println("优秀");
                break;
            case 'b':
                System.out.println("良好");
            case 'c':
                System.out.println("普通");
            case 'd':
                System.out.println("加油");
            case 'e':
                System.out.println("不合格");
            default:
                System.out.println("请正确输入");
        }
    }
}

// 上例中由于c选项后面没有break
//所以会输出 c d e f default内所有选项(或者说按顺序执行到break为止)
普通
加油
不合格
请正确输入

//所以保证break要加上,确保分支的独立性
~~~



#### 4.循环结构

 #条件为真,继续循环,条件不满足,循环终止

4.1 while循环

#先判断再执行,如果开始就不满足条件则不会进行循环

4.2 do while循环

#最少执行一次,即使不满足条件循环

#### 5.break#continue

#### 6.练习



## 四.java方法

#### 1.方法是什么

例 : system.out.printInt();

​      类.对象.方法

​	调用system类中 标准输出对象out 中的printInt()方法

##### 1.1方法特征

- 方法是语句的集合,他们在一起完成一种功能

- 方法包含于**类**或者**对象**中

- 方法在程序中被创建,在其他地方被引用
- 原子性 :一个方法只解决一个问题

#命名规则 : 驼峰法



#### 2.方法的定义与调用

​		java中的方法类似其他语言中的函数-------<font color=red>是一段用来完成特定功能的代码片段</font> 

##### 2.1方法的组成

方法一定有返回值类型!! 它没有返回值就写void

```java
访问修饰符 返回值类型 方法名(参数类型 参数名,参数类型 参数名)
{	
	方法体
	return 返回值;
}

// 有返回值
	public String getName()
    
// 没有返回值
    public void clear()
```

```java
  // 不能在一个方法内部再声明另一个方法
  public void clear(){
   
   	public String getName() {
   	
   	}// 不可以这么声明
   	
   }
```



- ###### 权限修饰符(可选)

  告诉编译器如何调用该方法

  它定义了该方法访问权限

  例:public

- ###### 返回值类型(必须)

  方法可能会有返回值. 

  #return value type 是方法返回值的数据类型.

  - 如果方法要返回数据的话,需要return 语句并且定义好返回值的-数据类型(写了就一定要返回值)

  - 如果方法只执行固定操作不返回数据的话,用**void**表示这一情况.
  - 注意:

  ```java
  // 在条件判断中终止方法,或者跳出循环终止方法
  
  public static int max(int a, int b) {
          int result = 1 ;
          if(a>b){
              result = a;
          }
          else if(a<b){
              result = b;
          } else {
              return 0; //用return在提前终止方法/或者循环
          }
          return result;
      }
  //直接设置一个result 变量来用于输出
  ```

  

- ###### 方法名(必须)

  方法的实际名称

- ###### 参数类型(可选)

  参数类似占位符,因为可能需要接收传递来的数据,所以提前声明参数(形参).

  传递来的实际值,被称为实参(变量).

  方法本身可以不包含参数不进行交换,所以是可选的:比如main()

  #参数分类

  - 形式参数 : 在方法被调用时,提前声明用于接收外界输入的数据
  - 实参:调用方法时实际传递给方法的数据

- ###### 方法体 {}

  完成某一功能实际的代码语句

  

  ##### 2.1方法的组成

  对象名.方法名(实参列表)

  - 当方法返回一个值时,方法通常被**当做一个值**

  ```java
  int larger = max(30,44);
  // 但是一般用变量接收
  
  System.out.println(max(a,b));
  ```

  

  - 当方法返回值为void ,方法调用一定是一条语句

  ```java
  System.out.printInt("hello");
  //.printInt() 调用方法
  ```

  ##### 2.3 值传递/引用传递

#### 3.方法重载

##### 	3.1定义

同一个类中运行同名函数,但是接收的参数个数或者参数类型不同

![image-20210518234316452](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210518234316452.png)

​	重载:在相同的类中,有相同的函数名称,但是形参不同

| 类型                        |               |
| --------------------------- | ------------- |
| 方法名称                    | 一定相同      |
| 参数列表 个数/类型/排列顺序 | 必须不同      |
| 返回类型(都返回int也可以)   | 可以相同/不同 |
| 单纯方法类型不同不是重载    |               |

##### 	3.2为什么需要方法重载?

```
#因为方法的数据类型是固定的,所以如果想用其他数据类型执行同样功能就不得不再写一个几乎一模一样(但是处理数据对象不同的方法)

比如比大小,一个比整数int 一个比双精度 double
```

java只有值传递

#### 

#### 4.命令行传参



#### 5.可变个数的形参

```java
    //1.原因:当传入的参数数目不确定时,这意外要写很多很多重载方法,显然是不合理的
    public void method1() {
    }

    public void method1(int a) {
    }

    public void method1(int a, int b) {
    }

    public void method1(int a, double b) {
    }

    //2.解决方法:可变参数/不定项参数
    //3.写法  参数类型... 参数名称
    public void method(double... a) {
    }

    public void method(int b, double... a) {
    }
    //4.注意事项
    /**
     * 1.一个方法只能指定一个可变参数
     * 2.可变参数必须是 方法的最后一个参数
     * 3.所有普通参数必须在可变参数之前
     */
```



#### 6.递归*

递归本质就是自己调用自己

递归结构

* 递归头 什么时候不调用自身(没有会进入死循环)
* 递归体 什么时候调用自身方法



```java
public class demo4 {
    public static void main(String[] args) {
        //阶乘
    }

    public static int f(int n){
        if(n==1) {
            return 1;
        }else {
            return n*f(n-1);
        }
    }
}

每次都留有f(n-1)存在,所以需要继续计算,一直到f(1),或者一直到能够返回具体的结果
    
    边界条件:f(1) = 具体值
    前阶段 :当参数不等于1时就需要不断调用自身直到边界
    返回阶段:通过计算到边界,再回代具体值,到最开始的main目标输入n
```

![image-20210519153257399](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519153257399.png)

但是递归非常的占内存,能不用就不用,因为每调用一次就占用一次方法,非常的占据资源和时间

## 五.数组

#### 1.数组概述

#定义 : 数组是 **相同数组类型** 的有序集合

数组元素:数组中的每一个数据被称为一个数组元素,使用数组下标来访问他们

数组下标:从0开始,数组长度从1开始,length = index+1

#数组可以作为方法的参数

methods(int[] arrays);

#### 2.数组声明创建

##### 2.1数组的声明

```java
#1 类型[] 数组变量名;  //推荐方法

#2 类型 数组变量名[];


比如 int b; 定义存储一个int数据的变量
    如果加上[]
    int[] b; 那就变成存储一组int数据的变量(数组)了,这就是[]的作用
```

##### 2.2 数组的创建

```java
   //数组变量名 = new int[数组最大容量个数];
        nums = new int[10];
	// 这里面可以存放10个int类型数据,也就是设定数组最大长度为10

//1.创建之后才分配了内存空间(声明不分配)
//2.数组下标的合法区间 [0,length-1],越界就会报错
//3.
```

![image-20210519155226250](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519155226250.png)

##### 2.3数组元素赋值

```java
num[0] = 1;
num[1] = 2;
num[2] = 3;
num[3] = 1;
num[4] = 2;
num[5] = 3;
如果不赋值则会保留默认值,比如0,null,''等
    
    for(i=0 ; i < num.length i++) {
        
    }
```



##### 2.4 java 内存分析

​	java将内存划分为两种:一种为堆内存,另一种为栈内存

​	stack 栈 heap 堆

​	特点:

- java自动管理堆栈,程序员不能直接配置(不同于c++)
- java基本数据类型有8种,即int, short, long, byte, float, double, boolean, char(**注意，并没有string的基本类型**)

数组本身是引用类型,存放的具体数据在堆中



![image-20210519160429242](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519160429242.png)![image-20210519160457882](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519160457882.png)

![image-20210519154200630](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519154200630.png)

##### 2.5 数组三种初始化状态

```java

        //1.静态初始化 创建 +赋值
        int[] a = {1,2,3,3,4,5,};
        demo1[] demos = {new demo1(),new demo1()};

        System.out.println(a[0]);
        //2.动态初始化 后期手动赋值
        int[] b = new int[10];
        b[0] = 10;

        //3.数组默认初始化
        //数组也是一种引用类型,它的元素相当于类的实例变量
        //所以数组一经分配空间,里面的每个元素也按照实例变量被隐式初始化
```

##### 2.6数组的特点

- 数组的长度一般是固定的,一旦创建不能改变
- 元素类型必须相同,不允许混合
- 元素可以为任何类型,引用和基本类型都可以
- 数组属于引用类型,本身可以看成对象.所以无论保存声明类型数据,数组对象本身是在**堆**中的

##### 2.7 数组的for -each循环

```java
//#专门用来输出数组内容
int[] array = {1,2,5,3,99,5};

//array.for enter 生成增强型for循环
//jdk1.5 但是无法取到下标
 for (int i : array) {
   System.out.println(array); //直接就输出数组
     }
```



#### 3.数组声明

#### 4.多维数组

#### 5.Arrays类

##### 5.1 java数组工具类 java.util.Arrays

```java
int[] a ={1,5,6,999,5}; // 定义了数组a

Arrays.toString(a); //调用array类中的tostring()方法,其中方法的实参是数组a

//因为所有数组都是一个对象,属于Array类的对应对象

```

##### 5.2冒泡排序



#### 6.稀疏数组

#### 六.面向对象(oop)

以类的方式组织代码,以对象的方式组织(封装)数据

对象是具体的,类是抽象的

类是对一类事物整体的描述和定义,它是抽象的,它是一个模板



对象通过引用来操作的,说白了是指向堆中实际对象内容数据的地址



封装

继承,\

多态

##### 1.方法的定义

return,结束方法

break结束循环,跳出switch

continue 结束一次循环

##### 2.方法的调用 static

分类

static 静态方法 :

```java
//静态方法调用
public class Student {
public static void sayHi() {
      
}
}
Student.sayHi(); 
//直接  类名.方法名
```

非静态方法

```java
//非静态方法调用
public class Student {
public void sayHi() {
      
}
}
对象类型  对象名         对象值
Student studentclass = new Student();
studentclass.sayHi();

//需要实例化这个类,也就是建立这个类的对应对象
```

实际传递的参数类型要一致,java参数的传递是值传递





new关键字创建对象,类里面不要main方法,一个项目只存在一个main方法

属性/方法两种组成

类需要实例化,它实例化后会返回一个自己的对象,new创建对象时,除了分配内存空间外,还会给创建好的对象进行默认的初始化以及对类中构造器的调用

2. ##### 构造器

   nwe创建一个新对象,每次对象都是全新的完全不同的

一个类就算声明也不写也会在.class文件中存在一个方法(隐式无参)

- 显示的定义构造器
- 可以实例化初始值
- public person() {}
- 1.使用new关键字,必须要有构造器,本质就是调用构造器
- 2.一旦定义了有参构造,,无参构造必须显式定义才能使用
- 3.构造器用来初始化值
- alt + insert 生成构造器(默认生成有参)
- 方法名必须和类名相同,没有返回值

3.特性

3.1封装

高内聚,低耦合,功能内部解决,不允许外部干涉

属性私有 get/set



封装主要用在属性

```java
package com.hezu.train.methods;
//封装的意义
/**
 * 1.提高程序安全性
 * 2.提高可维护性
 * 3.统一接口
 * 4.隐藏代码实现细节,黑箱系统,只需要专注功能
* */
//类 private:私有
public class student {
    //1.属性私有
    //名字
    private String name;
    //学号
    private int id;
    //性别
    private char sex;
    //2.提供操作私有属性的方法
    //提供一些 public get.set 方法,get获得这个数据,set设置值
    private int age;

    public String getName() {
        return this.name;
    }

    //set 给数据设置值
    public void setName(String name) {
        this.name = name;
    }
    // alt + insert

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public char getSex() {
        return sex;
    }

    public void setSex(char sex) {
        this.sex = sex;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        if (age <= 120 && age >= 0) { // 可以内部设置合法性检验
            this.age = age;
        } else {
            System.out.println("错误的年龄!");
        }
    }
}

```



![image-20210519224332308](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519224332308.png)

j继承 对类的再次抽象

extends

![image-20210519230703784](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519230703784.png)

关于object类

在java中所有的类都默认继承object类,它提供了很多原生的方法,这也是为什么什么定义都没有的类也能调用某些方法,它相当于所有类的源头

![image-20210519233040303](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519233040303.png)

![image-20210519233001864](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210519233001864.png)

java中只能有单继承,一个儿子只能有一个父亲,但是一个父亲可以有多个孩子,这也是符合逻辑的,如果要继承多个类,要通过多次继承的方法执行,比如爷-父-子这种多代关系



super详解

和this对比

```java
//#1. 父类
public class person {
    protected String name = "父亲";
    
      public  void print() {
        System.out.println("你好");
    }
    
}

//#2.子类

public class students extends person{
    private String name ="学生";

    public void text(String name) {
        System.out.println(name);   //输出传递来的参数name
        System.out.println(this.name);  //输出子类中的name
        System.out.println(super.name);  //输出父类中的name
        
           public void print(){
            System.out.println("你好");
        }
//可以用super.print()调用父亲方法,但是调用必须是非私有
    }
}

//子类的构造函数会先默认的调用父类的无参构造再调用子类
//1.super调用父类的构造方法,而且必须在第一个
//2.super必须只能出现在子类的构造方法或者方法中
//3.super和this不能同时调用构造方法
//4.this:本身调用者这个对象 super 代表父类对象
//5.super需要继承,this无需

```

方法的重写

重写都是方法的重写,和属性无关

父类的引用指向子类

只和非静态方法有关 只能是public  private 





