先看看一般怎么写

```javascript
$(document).ready(function(){
//1.这个document函数必写
  $("p").click(function(){
      //事件触发函数
    $(this).hide();
      //触发之后结果
  });
});
```





### 1.引入jQuery

```
<head>
<script type="text/javascript" src="jquery.js"></script>
</head>
```

### 2.jQuery的函数和作用

1.隐藏函数hide() 

- hide() 隐藏当前

```
$(this).hide();
```

- 隐藏对应id元素

```
$("#test").hide();
id = text
```

- 隐藏所以 某类标签

```
$("p").hide();
标签p全部被隐藏
```

- 隐藏某类标签

```
$(".act").hide();
```







### 3.jQuery本质是一个js文件库,它封装了很多方法

- 关于美元符号$ 它和 jQuery是等价替换的

```
$("#foo") = jquery("#foo")
```

- 关于加载前的函数

```
$(document).ready(function(){
//函数体
});
//这本质和原生window.onload 没有太大区别
只是执行时机不同,有点类似事件触发函数

//而且原生的事件触发只能编写一个,新的会覆盖旧的
```

![image-20210607152154365](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210607152154365.png)

- 注意jQuery对象里无法使用任何原生的dom方法.他们都能用jQuery方法代替![image-20210607153350011](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210607153350011.png)

- jQuery无需担心是否选择器对应选中会报错![image-20210607154358598](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210607154358598.png)

因为$("#")获取的永远是个对象,所以if判断存在时要从获取长度>0来判断是否有没有



### 4.jQuery 的作用

- 查询 query HTML元素
- 操作dom action
- 操作css

```
$("#user").css("backgroud-color", "red");
"属性名","属性值"
```



### 5.jQuery语法

jQuery 语法是为 HTML 元素的选取编制的，可以对元素执行某些操作。

基础语法是：*$(selector).action()*

> 意思为:用选择器找到某些东西然后对他们执行某些操作



所有 jQuery 函数位于一个 document ready 函数中

> 这是为了防止文档在完全加载（就绪）之前运行 jQuery 代码

为了方便维护,最好把用jQuery写的自定义事件函数全部单独放到一个js文件并从外部引用

```
<head>
<script type="text/javascript" src="jquery.js"></script>
<script type="text/javascript" src="my_jquery_functions.js"></script>
</head>
```



### 6.jQuery选择器

#### 6.1.基本选择器

##### 1.元素选择器

$("p") 选取 <p> 元素。

$("p.intro") 选取所有 class="intro" 的 <p> 元素。

$("p#demo") 选取所有 id="demo" 的 <p> 元素。

##### 2.属性选择器

注意是""

然后是[]

$("[href]") 选取所有带有 href 属性的元素。

$("[href='#']") 选取所有带有 href 值等于 "#" 的元素。

$("[href!='#']") 选取所有带有 href 值不等于 "#" 的元素。

$("[href$='.jpg']") 选取所有 href 值以 ".jpg" 结尾的元素。

#### 6.2层次选择器

可以选择层次关系的元素

比如后代元素,子元素,相邻元素,兄弟元素,父元素

![image-20210607155811521](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210607155811521.png)

.next()方法 和 nextAll()方法 可以代替//都只能选后面的兄弟

siblings()方法可以选择无论前后的兄弟元素

#### 6.3过滤选择器

#### 6.4表单选择器



### 7.jQuery 事件函数

| Event 函数                      | 绑定函数至       |
| :------------------------------ | :--------------- |
| $(document).ready(function)     | 当文档完成加载时 |
| $(selector).click(function)     | 点击             |
| $(selector).dblclick(function)  | 双击             |
| $(selector).focus(function)     | 获得焦点 focuson |
| $(selector).mouseover(function) | 鼠标悬停 hover   |

### 8.jQuery效果 

#### 1.隐藏和显示

1.hide()

```
//控制隐藏显示时间
$("button").click(function(){
  $("p").hide(1000);
});

$(selector).show(speed,callback);
speed控制时间,单位ms,后面一个控制函数,隐藏之后触发
```

2.toggle()

隐藏显示功能都包了

```
$("button").click(function(){
  $("p").toggle();
});

也有speed 和callback
```

#### 2.淡入淡出

淡入淡出操作的是display,元素消失后不占据空间,都有speed 和callback

- fadeIn()  淡入 出现
- fadeOut() 淡出 消失
- fadeToggle()  淡入和淡出
- fadeTo() 渐变透明度

```
$(document).ready(function(){
  $("button").click(function(){
    $("#div1").fadeTo("slow",0.15);
    $("#div2").fadeTo("slow",0.4);
    $("#div3").fadeTo("slow",0.7);
  });
});

当为0时.就完全淡出
```

#### 3.滑动

