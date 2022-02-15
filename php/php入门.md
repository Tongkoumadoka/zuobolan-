### 1.基础信息

- PHP是后端脚本语言

```php
<?php
// 此处是 PHP 代码
?>
```

- 语句以;分号结尾

- 大小写不敏感

- 变量名对大小写敏感,所以不能乱写

  所有用户定义的==函数==、==类==和==关键词==（例如 if、else、echo 等等）都对大小写不敏感。

```
<?php
ECHO "Hello World!<br>";
echo "Hello World!<br>";
EcHo "Hello World!<br>";
?>
上面的都能用
```





### 2.PHP变量规则

#### 2.1基本规则

- 变量必须 $ 开头 (类型于 js里面的 var 声明这是个变量)\
- 变量名称必须字母 或者 _下划线开头
- 变量名称大小写敏感/组成只有数字/字母下划线_

- 变量只有被赋值才会被创建
- 文本记得用""
- 和JS一样PHP不管数据类型
- 如果一定要声明一个预留变量就声明空: $website = ""; 或者null

```
<?php
$txt="Hello world!";
$x=5;
$y=10.5;
?>
```

#### 2.2变量作用域

有三个变量作用域

- local（局部）
- global（全局）
- static（静态）

>函数*之外*声明的变量拥有 Global 作用域，只能在函数以外进行访问。
>
>函数*内部*声明的变量拥有 LOCAL 作用域，只能在函数内部进行访问。
>
>也就是专款专用,不得交流

所以不同函数内可以创造同名变量,因为外部无法访问,所以等价于唯一

那么函数如何访问全局变量呢?

方法1:使用global关键字

```
比如你在全局声明了变量$x

想要在function 中访问就 调用时添加 global
global $x
这样计算机就知道去全局作用域找,然后返回值

global $x,$y;
你可以想象成在函数内声明一遍可以访问的全局变量
```

方法2:使用 $GLOBALS[INDEX]数组

```
在这个数组下标输入你要访问的变量名称即可
记得用''
  $GLOBALS['y']=$GLOBALS['x']+$GLOBALS['y'];
```



### 3.输入输出语句

PHP有两种输出方法,无论括号有无都能用

- echo
- print

区别:

>echo:能够输出很多东西,不返回值
>
>print:只能输出==一个字符串==,并且始终 返回值1

```
echo和print字符串中能包含 HTML 标记,比如你写H2,那么文本内容就会对应加粗,表现成相应的样式

echo "<h2>PHP is fun!</h2>";
```



3.1



### 4.表格方法

#### 4.1如何制作必填字段

![image-20210604150520558](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604150520558.png)

4.3操作单选按钮 检验

```php
<input type="radio" name="gender"
<?php if (isset($gender) && $gender=="female") echo "checked";?>
value="female">Female
<input type="radio" name="gender"
<?php if (isset($gender) && $gender=="male") echo "checked";?>
    //如果被选了就输出checked
value="male">Male
```



### 10.内建函数或者语法

#### 1.echo

```
<?php
echo "Hello World!";
?>
```

#### 2.var_dump() 测变量类型

```
$x = -345; // 负数
var_dump($x);

会返回变量类型和值
int(-345)

数组
array(3) 数组类型,元素个数为3
```

#### 3.strlen() 返回字符串长度	

```
<?php
echo strlen("Hello world!");
?>
//包括空格也算一个长度单位
```

#### 4.str_word_count() 字符串单词计数

```
<?php
echo str_word_count("Hello world!"); // 输出 2
?>
```

#### 5.strrev()翻转字符串

```
 strrev()
<?php
echo strrev("Hello world!"); // 输出 !dlrow olleH
?>
```

#### 6.strpos() 检索匹配字符位置

```
<?php
echo strpos("Hello world!","world");
?>
// 输出6,没有输出false
```

**上例中字符串 "world" 的位置是 6。是 6（而不是 7）的理由是，==字符串中首字符的位置是 0 而不是 1==。**

#### 7.替换字符串内文本

把字符串C中的a子文本替换为b

```
<?php
echo str_replace("world", "Kitty", "Hello world!"); // 输出 Hello Kitty!
?>
"a","b","C"
```

#### 8.常量定义函数 define()

```
define("常量叫什么","常量的值是多少")
```

注意常量贯彻整个脚本,谁都能用

#### 9.字符串运算(主要是加法)

用.运算符

```
$x = "hello";
$y = "world";
$c = $x.$y;
echo $C;
或者也可以直接加字符串不加变量
$d = $x . "wolrd"
//输出c 为hello world
```

#### 10.htmlspecialchars() 函数

用来放置xss攻击,跨站点脚本（Cross-site scripting，XSS）

因为它会把脚本的关键字< > 变成HTML文本 &alt,于是就无法运行了

11.检验变量是否为空



```
empty() 函数
empty($ivar1) 会返回一个布尔值进行 if 条件判断

empty(trim($name)) 在PHP5.5后可以使用嵌套函数再判断,之前这样写会报错

empty($_POST["name"]) 检验表单送来的数据值是不是空
```

12.匹配正则表达式

preg_match()

13.检测变量是否已经设置

**isset()** 函数用于检测变量是否已设置并且==非 NULL==

### 11.超全局变量

#### 11.1 $_SERVER["PHP_SELF"] 变量

- 超全局
- 它返回当前执行脚本的文件名

#### 11.2 返回 访问页面 的请求方法

$_SERVER['REQUEST_METHOD']

比如"POST"'GET'





可以用$_POST["name属性名称"]来访问表单传输的数据

```
  $gender = test_input($_POST["gender"]);
  比如,这就接收到前端的数据了
```

