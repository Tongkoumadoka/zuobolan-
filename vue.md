vue

html+css+js 给用户看,刷新数据给后端

网络通信:axios

页面跳转:vue_router

状态管理 vuex

vue-UI



CSS预处理器

因为直接改css特别麻烦,也不好操作,所以专门又设计了一种编程语言,进行web页面样式设计,然后编译器转化成正常的css文件



常见的有

sass(基于ruby,服务端处理,难度高于less)

less(基于nodejs客户端处理,简单)

多了变量声明,嵌套



let在es6版,但是不兼容需要打包

于是就用webpack打包成es5支持

mvvm 数据双向绑定 angular提出的

react Facebook出品,js前端框架,虚拟dom内存中模拟dom操作,

计算属性(vue特色)-->学jsx元

vue渐进式,就是慢慢更新新特性,

就是MVVM+dom集成

axios:前端通信框架,只做通信.vue就是用来处理dom,所以用axios与服务器狡猾,jqury中的Ajax也可以



UI框架

anti-design 阿里巴巴 基于react

elementUI,ice 饿了么 基于vue

bootstrap Twitter用于前端开发的开源工具包

amazaui: 很简单 



JavaScript构建工具

webpack打包工具



前端目的

三端统一开发 (pc,android:apk,ios:ipa)

并且能够调用到设备底层硬件

云打包 Hbuild->HbuildX,API Cloud

本地打包 cordova

WeUi 微信小程序UI

soc原则

关注度分离原则

mvvm模式,是一种软件架构,以事件驱动编程,来源于mvc

本质,分离视图和模型

vue核心就是dom监听和数据绑定

vm就是双向绑定层,视图状态和行为全部被封装到vm中

mvvm的核心是viewmodel对象(层),负责转换model中的数据对象让其更方便管理

vue是一个对象

el指的是element,用element对象去绑定某个元素或者标签

data也是个对象

var 定义的vue对象绑定的值和后端双向绑定,不刷新页面也会同步变化,vue不改变dom对象

react就是实时监听变化,就是虚拟dom,没有操作dom对象

1.v-bind用来绑定元素内属性从而动态即时操作其值

{{变量}}则是用来模拟操作dom元素对象innerHTML值来修改标签内内容

2.v-开头的都被称为指令,表示是vue提供的特性,响应式行为

3.判断-循环

v-if v-else

```
<h1 v-if="ok">yes</h1>
<h1 v-else-if>g</h1>
<h1 v-else>no</h1>
data:{
  ok: true
}
//还有v-else-if的嵌套
```

for/if

4.数组

```
<li v-for="it in items">
	{{it.message}}
</li>

//1.这里的items绑定的是data对象中的items属性,也就是代表一个数组对象
//2.it则是数组中的元素对象,代表一个又一个单独的内容
//3.调用数组内的元素,则用单个元素it,它代表{message:'对象'},它是个对象元素,然后再调用它的内部属性message,就会遍历得到所有'对应值'
it.message,

data:{
	items:[
		{message:'对象1'},
		{message:'对象2'}
	]
}
//1.数组格式为名称:[]
//2.数组内元素如果为对象变量,则用大括号{}
//3.对象变量有属性也有方法,写法为 {对象变量内属性名称:'值'} 
```

5.methods

方法必须定义在vue的methods对象中,v-on绑定事件

函数名:function(){}定义到内部

this指向var vm的对象vm,对象本身

this.message=this.data.message 源码里面设置可以访问

6.v-model实现数据双向绑定,输入的数据和显示的数据双向绑定,同时变化

重要在于输入数据在动态变化

input 和textarea 等

v-model同步绑定的是输入的值,复选框绑定值用数组输出,单选用布尔值,和选择值value,select下拉框用选择框内值textarea用文本值

```
<div id="example-5">
  <select v-model="selected">
    <option disabled value="">请选择</option>
    //预留项
    <option>A</option>
    <option>B</option>
    <option>C</option>
  </select>
  //取出选中值:
  <span>Selected: {{ selected }}</span>
</div>

//选中谁就输出谁,比如a输出a
```



7.vue组件(可复用vue实例)

vue 对象创建

定义组件

v-bind:qin='item'

vue.component("myhead",{

//但是接收hello这个data中定义的变量还需要告诉组件接收,而不是直接显示文本,所以用props

//传递给组件的值,只能用props接收

​	props :['qin'],

​	template:'<li>{{qin}}</li>'

});

意思是我用myhead 就等价于写了template(模板)里面的东西

写<myhead></myhead> 等价于==<li>{{hello}}</li>

通过这种方法就可以调用双向绑定变量并动态变化



自己定义一个标签,自命名



Prop 是你可以在组件上注册的一些自定义 attribute,自定义属性



7.axios 网路通信 异步通信框架,用来实现Ajax异步通信

基于es6规范!!!!!!,不调到es6会报错,webpack用来兼容

jQuery.Ajax()可以但是操作dom不建议

vue有生命周期!!

创建到死亡的过程

先加载模板再渲染数据

链式编程

var vm =new Vue(){

​	el:'#vue',

​	data:{}属性是vm固有的

​	data(){}但是还有data方法

​	data(){ //方法

​		return{//return就是接收axios中后台传来的信息response

​	info:{ //请求返回的参数内容必须和json字符串一样,比如有name属性传过来,info就要设置对应的name接收,传多少设置对应多少

​	name:null,

​	url:

​	address:{

​	street:null,

​	city:null

//只是摆格式,没有值,相办法接收就完事了	

​	}

​	}

​	}

​	},

​	mounted(){/链式编程,then然后响应,=>指向要产生的事情

​	axios.get('../data.json').then(response=>(this.info=response.data));

//response中data的数据赋值给了info,this就是指代vm vue对象

}

//我们向后台请求的数据希望绑定到vue对象中的data属性变量中来!!

}

绑定属性后调用

v-bind:href="info.url"

调用,

<div>{{info.name}}<div>

```
<style>
[v-clock]{
   display:name;
}
//作用:加载过程白屏,隐藏模板不备用户看见
</style>
```

json函数本地设置

8.计算属性--特色

动词+名词,就是先计算出一个结果,然后保存再一个属性~中,好处:在内存中运行,可以想象成缓存

调用方法必须括号调用{{currentfunction()}},而且该函数方法有return返回值

data.now()调用时间戳

methods调用通过方法

计算属性

computed:{

//计算属性,可以重名,但是会覆盖,使用不建议重名,methods优先级高一点

方法

}

computed调用通过属性!!这就是两者区别

{{currentfunction}}

p11再看一遍

节约开销

9.插槽slot 元素

vue文件需要初始化环境 ,npm

ctrl+c停止

10.webpack 静态模块js打包器

兼容打包工具



webapp

commonsJS规范 nodejs遵守

优点:应用export和import接口来定义作用域暴露接口

缺点:同步加载,浏览器本身是要异步加载

于是改进成异步非阻塞

AMD提供异步加载,开发成本高

实现 curl和requires

最后es6模块

尽量静态化编译,编译时确定模块的依赖关系

以及输入输出的变量

静态分析



es6使用严格检查模式 strict

vue router是官方路由器,由vue.js集成

安装还是 npm install vue-router --save-dev 保存开发配置

开发在scr中

import vueRouter from 'vue-router'(它本身也是一个标准的前端工程)

//显示声明使用vuerouter

vue.use(vuerouter);

同理安装axios也是如此

先安装,再导入import,再使用vue.use(插件)

路由路径 path

跳转组件 component:

前端自己就能跳,不需要请求后端

router-link to ="url"就等于a标签

layui组件,弹窗组件