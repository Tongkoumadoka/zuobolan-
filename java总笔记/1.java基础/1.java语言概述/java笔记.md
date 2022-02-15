

##### @1.java语言的特点

![image-20211125195447115](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125195447115.png)

==严格区分大小写==

##### @2.java为什么能够跨平台运行?

 归功于 JVM java 虚拟机,不同的操作系统对应有不同的jvm

![image-20211125195615376](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125195615376.png)

![image-20211125195643890](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125195643890.png)

![image-20211125195722744](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125195722744.png)

##### @3.java的垃圾回收机制(管理内存自动化)

自动执行内存释放,程序员无法精准控制和干预

但是还是会存在内存泄漏和溢出的问题

##### @4.什么是jdk 

java development kit java开发工具包

![image-20211125220820711](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125220820711.png)

##### @5.jdk ,jre , jvm 的关系

![image-20211125220840344](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125220840344.png)

![image-20211125220923670](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125220923670.png)

##### @6.测试jdk环境安装是否成功和java是否能够运行

```
cmd 中输入
java-version  得到对应jdk版本(注意java在程序员眼中就是jdk开发工具这一个整体,所以jdk的版本就是所谓的java版本,显示证明jre也安装成功了)

javac 查看java编译环境是否正常

java 查看java是否正常

都会弹出具体目录消息
```

##### @7.java 8 和jdk 1.8 就是同一个东西,只是叫法不同

另外`JDK8`或者`JDK1.8`是由于自从`JDK1.5`/`JDK5`命名方式改变后遗留的新旧命令方式问题。所以`JDK8`或者`JDK1.8`也是同一个东西。

##### @8.`JDK`与`J2SE`的区别与关系

JAVA就是指JDK开发工具，所以我们可以理解为JAVA等价于JDK。又因为JAVA有3个版本：J2SE J2EE J2ME，所以J2SE是JDK的3个版本中的其中一个，即标准版本。

等价关系

##### *@9.java/jdk 各个文件夹内容

![image-20211125223538862](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125223538862.png)

##### *@10.环境变量的意义/为什么要配置环境变量

例如安装java时,就必须要要配置对应的PATH环境变量,否者无法编译运行java程序



==-->== 如果我们没有配置环境变量

那么在cmd中想输入java -version 或者javac 等命令时,就会出现报错

![image-20211125224133539](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125224133539.png)

这个报错的表示计算机不认识(无法识别)你这条"java"命令,也就无法执行任何对应操作



==-->== 而java这个命令的来源?

​	在jdk安装目录下的bin文件夹中,有大量.EXE可执行文件,其中就有java.exe文件,实际上输入java指令的目的就是为了执行这个可执行文件(我们运行其他命令本质也是执行某个程序文件,只不过操作控制台在cmd)

如果我们将cmd目录移动到\bin文件夹内再执行该命令,就可以发现正确运行

![image-20211125224632492](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211125224632492.png)

```
写出可执行文件的/ 完整 / 绝对路径 就可以在任何目录下执行了 
```

==-->== 但是如果每次调用java执行java.exe程序都得调到对应bin文件夹是一件很不方便的事情,所以能不能直接输入java就能让系统知道该执行"java.exe" 程序了呢?

我们编写java程序时要多次调用javac,java 命令来编译运行,这么多绝对路径的输入是非常不方便而且也不现实的

==-->== 所以**环境变量**就是解决它的办法

​	path -- 路径 在PATH环境变量存储的值,就是一连串的路径 

​	环境变量的 作用就是可以让我们在任意目录让系统执行某个命令语句

​	/ 不同的路径用 ; 分隔

​	 / Windows下环境变量名不区分大小写，这与UNIX不同

​	将bin目录的完整路径添加到PATH环境变量中后,,

==-->== 系统执行用户命令的顺序

​	如果用户没有给出绝对路径,

​		-->在当前cmd所在目录查找是否有对应从可执行文件 找到则执行

​			-->没找到则**依次**在PATH 中保存的对应目录中进行**遍历**查找是否有对应可执行文件

​				-->如果还未有结果,则显示之前的未识别错误

==-->== 为什么修改path的写法需要加%path%

```
set path=%path%;D:\Java\jdk1.6.0_24\bin,

path变量之前还要很多预设路径,如果直接就设置D:\Java\jdk1.6.0_24\bin,等于java路径覆盖了以前所以路径这显然不行,我们的目的是追加java路径到PATH变量

--> path = 路径1;路径2;路径3 + ;java路径
--> 把PATH放在两个百;路径分号之间，指把PATH原有的值取出。
-->其后的分号表示分隔不同的路径值,最后一个路径没有;
-->set 设置的环境变量只在当前cmd有效,我们需要永久变化就得在Windows下修改
```

==-->==为什么还要配置JAVA_HOME 命令

```
JAVA_HOME

JAVA_HOME是一个约定，通常它指的是JDK的目录。如果需要JDK的话，大部分程序会默认去环境变量中取JAVA_HOME这个变量。

CLASSPATH

在于告诉Java执行环境，在哪些目录下可以找到我们所要执行的Java程序所需要的类或者包。不过在JDK1.5之后的版本完全可以不用设置classpath环境变量就能正常运行程序。
```

![image-20211126162941823](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211126162941823.png)

##### *@11.什么是内部命令/外部命令?

```
内部命令  系统启动就直接加载到内存,随调随用(最根本核心的命令,比如md dir),即使删除path变量内容依旧可以执行

外部命令  使用相对较少,所以不预先加载到内存,要用就会到硬盘查找再执行 比如attrib format 
```

##### *12.什么是批处理文件(.bat)

batch 批量

另外一种可以执行的文件,批处理文件包含了很多DOS命令。

文件执行时，就一条一条地执行这些命令。

不一定顺序执行，像通用的程序设计语言一样，它也有自己的流程控制。

批处理文件创建很简单：用任何一个文本编辑器（如Windows的记事本）创建一个文本文件，然后把后缀名改为.bat即可。

创建好的批处理文件，你也可以用文本编辑器打开，查看它的“源代码”。

##### @13.Java文件的编写流程

![image-20211126163800784](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20211126163800784.png)

*@14.第一次编译注意的点

==1.javac命令会生成对应类名的.class文件==

```
比如
	javac helloworld.java
	内部的class helloChina
	执行后生产的文件为 : helloChina.class	
```

==2.在运行.class文件时,不需要加class文件后缀名==

````
   java helloChina 即可
   不需要加.class,这和java指令有所区别
````

