webAPIs 和 JS基础关联性

js基础学习 ECMAscript 基础语法为后面做铺垫,web APIS是js 的应用,使用它做页面交互效果

![image-20210523180006275](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523180006275.png)

![image-20210523180110347](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523180110347.png)

API application programming interface  应用程序编程接口

是一些预先定义的函数,给程序员提供的某种工具,提供对应功能,程序员只要找到接口就能实现某种功能,我们无需了解它的原理和机制



web API  浏览器的API 提供一套操作浏览器功能和 页面元素 的API (bom 和 dom)

比如 alert();函数

## DOM

![image-20210523180949906](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523180949906.png)



![image-20210523181007945](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523181007945.png)



### 1.dom的定义

> 文档对象模型 (DOCUMENT OBJECFT MODEL DOM) 是w3c推荐用来  处理 可扩展标记语言(HTML xml) 的标准程序接口(api)

- W3C定义了一系列dom接口
- 



### 2. DOM树



![image-20210523181304363](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523181304363.png)

- 文档:一个页面就是一个文档(.HTML文件),DOM中用ducument表示

- 元素:页面中所有的标签被称为元素, element

- 节点:网页中所有内容都是节点  node

  (包括 **1.标签(**元素),标签中的2.**属性**,标签内的**3.文本**内容 4.**注释**)

- DOM把以上所有内容 (文档,元素,节点)全部看为对象 (object)

### 3.获取元素

DOM在实际开发中主要用来操作元素 (element)

#### 3.1获取元素的方式(4)

##### (1)根据 id属性 获取, # -- id

- 使用getElementById()方法

```javascript
//使用getElementById()方法
getElementById(id)



var element = getElementById(id);

//(1)它返回一个 element对象
//(2)找不到返回 null
```

```html
    <div id="time"> 20002 </div>
    <script>
        //1.注意:由于文档加载顺序从上往下,所以script放在后面
        //2.方法标识符严格区分大小写 驼峰命名
        //3.参数 id 是大小写敏感的字符串
        //4.返回的是一个元素对象
        var time = document.getElementById("time")
        console.log(time); //<div id="time"> 20002 </div>
        console.log(typeof time);  //object 不是string!!

        //打印查看对象的属性和方法目录
        console.dir(time);
    </script>
```

##### (2)根据标签名(元素名)

用来获取大量相同类型的标签或者元素,因为给很多标签添加#id 是非常繁琐的

- ###### document.getElementsByTagName('li')使用方法

```HTML
	<ui>
        <li>相同标签好麻烦0</li>
        <li>相同标签好麻烦1</li>
        <li>相同标签好麻烦2</li>
        <li>相同标签好麻烦3</li>
    </ui>
    <script>
        //1.返回的是 获取的元素对象集合 用伪数组的形式存储
        //2.可以遍历打印里面的元素对象
        //3.得到的元素对象是动态的
        //4.注意,就算只有一个Li 返回的还是伪数组,只是存储一个对象元素
        //5.注意:没有内容,返回的就是空的伪数组
        //6.它会搜索当前整个页面所以的该标签元素并返回过来
        var lis = document.getElementsByTagName('li');
        console.log(lis);
        console.log(lis[1]);
        for (i = 0; i < lis.length; i++) {
            console.log(lis[i]);
        }
```

- ###### 获取父元素内部 指定标签名的子元素

```javascript

        //获取父元素内部 指定标签名的子元素
        //1.指明它的父元素,然后获取这个父元素下对应的标签元素
        //2.父元素用id 表明唯一性,才能使用
        //3.获取时不包括父元素本身
        var ol = document.getElementsById('ol');
        var ollis = ol.getElementsByTagName('li');
```

![image-20210523191132073](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523191132073.png)

##### (3)H5新增方法

![image-20210523191052450](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523191052450.png)

##### (4)特殊元素的对应获取方法

- body元素的获取

```javascript
  //1.获取body 元素
        var getBody = document.body;
        console.log(getBody);
        console.dir(getBody); // 返回body元素对象

```

- HTML元素获取

```javascript
  //2.获取HTML元素
        var gethtml = document.html;
        console.log(gethtml);  //undefined

        //正确写法
        var gethtml = document.documentElement;
        console.log(gethtml); //返回HTML元素对象
```

### 4.事件基础

> 事件类似开发的开关,它可以被看成可以被js侦测的行为

​	触发--响应机制

![image-20210523191806353](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523191806353.png)

#### 4.1事件的组成

事件三要素

