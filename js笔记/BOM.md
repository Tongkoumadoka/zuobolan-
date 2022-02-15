BOM

1.BOM是什么



2.window对象

- document也是window对象的属性之一
- 所有JS全局对象,函数,变量都是window对象的成员(属性/方法)
- 

3.确定window窗口的尺寸

**==window.innerHeight==**

包括滚动条,但是不包括菜单栏等杂项

**==window.outerHeight==**

浏览器窗口全部包含



注意窗口模式如果有边框的话,innerheight是不包括边框的



![img](https://upload-images.jianshu.io/upload_images/1666407-bef83328a7244f3e.png?imageMogr2/auto-orient/strip|imageView2/2/w/738/format/webp)

==scrollX、scrollY==

返回的是整个浏览器距离桌面顶部和左边的距离

![img](https://upload-images.jianshu.io/upload_images/1666407-426f24f504b66326.jpg?imageMogr2/auto-orient/strip|imageView2/2/format/webp)

4.screen 对象

5.location 对象

- location.hostname 返回 web 主机的域名
- location.pathname 返回当前页面的路径和文件名
- location.port 返回 web 主机的端口 （80 或 443）
- location.protocol 返回所使用的 web 协议（http: 或 https:）

使用location.assign() 方法可以跳转到新页面

```javascript
function newDoc(){
   window.location.assign("https://www.runoob.com")
}
```

6.history 对象

- history.back() - 与在浏览器点击后退按钮相同
- history.forward() - 与在浏览器中点击向前按钮相同

用来跳转历史页面

7.navigator 对象

可以调用一些内置属性来知道浏览器的相关信息

8.cookie

9.正则表达式

```
/正则表达式主体/修饰符(可选)
比如
/soda/i i不区分大小写
```



一些方法

9.1 search()

返回搜索结果对应的起始位置

```javascript
var str = "Visit Runoob!"; 
var n = str.search(/Runoob/i);
你要输入正则表达式

var str = "Visit Runoob!"; 
var n = str.search("Runoob");
也可以输入字符串
```



9.2replace()

```
var str = document.getElementById("demo").innerHTML; 
var txt = str.replace(/microsoft/i,"Runoob");
用"a"替换"b"

字符串和正则都行
```

9.3正则表达式 的修饰符和模式

修饰符:

![image-20210604155710346](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604155710346.png)

