## ajax 

### 1. 什么是ajax?

​		用 XMLHttpRequest对象和后台进行数据交互

![image-20210617145717334](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617145717334.png)

### 2.ajax 的应用场景

- 用户数据检测

![image-20210617145814136](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617145814136.png)

- 搜索提示

![image-20210617145831500](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617145831500.png)

- 表格数据动态刷新

![image-20210617145903441](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617145903441.png)

- 表格动态增改

![image-20210617145959994](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617145959994.png)

### 3. jQuery 中的ajax

#为什么使用jQuery中的ajax?

因为浏览器原生的ajax比较复杂,jQuery对它进行了优化封装,提供了很多api,**降低了使用难度**



常用的函数用法

注意$后面有.

#$.get() 拿

#$.post() 给

#$.ajax() 拿/给

#### 3.1 $.get()语法

```
$get(url,[data],[callback])
```

![image-20210617150333216](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617150333216.png)

#### 3.2 $.get()发起不带参数请求

![image-20210617150904467](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617150904467.png)

#### 3.3 $get()发起带参数请求

第二个参数传送参数对象 {id:1}, 有筛选功能

![image-20210617152357904](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617152357904.png)

3.4$.post()语法

![image-20210617152503364](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617152503364.png)

3.5$ajax() 语法

可以配置四个属性,它传输一个对象

![image-20210617152928025](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617152928025.png)

发送get请求

![image-20210617153131669](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617153131669.png)

发送post请求

![image-20210617153436910](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617153436910.png)

注意 Type 内要大写

### 4.接口

#### 4.1概念

请求的 URL地址 

![image-20210617154055432](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617154055432.png)

#### 4.2 请求过程

![image-20210617154217334](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617154217334.png)

![image-20210617154235875](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617154235875.png)

#### 4.3 接口测试工具

![image-20210617154326784](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617154326784.png)

最常用的---postman

到时候再找教程

#案例 -图书管理

![image-20210617155326261](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617155326261.png)



![image-20210617161616305](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617161616305.png)

### 5.表单

5.1表单属性

![image-20210617175037532](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617175037532.png)

![image-20210617175213988](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617175213988.png)

// 不指定action就提交到页面本身

// 提交后会直接跳转到对应页面!!! url

所以一般用 @submit.prevent="函数"阻止这个跳转行为,并执行其他函数

//问号?分割url 和具体数据

//post 不会在地址栏显示提交数据

//可以在network - formdata 中看见

![image-20210618095529860](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618095529860.png)

![image-20210618100032288](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618100032288.png)

![image-20210618100103386](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618100103386.png)

文件上传操作用第二项,其他第一项默认

![image-20210618100153961](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618100153961.png)

5.2表单同步提交

- 提交之后就发生页面跳转,跳转到**action URL**指向的地址

- 页面之前的状态和方案会丢失

解决方法:

![image-20210618100400500](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618100400500.png)

功能模块化

5.3 使用ajax提交表单数据

​	#1.监听表单提交事件

![image-20210618100520869](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618100520869.png)

#2.阻止表单默认行为(跳转)

![image-20210618101326272](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618101326272.png)

event.preventDefault()

#3.一次性获取表单所有数据 serialize()

![image-20210618102627631](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618102627631.png)

![image-20210618102847494](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618102847494.png)

![image-20210618103923636](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618103923636.png)

### 6.XHMHttpRequest 

#### 6.1 XHMHttpRequest定义

xhr 浏览器提供的js对象

![image-20210618104150608](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618104150608.png)

#### 6.2 基本使用

###### #GET请求发起流程

![image-20210618104352201](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618104352201.png)

传送成功后xhr会接收到服务器送来的数据,它自带的方法可以让我们取到这些数据

注意:打印的status是服务器响应的一个属性,是传递来的数据的一部分

但是再xhr.status判断中,这是http一个请求状态的一部分



###### #发起带参数的GET请求

如果对请求数据有要求,就发起带参数的GET请求

直接在url 地址后加查询字符串

