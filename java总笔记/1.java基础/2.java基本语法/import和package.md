#### 1.package

##### @1.写法

```java
package com.atguigu.java ;
```

- 包属于表示名,包名全小写(xxxyyyzzz)
- 声明类或者接口所属的包,必须写到源文件**首行!**
- 每.一次,代表一层文件目录
- 一般放到src文件夹中
- 同名的包 ==> 不允许重名类/接口

##### @2.目的

```

```

##### @3.重要包的介绍

```
java.lang java.io java.util java.net java.text java.sql java.awt
```

![image-20220112214250702](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220112214250702.png)

#### 2.import

##### @1.写法

导入指定包下的 某个类,接口(自定义的,还有官方的都行)

```java
package com.atguigu.java;

import java.util.Arrays;
```

- 声明在包的声明之后

```
```

如果一个包内的多个类被import,那么可以并列写出

``` java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;

// 导入这个包下所有的结构,但是子包下的结构还是得显式导入(只导入一级层级结构)
import java.util.*;
    
// 导入指定包下对应文件的静态结构
import static java.lang.System.*;
import static java.lang.Math.*;
```



##### @2.细节

(1)String[] / System 也是java.lang包中的类,为什么不需要import?

因为他们时java.lang包下定义的,是核心类,可以省略import结构

(2)什么时候省略引入?

除了java.lang包内外,同包文件也无需引入,直接写该类即可

![image-20220112215741596](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220112215741596.png)

(3)不同包同名.java文件引用怎么解决?

![image-20220112215900814](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220112215900814.png)

#### 3.super

##### @1.写法

```
(1)调用父类属性
super.属性名 //常常作用在父子类有同名属性,子类需要调用父类同名属性时
(2)调用方法默认
this.方法(),只不过会省略this
(3)调用构造器
子类构造器首行,调用父类构造器
@1.super(形参列表) 
@2.this 和 super二选一
@3.没写,子类默认先调用父类的空参构造器
```

![image-20220113102014313](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220113102014313.png)

##### @2.目的

```
super是为了解决 : 子类重写父类方法后,想调用父类同名方法/属性的问题
(1)比如子类的重写方法是在父类方法基础上做某些运算处理,就没必要再写很多相同的代码,直接调用super然后加子类的逻辑
(2)比如修饰构造器/方法/属性
```



##### @3.多层父类调用

```
如果是多层父类调用,则顺着父类子类向上查找,定义在哪儿就调用那个(取近)
```

##### @4.注意

```
如果子类写了空参构造器,父类必须也提供空参构造器,否则会报错

在多个构造器中,至少有一个调用super()父类构造器

当创建子类对象时,会直接间接的调用继承链上父类的构造器,最后直到object空参构造器,也正是因为加载过构造器,子类对象才会有父类结构

但是,创建子类对象过程中,调用父类构造器,并没有创建父类对象!!!
```

