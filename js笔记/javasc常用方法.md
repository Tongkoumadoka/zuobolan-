### 1.常用数学方法

循环语句条件为真就执行循环!!!

Math.

abs(x) 求绝对值

max(x,y,z)求多个数的最大值

min(x,y,z) 求多个数最小值

pow(x,y) 求x的y次方

random() 返回一个0-1的随机数

floor() 向下取整

##### #ceil() 向上取整

round(num) 四舍五入最接近的整数

##### #es6 计算a的任意次方,比如2的3次方

```
包括小数,负数次方都可以计算
```

```
a ** b 2**3
```



```
  total == 0 ? 0 : Math.round((nv / total) * 100) + "%";
  求整数百分比
```

![image-20210707103133657](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707103133657.png)

![image-20210707103117515](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707103117515.png)

### 2.常用字符串方法和属性

#### 2.1属性

.length 返回字符串长度,包括空格 !!! 

可以调用字符串的length判断它的位数,数组进行转换判断位数

#### 2.2方法

##### #1.indexOf()  判断字符串内有没有查找的字符(串)

比如在一句话中找有没有关键字 "async",有一定返回位置>0的数,没有返回-1,所以可以进行条件判断筛选

返回字符串中 指定文本 ==首次出现位置==

注意字符串的第一个字符是从0开始存储的

```
var str = "The full";
var pos = str.indexOf("full");
//返回值为 4  T是0存储位置
```

0 是字符串中的第一个位置，1 是第二个，2 是第三个 ...

lastindexof() 返回最后一次出现位置

没有找到均返回-1 可以用if判断语句

##### #2.trim() 方法 删除字符串两端的空白符

```
var str = "       Hello World!        ";
alert(str.trim());
```

typeof 变量或者数据  确定变量的数据类型

```
typeof "Bill"                 // 返回 "string"
```

- NaN 的数据类型是数值
- 数组的数据类型是对象
- 日期的数据类型是对象
- null 的数据类型是对象

- 未定义变量的数据类型是 *undefined*
- 尚未赋值的变量的数据类型也是 *undefined*

##### #3.把数字转换为字符串 

String()

toString()

##### #4.把字母全大写/小写

data.toUpperCase()

data.toLowerCase() 

应用:对用户传来的数据进行if判断

因为用户有时候传输的数据有大小写夹杂,而实际判断对大小写不做要求,就在判断中用这个进行处理统一大小写方便判断,比如判断get请求之类的

![image-20210618140443794](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618140443794.png)

##### #5.把字符串分割为数组

```
不修改原字符串
```



split()方法 参数必须填

按空格分隔 arr.split(' ') ,输出一个==数组==!!

应用:

对于以字符串形式存储的数组信息,就要用这个方法接收到数组

然后再分别对数组中元素进行操作,用for循环批量处理后,再用新数组接收

这样就得到处理后的数组

也可以再进行join()得到处理后的字符串

第二个参数控制返回数组的最大长度

![image-20210624103344819](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210624103344819.png)

##### #6.对数组内元素进行批量处理

forEach()方法 es3

forEach(回调函数名 callback())

```
array.forEach(function(currentValue, index, arr), thisValue)
```

注意第一项是必须的,可以写函数名,在foreach()外再声明函数

或者直接在里面写箭头函数/匿名函数

currentvalue就是当前循环到的数组 中的某个 元素

![image-20210618174326816](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618174326816.png)

##### #7. 替换字符串中的某个字符为另一个

replace() 方法

进行字符串和数组间元素数据更换时经常用

比如把'=',':'等号替换我冒号,变成数组内元素key:value

##### #8.获取字符串中对应索引的ASCII码

```
String.charCodeAt(index)
返回一个数值
```

##### #10.获取某一节字符串内容

##### #9.数字0-9ASCII码 48- 57

```
字符 二进制 十六进制 十进制
0 110000B 30H 48
1 110001B 31H 49
2 110010B 32H 50
3 110011B 33H 51
4 110100B 34H 52
5 110101B 35H 53
6 110110B 36H 54
7 110111B 37H 55
8 111000B 38H 56
9 111001B 39H 57
```

##### #11.str.repeat(n) 返回新字符串,n次拼接的

```js
   // str.repeat(n)
    // (1)不改变原字符串(字符串确实也不会被改变)
    // (2)会返回一个新字符串/新字符串重复n次调用的str内容
    let str = 'abc'
    console.log(str.repeat(3)) // abcabcabc 拼接三次
    console.log('0'.repeat(3)) // 000
    console.log(str)
```



### 3.常见对象

#### 3.1 event对象

方法:

target





focus() 获取节点焦点 原生方法 input



#

for in语句 遍历数组/或者对象的属性 或者进行循环操作

应用:把对象属性进行处理用数组形式输出

```
for (变量 in 对象)
{
    在此执行代码
}
//“变量”用来指定变量，指定的变量可以是数组元素，也可以是对象的属性。
for (let k in data ){

}
//每循环出一个属性,就用变量k接着,然后对他进行操作就是对属性进行操作
```

