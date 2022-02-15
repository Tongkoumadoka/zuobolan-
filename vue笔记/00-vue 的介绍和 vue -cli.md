## 00-vue 的介绍和 vue -cli

### 1.MVVM模式

![image-20210520212827498](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520212827498.png)

>MVVM模式的结构:

- model : 负责数据存储
- view : 负责页面展示
- view model :负责业务逻辑处理 (Ajax请求),对数据进行加工后交给视图展示(vue-实例对象  vm )

// 视图和数据通过VUE作为中介绑定

![image-20210608093549486](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608093549486.png)

>旧MVC模式的结构:

- M model 模型  控制数据 js变量
- V  View 视图 用户实际接触的界面(交互)
- C control 控制器 事件交互 如何根据用户在界面的行为改变后台数据和视图(dom对象绑定事件,修改变量) 

// MVC设计模式,



### 2.框架和库的区分

> 框架: 框架是一套完整的解决放啊安

如果一个项目要更换框架,就要重构整个项目

> 库(插件):只提供某一个或者某些小功能

如果某个库无法完成某些需求,可以切换到其他库实现

//可以想象红警里面的阵营(框架)和有各种功能的单位(库)

扩展插件

![image-20210608104656176](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608104656176.png)`

### 3.vue 的发展

2016 10 发布2.0



### 4.vue的使用方式

4.1生产版本: 只用于测试和调试,开发不使用

直接引用框架就可以使用

```html
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

//#也可以直接跳转到源码,下载到本地方便使用

```
https://cdn.jsdelivr.net/npm/vue/dist/vue.js
```

//我推荐直接下载vue.js再到文件中引用比较合适



4.2

检测vue-cli 的版本

```
vue -V
```



```
vue ui 跳转出项目页面
```

4.3给vue项目安装element UI插件

```
搜索插件
vue-cli-plugin-element 
安装

然后进行插件配置
```

![image-20210602224434321](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602224434321.png)

4.4.配置axios

安装依赖

```
添加插件,安装为运行依赖
axios
```

4.5.Windows shell

![image-20210602225944916](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602225944916.png)

4.6后台项目的环境安装配置

- MySQL数据库安装
- 安装nodejs
- ![image-20210602230809315](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602230809315.png)

4.7

token方法 存在跨域问题

![image-20210602231359673](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602231359673.png)

4.8写登录页面

![image-20210602231556066](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602231556066.png)

用VScode打开项目文件

![image-20210602231741527](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602231741527.png)





开发新功能都是用branch,然后加到master branch上

```
git checkout -b login(分支名称)
创建子分支
```

![image-20210602231922398](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602231922398.png)

```
查看当前有哪些分支
*正在打开的
```

![image-20210602232047284](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602232047284.png)

![image-20210602232547426](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210602232547426.png)



scoped 表示样式只在当前组件生效,否则全局生效,单文件组件一定要scoped



路由规则重定向

只要你访问主页就直接跳转到login页面

```
vue cli 里面的 注释必须
// 跳转到登录页面 要空一格,否则报错
```

element UI是按需导入,你用到什么组件就得自己导入什么组件到element.js plugins文件夹

![image-20210603091126159](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210603091126159.png)

label相关的属性就是预留给输入栏介绍的空间

比如label-width就是预留多少宽度



```
justify-content: flex-end;
作用是什么?
```



```
现代浏览器和IE9+默认值是content-box。
width百分比加padding一定会超过父盒子尺寸,从而出现图片或者文字溢出容器,这时候就需要改为border-box

实际上就是让padding和border都被包含在width:100%里面,面得溢出
width: 100%;
padding: 0 20px;
box-sizing: border-box;
  
```

- content-box：标准盒模型，又叫做 W3C盒模型，一般在现代浏览器中使用的都是这个盒模型
- border-box：怪异盒模型，低版本IE浏览器中的盒模型

content-box：padding和border不被包含在定义的width和height之内。
盒子的实际宽度=设置的width+padding+border
border-box：padding和border被包含在定义的width和height之内。
盒子的实际宽度=设置的width（padding和border不会影响实际宽度



4.11