- 事件源 :事件被触发的对象 (可以用获取对象的方式得到它)
- 事件类型 :事件是如何被触发的 如何触发,什么事件 (用定义的事件处理)
- 事件处理程序 :通过一个函数赋值的方式完成 

#### 4.2事件的进行流程:

 按钮(button 事件源 事物) 被 点击(事件类型 动作) 于是获得100美元(事件处理程序 get100dollors() 执行)

- 获取事件源

```javascript
var div = document.querySelector('div');
```

- 注册事件(绑定事件)

```javascript
div.onclick
```

- 添加事件处理程序

```javascript
div.onclick = function() {
	console.log('我被选中了');
}
```

#### 4.3常见鼠标事件

![image-20210523192731650](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523192731650.png)



### 5.操作元素

DOM操作可以做到很多功能

- 改变网页结构 html

- 改变网页内容 innerhtml

- 改变网页样式 css

- 改变元素 属性 attributes

- 改变元素 内容 

  

#### 5.1改变元素内容

- 

```
element.innerText = 赋值
//它输出的是文本内容,不会输出标签
//去除空格和换行
//不识别内部HTML标签,会视作文本,一同打印
```

- 

```
element.innerHTML
它输出包含HTML标签,保留空格换行
//内容识别HTML标签
```

- 区别

```javascript
  <script>
        var div = document.querySelector('div');
        div.innerText = "<strong>具体</strong>"; //<strong>具体</strong>

        div.innerHTML = "<strong>具体</strong>"; //具体(加粗)

    </script>
```

- 结论

建议使用HTML,w3c指定标准

他们可以同步获取对应标签内容



#### 5.2操作常见元素属性

#### 5.3操作表单元素的属性

this指向事件函数的调用者,谁发生了事件,就是谁

```
btn.onclick = function () {
	this.disabled = true ;
	btn.disabled = true ;
	//两者等价
}
```



![image-20210523213510662](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523213510662.png)

#### 5.4元素样式操作 (style)

使用js修改 元素 的大小,颜色 ,位置,隐藏

![image-20210523220825260](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523220825260.png)

#js修改的style属于行内内联样式,它比内嵌样式权重高,会直接覆盖

内嵌样式就是行内样式

![image-20210523221403968](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210523221403968.png)

```
注意,修改类名必须是
this.className = "";
对应修改标签的 class = ""内的值
```

> 修改样式的实际思路是写很多替换的类,他们有不同的类名className,当要换的时候,就换对应标签中class值
>
> id是接收变量识别标签的基础
>
> classname是更改状态的前提

![image-20210524112202084](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210524112202084.png)

5.5 获取元素属性的方法

(1)获取方法

```
element.属性 获取内置属性值(元素本身自带属性)
class,id,value 之类的


element.getAttribute('属性'); (获取自定义属性)
```

(2)设置元素属性值

```
element.属性 = '值';

element.setAttribute('属性','值');

div.setAttribute('index','1');
divelement.setAttribute('class','1');
//但是class比较特殊,不写classname
同上
```

(3)移除自定义属性

```
div.removeAttribute('index');
```

5.5 H5自定义属性

![image-20210524174557122](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210524174557122.png)

规范

```
1.所有自定义属性都是 data-开头的
比如data-index
2.或者用js中setattribute设置自定义属性
```

获取方法

```
1.div.getattribute('date-index'); 更加好用


H5新增
2.element.dataset.index
他会作为一个对象,输出所有的data开头的自定义属性

如果自定义属性有多个-链接,就用驼峰命名法获取
//它只能获取data开头的
//ie11才能获取
//所以优点?
```

### 6.节点操作

页面中所有的内容都是节点node

![image-20210524194634563](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210524194634563.png)

节点层级 

- 父子 
- 兄弟

```
//1.父节点 parentNode
子节点.parentNode  得到离元素最近的节点


//2.子节点 childNodes 标准获取所有子节点(包括文本,元素)
得到对象的集合

//ul.childNodes  
得到所有li列表
text 换行也算,包含所有元素节点和文本节点

只得到元素节点,使用节点类型来筛选

用for循环遍历,把[1]的存到一个新数组
//但是很麻烦,一般不用子节点

//3.使用children节点 获取所有子元素节点
```

![image-20210524195743723](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210524195743723.png)

```
//1.firstChild
 获取第一个子节点,无论是换行的文本节点还是元素节点
 2.lastChild 
 同样
 
 ie9兼容
 //3.firstElementChild 返回第一个子元素节点
 //4.lastElementChild
 
 实际开发写法
 children 是伪数组,所以返回第一个和最后一个的下标即可
 
 第一个元素:children[0]
 最后一个元素 : ol.children[ol.children.length - 1]
```