![image-20210618131830362](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618131830362.png)

注意k是==字符串形式的属性名==!!

#### 3.2 formDate 对象

````
创建 : 构造函数
var fd = new formDate()
````

append() 方法

```
formData.append(name, value);
```

向 `FormData` 中添加新的属性值，`FormData` 对应的属性值存在也不会覆盖原值，而是新增一个值，如果属性不存在则新增一项属性值。

#### 3.3Object

##### 1.Object.assign() 方法

```
它可以把多个源对象resource{}的属性分配到目标对象target对象,再返回目标对象target,
//属性值会有后来覆盖先来
//但是
```

```
Object.assign(target, ...sources)
执行后 return target对象
比如这种何并几个对象到一个空对象
Object.assign({}, ...sources)
```

#### 3.4document

检索节点

```
注意:节点本身分为三种
元素,属性,文本节点
元素为element node
```

![image-20210623112606540](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623112606540.png)

### 4.常用数组操作方法和属性

#### 4.1方法

##### #1.把数组内容全部拼接起来(输出字符串) 数组=>字符串

join()方法

```javascript
  var stringArray = ["This", "is", "Baidu", "Campus"];

    alert(stringArray.join(" "));
输出字符串://"This is Baidu Campus"
```

注意: 参数为指定要使用的分隔符。

如果省略该参数，则默认使用逗号,作为分隔符。



应用:对数组的每一项数据换行后再拼接  arr.join('/r/n')

##### #2. 给数组添加内容(末尾)

push()方法

push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。

注意它的返回值是 ==number== !!

##### #3.数组内容筛选(调用某个函数)  数组->数组

filter(筛选函数) 注意返回值是 新==数组==!!

注意筛选函数必须要有return==布尔返回值==

filter()根据布尔值的来确定保留数组中的哪个元素

![image-20210623154853917](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623154853917.png)

filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。

**注意：** filter() 不会对空数组进行检测。

**注意：** filter() 不会改变原始数组。

##### #4.map()   数组数据全部某个函数处理后 返回新数组

map(处理函数)方法 返回值是 新==数组==!!

调用方法

```
array.map(函数名或者匿名函数)
```

数组内所有元素按index依次执行处理函数

![image-20210623171109518](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623171109518.png)

map() 方法返回一个新数组，数组中的元素为原始数组元素调用函数处理后的值。

map() 方法按照原始数组元素顺序依次处理元素。

**注意：** map() 不会对空数组进行检测。

**注意：** map() 不会改变原始数组。

但是如果是引用元素就可以改变属性和方法,比如对象



##### #5.some()方法

##### #6.every()方法

##### #7.在数组中找到符合条件的元素,然后返回它在数组中的index值

arr.findIndex(callback) 但是只返回满足条件的第一个index

##### #8.在数组中找到满足条件的元素,然后返回这个元素

arr.find() 只返回满足条件的第一个元素(对象返回对象)



##### #9.数组排序 (修改原数组)

```
arr.sort()
顺序排列
arr>reverse()
逆序排列'

可以排列字符串,会先转换为字符串各个字符的Unicode位点进行排序
如果同时有数值和字符串,会先排列数值部分,然后再在之后排列字符串(顺序)


注意比较的数字会被转换为字符形式,所以有可能出现80 小于9 的情况
```



### 5.常用对象的操作方法和属性

#### 5.1属性

##### #1.如何调用对象的属性

有两种方法调用对象属性!!

- 对象.属性
- 对象['属性']

第二种方法在 ==for in循环==中用的特别多!! 注意属性名称必须==字符串形式==!!

##### #2.对象和JSON的相互转换

```
JSON.parse(xhr.responseText)
把json = > 对象
```

![image-20210623112009977](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623112009977.png)

### 6.循环的方式

#### @1.for of  

```
ES6 新增的for of 循环
遍历所有数据结构统一的方法

数组/map/set/类数组/字符串都可以遍历
```

#### @2.forEach() 不改变原数组,返回undefined

```
// forEach()  不改变原数组
    // (1)callback执行一次,那些已删除或者未初始化的项将被跳过（例如在稀疏数组上）
    // (2)一般不会改变原数组,只是借用原数组元素进行处理,然后用console.log()输出,
    // (3)但是如果存储内容是引用类型,那么其属性还是会被间接改变
    // (4)原因在于callback(item,index,array),参数实际是存储了原数组引用变量中的地址,也就是浅拷贝
    // (5)没有返回值undefined
    // (6)无法提前终止循环
```





### 7.set数据结构

7.1 set数据结构的特点

(1)双中括号是内置属性,无法被枚举,只有引擎可见

![image-20220119101543441](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220119101543441.png)

(2)set[0]的返回值是undefined,因为它会当做属性名搜索'0'属性,显然没有定义,返回undefined