```
prefix-icon="el-icon-search"
注意给input组件加图标的话要写到
 <el-input prefix-icon="el-icon-search"></el-input>
 写到input标签属性里面去!
```





4.12怎么更改图标

- 在阿里图标网购物车下载
- 把下载的放到项目中的font文件夹
- 在main.js中导入
- ![image-20210603094857786](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210603094857786.png)

- 更换图标

![image-20210603095047127](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210603095047127.png)

![image-20210603095106807](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210603095106807.png)在下载给的HTML文件里面找,教程也在里面这是font-class方法

prefix-icon属性添加前置图标

4.13表单绑定

注意表单采用v-model而不是v-bind !

```
:model 是表单绑定属性
```

然后为每一个输入框input添加对应的v-model属性实现双向绑定



注意密码框最后要添加 type =password 属性,因为el-input不带这个东西

4.14表单数据验证行为

```
<el-form :model="ruleForm" :rules="rules"
```

让规则生效需要指定props

```
 loginFormRules:{
        // 表单验证规则对象
        username:[
          { required: true, message: '请输入登录名称', trigger: 'blur' },
          { min: 3, max: 10, message: '长度在 3 到 10 个字符', trigger: 'blur' }
        ],
        // 验证密码
        password:[
            { required: true, message: '请输入正确的密码', trigger: 'blur' },
            { min: 6, max: 12, message: '长度在 6 到 12 个字符', trigger: 'blur' }
        ]
      }
      
      //最后一个数据不要加逗号,!!!!
```

4.14表单的重置

调用

```
resetFields 方法
```

先拿到表单的实际对象,然后再对表单进行调用

注意给表单标签 form添加ref=



因为点击重置就重置,所以需要给他绑定一个单击事件来触发

4.15 登录前的预验证

在提交表单数据前对其进行预验证,只有通过了才允许发起访问请求,否则告诉用户错误

```
validate 用该函数,同样是使用表单引用对象
```



学学箭头函数的用法es6新增

```
login() {
      this.$refs.loginFormRef.validate((valid)=>{
          console.log(valid);
      });
    }
    
    格式类似于
    () => {}
    这是匿名箭头函数
    
    调用的第一个形参valid是个布尔值,通过它的结果我们可以知道到底验证是否通过没有
```

根据预验证结果来决定是否发送

P22再看几遍



4.16配置消息提示

UI message 

因为是新组件所以还是得element.js中导入

4.17

html:height:100% 是相对于浏览器的本身的高度.这是可以获取到的.在dom中用**window.innerHeight** 这是在 html文件加载就自动形成的.

4.18 flex-wrap: wrap;

作用

父盒子设置overflow的话子盒子绝对定位的溢出部分也会被隐藏

4.19

vue所调用的函数,都不要写成箭头函数

### 5.vue-数据代理原理

在new vue 对象时,就已经后台传递了参数,但是它只传递了有且只有一个的VUE实例对象

data里面的属性都可以用 vm.属性名得到

![image-20210608102854181](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608102854181.png)



为什么需要数据代理?

多出一个_data在vm中传递数据的理由是什么?为什么需要如此大费周章?

答案在于:这样可以更好的监听数据

因为vm和视图数据是动态绑定的,比如当name数据发生变化时,对应视图也要修改.那么vm怎么知道数据更改了?

显然vm必须监听对应的属性数据,所以必须监视数据.

如果把属性数据全部挂到vm实例本身,那么vm就必须监听整个vm的所有属性和对象接口,好像我就想知道超市哪儿有卖西瓜,却必须在整个长沙市地图遍历的找

而_data数据代理,让vm只需要专注它就可以监听所有data数据,等价于范围缩小到一个超市,更加高效得多



本质就是缩小范围,数据监听集中化

![image-20210608104311600](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608104311600.png)

所以这也是不在data外面设置属性的原因

自身反向赋值

![image-20210608110446405](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608110446405.png)

### 6.vue 事件处理

### 7.语法检查的临时关闭方式



```
eslint-disable-next-line
下一行不进行语法检查

eslint-disable
整个脚本都不进行语法检查
```

![image-20210616135756284](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616135756284.png)

==解决方法==

自己手动配置一个vue.config.js文件关闭