![image-20210618105450718](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618105450718.png)

###### #发起POST请求

![image-20210618110642449](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618110642449.png)

![image-20210618111108391](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111108391.png)

#### 6.3 xhr readyState属性

![image-20210618105210353](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618105210353.png)

```
 if (xhr.readyState == 4 && xhr.status == 200) 数据传送成功判断
```

#### 6.4查询字符串

![image-20210618105837459](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618105837459.png)

###### #封装方法get请求携带参数的本质:

无论是$.get()还是$.ajax(),本质上都是以查询字符串的方式向服务器发起请求

只是jquery封装的方便一些,让你写到一个对象里面,它自己接到url后面改变形式

![image-20210618110005349](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618110005349.png)

6.5 URL编码

 #1.url编码定义

最常用的用 utf-8

因为url地址不允许出现中日韩文,所以要对这些字符进行编码(转义)

![image-20210618110327020](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618110327020.png)

中文就是3组百分号加16进制

#2.编码和解码过程

浏览器提供了方法,调用即可,输出结果都是字符串

![image-20210618110527605](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618110527605.png)

### 7.数据交换格式

#### 7.1定义

一般两种 XML 和 JSON,主要是==JSON== 

![image-20210618111441125](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111441125.png)

#### 7.2 XML

可扩展标记语言,它和HTML类似,但是可以自定义标签,语义化很强

- HTML和xml没有任何关系,只是都是标记语言而已
- XML用来传输和存储数据

![image-20210618111644387](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111644387.png)

###### #XML缺点

![image-20210618111736257](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111736257.png)

所以用的少,标签比数据都多..

#### 7.3JSON

##### #1.定义和特点

![image-20210618111827162](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111827162.png)

- 本质就是==字符串==

- 它是对js 对象 数组 的一种字符串表示方法
- 它就是一个文本文件
- 用来传输和存储信息

![image-20210618111938050](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618111938050.png)

###### #json 和 js对象关系

对比就可以知道区别

![image-20210618112842353](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112842353.png)

###### #json和js对象的互相转换

#json = > js

```
	JSON.parse()
```

![image-20210618113322552](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618113322552.png)

![image-20210618113910320](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618113910320.png)

#js = > json

```
JSON.stringify()
```



##### #2.两种结构

###### #对象结构

- 数据写在{}内
- 数据写成key:value 形式
- 数值和布尔值直接写,无需双引号
- 其他数据必须用=="key"==包裹
- 不存在的值用 ==null==,不能写undefiened
- ==不能传输函数类型==

![image-20210618112437056](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112437056.png)

![image-20210618112443619](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112443619.png)

###### #数组结构

![image-20210618112542944](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112542944.png)

##### #3.JSON语法注意事项

![image-20210618112719206](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112719206.png)

<img src="C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618112737868.png" alt="image-20210618112737868" style="zoom:150%;" />

###### #序列化和反序列化

就时一种convert过程

![image-20210618130950899](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618130950899.png)

##### #4.封装ajax函数

![image-20210618131140232](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618131140232.png)

先定义传入参数的配置项

![image-20210618131216507](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618131216507.png)

#处理data![image-20210618131312262](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618131312262.png)数,转换为查询字符串形式

###### #定义 函数监听事件

![image-20210618135013314](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618135013314.png)

###### # 判断请求类型

![image-20210618135854749](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618135854749.png)

### 8.XHMHttpRequest 2.0ver

8.1 新功能

![image-20210618142012735](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618142012735.png)

##### #1.设置http请求时限

因为ajax操作很耗时

```
xhr.timeout = 3000 单位ms
配套还有timeout事件,可以调用回调函数
```

![image-20210618142154637](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618142154637.png)

##### #2.formData 对象管理表单数据

H5新增的对象

![image-20210618142703425](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618142703425.png)

直接采集用户输入的表单数据

##### #3.上传文件

![image-20210618151013802](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618151013802.png)

![image-20210618151021666](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210618151021666.png)