让元素上下滑动,都有speed 和callback

- slideDown() 滑出
- slideUp() 滑入
- slideToggle() 来回滑动

```
$(document).ready(function(){
  $(".flip").click(function(){
    $(".panel").slideDown("slow");
  });
});

$(document).ready(function(){
$(".flip").click(function(){
    $(".panel").slideToggle("slow");
  });
});
```

#### 4.动画

jQuery animate() 方法允许您创建自定义的动画。

```
$(selector).animate({params},speed,callback);

通过对animate()函数内想要改变的css样式属性进行修改,然后自动按speed时间或者速度变化

$("button").click(function(){
  $("div").animate({left:'250px'});
}); 
```

改变位置要把display变了

一个animate操作多个属性

```
$("button").click(function(){
  $("div").animate({
    left:'250px',
    opacity:'0.5',
    height:'150px',
    width:'150px'
  });
}); 
同样可以操作不止一个css样式属性
```

多个animate按顺序队列执行

```
$("button").click(function(){
  var div=$("div");
  div.animate({height:'300px',opacity:'0.4'},"slow");
  div.animate({width:'300px',opacity:'0.8'},"slow");
  div.animate({height:'100px',opacity:'0.4'},"slow");
  div.animate({width:'100px',opacity:'0.8'},"slow");
});
```

#### 5.停止动画

阻止动画继续进行

```
$(document).ready(function(){

  $("#flip").click(function(){
    $("#panel").slideDown(5000);
  });
  
  $("#stop").click(function(){
    $("#panel").stop();
  });
});
```

参数,可写两个true

- 不写 停止当前执行,队列后面继续
- true 停止队列
- true,true 停止队列并且设置完成

### 9.jQuery操作dom(HTML)

#### 1.内容获取

- text() - 设置或返回所选元素的文本内容

```
$("#btn1").click(function(){
  alert("Text: " + $("#test").text());
});

//这是段落中的粗体文本.
```

- html() - 设置或返回所选元素的内容（包括 HTML 标记）

```
$("#btn2").click(function(){
  alert("HTML: " + $("#test").html());
});

//这是段落中的<b>粗体</b>文本。
```

- val() - 设置或者获取 表单input的value属性值

```
$("#btn1").click(function(){
  alert("Value: " + $("#test").val());
});
```

- attr("href")获取属性值

```
$(document).ready(function(){
  $("button").click(function(){
    alert($("#w3s").attr("href"));
  });
});
```



#### 2.设置

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

> 他们的设置方法就是给("")加想要写的内容即可,会对应修改

设置attr()

```
$("button").click(function(){
  $("#w3s").attr("href","http://www.w3school.com.cn/jquery");
});

有两个参数,先选择属性再选择修改值,用,隔开

或者大括号{}加键值对的方式设置多个属性
$("button").click(function(){
  $("#w3s").attr({
    "href" : "http://www.w3school.com.cn/jquery",
    "title" : "W3School jQuery Tutorial"
  });
});
```

3.添加内容

- append() - 在被选元素的结尾插入内容
- prepend() - 在被选元素的开头插入内容
- after() - 在被选元素之后插入内容
- before() - 在被选元素之前插入内容

()可以存放变量,变量中存放了对应修改的标签或者值

```
var txt1="<p>Text.</p>";              // 以 HTML 创建新元素
var txt2=$("<p></p>").text("Text.");  // 以 jQuery 创建新元素
var txt3=document.createElement("p");
```

### 10.jQuery遍历

1.siblings()找同胞

就是有相同父元素的元素

对应方法

```
siblings()

$(document).ready(function(){
  $("h2").siblings();
});

返回被选择元素的所有同胞(找兄弟)
```

---

2.find()找所有该元素的后代

```
$("p").find("span").css('color','red');

//这是找所有段落 p元素 的span元素,然后对其进行css样式改变
```

3.each() 为每个匹配元素执行函数

```
$("button").click(function(){
  $("li").each(function(){
    alert($(this).text())
  });
});

点击后,选择器选中的元素(这里是所有li元素),每个都执行这个函数
```



### 11.jQuery属性操作

​	有许多对应方法

1. addClass() 方法向被选元素添加一个或多个类。

```
$(selector).addClass(class)
不会移除已有的类,只是添加一个或者多个
```

![image-20210604095432305](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604095432305.png)

2. hasClass() 检测是否包含某个类名

```
$("button").click(function(){
  alert($("p:first").hasClass("intro"));
});

比如这个就是查询第一个p元素有没有intro类
```

他会返回一个布尔值,常用来if条件语句进行状态判断和改变

3.removeClass() 移除某个类名

```
$this.addClass("current").siblings().removeClass("current");

比如这个就是给当前元素添加current类名后他的所有同胞元素移除current类名
```

