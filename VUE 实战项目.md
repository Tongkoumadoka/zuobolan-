# VUE 实战项目

## 0.命名规范

0.1vue-组件的命名

- 类名使用英文小写 + 中划线分隔命名

```
大驼峰命名方法,首字母全大写
{
    path: '/user-management',
    name: 'UserManagement',
    component: Foo
    // 注意没有s !! ,这是对应映射的组件
}
```

比如:![image-20210619205504717](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619205504717.png)

0.2css命名

- 类名

  使用英文小写 + 中划线分隔命名

```
class="main-content"
```

- id名

  小驼峰式命名,首字母小写,其余大写

```
id="myContainer"
```

0.3数据的命名

- 局部变量

  对象包括

  小驼峰法-首字母小写其余大写

  

## 1.项目概述

### 1.1电商项目业务概述

电商项目终端访问方式

- PC
- 移动app
- 移动web
- 微信小程序
- pc后端管理(后台管理员使用)

![image-20210520194223015](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520194223015.png)

### 1.2电商后台管理系统功能

![image-20210520194459848](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520194459848.png)

### 1.3 开发模式(前后端分离)

前端 : 基于 vue 技术的[SPA](https://baike.baidu.com/item/SPA/17536313?fr=aladdin)项目 

#### 前端技术栈: 

- vue 框架
- vue-router 路由
- element -UI 
- Axios 网络通信
- Echarts 

#### 后端技术栈:

- node.js
- Express
- JWT 状态保持工具
- Mysql 数据库
- sequelize 数据库框架

```
SPA 单页富应用程序 只有一张web页面的应用
```

![image-20210520194830377](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520194830377.png)

## 2.项目初始化

### 2.1 前端项目初始化步骤

#### #1.安装 VUE脚手架

全局安装一次就行,之后不需要安装了

#### #2.通过脚手架创建项目

#### #3.配置vue路由

#### #4.安装插件

插件存放位置在啊 plugins文件夹
![image-20210620103233514](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620103233514.png)

- 配置element_ui库

![image-20210619184803521](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619184803521.png)

注意需要配置element UI,全局导入东西太多不方便![image-20210620103102306](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620103102306.png)

- 配置axios库

6.初始化 git 远程仓库

#### #5.安装依赖

- 安装less

- 安装less-loader dev

- 安装axios

#### #6.本地项目托管到GitHub 或者码云

##### @1.生成公钥

![image-20210619195006479](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195006479.png)



##### @1.在码云创建一个新仓库

```
(1)创建一个新仓库
```

```
(2)cmd 执行以下代码
```

![image-20220117155850684](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220117155850684.png)



因为已经创建了一个仓库,所以在本地

![image-20210619195052750](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195052750.png)

```
先输入
git status 查看当前仓库状态
```

![image-20210619195106892](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195106892.png)

```
输入
 git add .
 把文件全部放入暂存区
```

```
git commit -m "add files" 
本地进行一次提交
```

![image-20210619195450678](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195450678.png)

```
再进行一次
git status 
结果如下:

On branch master
nothing to commit, working tree clean
```

本地操作完成



##### @2.将本地仓库上传

在项目的根目录运行这条命令

![image-20210619195600752](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195600752.png)

![image-20210619195746422](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195746422.png)

再执行第二行命令,本地云端进行关联

注意:

第一次输入可能需要密码和账号,之后就不需要了

##### @3.在远程仓库点击刷新,检查上传

![image-20210619195940904](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619195940904.png)





### 2.2后台项目环境安装



## 3.登录登出功能

### 3.1登录概述

![image-20210619200331672](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619200331672.png)

token 解决跨域问题

不存在则用cookie和session



### 3.2登录 -token原理分析

![image-20210619201138629](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619201138629.png)

服务器验证之后的token值就能找到对应用户信息并进行交互



### 3.3登录功能实现

用element-UI组件实现布局

![image-20210619201340476](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619201340476.png)

#### #1.打开项目,查看终端

查看当前工作区是否干净

```
git status
```

![image-20210619201525837](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619201525837.png)

输出: 证明已经干净

```
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

![image-20210619201644067](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619201644067.png)

#### #2.创建一个分支

当开发新功能时创建一个新分支,开发完毕后再合并到主分支

```
master branch
```

```
git checkout -b 分支名字
git checkout -b login
```

提示结果: 告诉你已经创建一个新分支

```
Switched to a new branch 'login'
```

![image-20210619201906193](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619201906193.png)

#### #3.查看当前项目所有分支

```
git branch
```

![image-20210619202030813](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619202030813.png)

#### #4.梳理项目的结构

在vue-cli可视化面板中-任务-serve-运行-启动app-自动打开默认页面

![image-20210619202254174](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619202254174.png)

###### #梳理-app.vue

清除app根组件中的默认模板,样式,脚本

![image-20210619202537427](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619202537427.png)

###### #梳理-routers

- 删除routes内的路由关系
- 删除引入的组件 Import
- 再删除对应的 home about组件
- 删除components/ helloworld组件

![image-20210619202734661](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619202734661.png)

### 3.4创建登录组件

#### #1.在components 文件夹中创建 login.vue

![image-20210619203109691](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619203109691.png)

推荐less 语法格式,控制==样式在当前组件生效== scoped

#### #2.组件的路由设置

- 导入组件到router/index.js

```
import Login from '../components/Login.vue'
注意组件名称必须大写,大驼峰
```

- 在 routes 中写好路径

```
{ path: '/login', component: Login }
```

#### #3.在app.vue 或者页面.vue 中引入该组件

```
    <router-view></router-view>
```

![image-20210619205902454](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619205902454.png)

路由匹配到的组件会到该标签内渲染

![image-20210619210051635](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619210051635.png)

#### #4.设置访问根路径的自动重定向

注意:根地址是

```
path:'/'  是/这个地址
```

![image-20210619210316802](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619210316802.png)

##### <1.在routes 中添加重定向规则

```
  { path: '/', redirect: '/login' },
```

![image-20210619210501282](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619210501282.png)

作用为:当用户访问'/'地址会自动重定向到'/login'地址

### 3.5登录组件基本页面布局

#### #1.创建全局样式表

#创建 global.css

![image-20210619213526020](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619213526020.png)

global.css控制全局的公共样式

#创建之后导入到main.js

![image-20210619213723488](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619213723488.png)

#### #2.创建login.vue基本结构

容纳整个背景的盒子 login-container

```css
.login-container{
    //继承HTML传递而来的高度,必须要写,不设置高度就只能用文本撑开div盒子,背景图片无法撑开盒子!!
  height: 100%;
  background-image: url('../assets/bgd.jpeg');
  background-size: 100% 100%;
}
```



容纳注册面板的盒子 login-box

```css
//设置了固定宽高
.login-box {
  width: 450px;
  height: 300px;
  background: #eee;
  border-radius: 3px;
    
  //水平垂直居中对齐
  position: absolute;
  left: 50%;
  top: 50%;
  transform:translate(-50%, -50%)
  //注意用 逗号隔开
}
```



#### #3.设置login中的表单

使用element ui插件,需要导入插件

plugins->elenment.js中手动导入需要的组件

![image-20210620103758470](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620103758470.png)

导入之后调用VUE.use(),告诉vue要使用这些插件

![image-20210620104024479](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620104024479.png)

```html
<!-- 表单 -->
      <el-form label-width="0px" class="login-box-form">
          //label-width宽度为输入框距离左边缩进长度
        <!-- 用户名 -->
        <el-form-item>
          <el-input></el-input>
        </el-form-item>
        <!-- 密码 -->
        <el-form-item>
          <el-input></el-input>
        </el-form-item>
        <!-- 按钮 -->
         <el-form-item class="btns">
           <el-button type="primary">登录</el-button>
           <el-button type="primary">重置</el-button>
        </el-form-item>
      </el-form>

//设置表单宽度为100%可以让input长度达到父盒子一样长
```

注意:

```
表单默认为box-sizing: content-box;会溢出,所以需要修改为
box-sizing: border-box;
```

![image-20210620143326003](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620143326003.png)



#### #4.给输入框添加前面的图标

![image-20210620143612602](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620143612602.png)

![image-20210620143724346](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620143724346.png)

```
在imput 属性内设置 prefix-icon="el-icon-search" 属性
```

#在第三方图标库获取自定义的图标

​	1.首先在阿里图标库购物车中下载代码

![image-20210620144137129](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620144137129.png)

2.下载文件解压后

![image-20210620144205529](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620144205529.png)

3.把文件重名名为font,放到assets

![image-20210620144458827](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620144458827.png)

4.在入口文件.main.js导入字体图标

````
import './assets/fonts/iconfont.css'
````

5.在需要替换图标的vue组件中替换

```
<span class="iconfont icon-xxx"></span>
也就是添加一个固定iconfont的类名,和对应需要文件的类名
```

![image-20210620144828695](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620144828695.png)

```html
   <el-input  prefix-icon="iconfont icon-password"></el-input>
     <el-input  prefix-icon="iconfont icon-yonghu"></el-input>
```

#### #5.实现表单数据绑定

首先为整个表单设置一个form表单对象,对象中设置很多对应的属性,将表单中的imput等组件绑定 form对象对应的属性. 

均使用==v-model==

![image-20210620150929218](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620150929218.png)

#6.设置变单验证添加

![image-20210620151120152](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620151120152.png)

为数据data设置一个 rule:属性,他是一个对象,存储着数组形式的具体验证规则

```
  name: [
            { required: true, message: '请输入活动名称', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
          ],
```

1.首先给表单整体的rules属性绑定验证规则对象

```
:rules="loginFormRules"
loginFormRules设置在data内
```

2.给不同的表单项指定props属性验证不同的规则

```
设置必填
{ required: true, message: '请输入活动名称', trigger: 'blur' },
 require 表示是必填项
 trigger 触发时机,文本框失去焦点时就触发检测
设置长度区间 
 { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
```

#### #6.表单的重置

调用 函数,拿到表单实例对象再调用

如何拿到实例对象?

- 给表单加ref引用

````
      <el-form ref="loginFormRef">
````

- 给重置按钮绑定重置事件

```
           <el-button type="info" @click="resetLoginForm">重置</el-button>
```

- 在methods中定义处理函数

  ````
  methods: {
      //重置登录
      resetLoginForm () {
        console.log(this)
      }
    }
    this指向当前组件vc
    调用 vc.$refs.loginFormRef
    就是表单实例对象
   
  ````

#### #7.表单登录预验证的结果判断

我们设置的表单验证规则rules,在满足所有情况下才允许发送登录请求

```javascript
这就需要调用,element Uiform组件自带的 valiadate(callback)函数
里面的回调函数传递参数valid,也就是是否通过验证的布尔值
 login () {
      // 登录前预验证
      this.$refs.loginFormRef.validate(valid => {
        // console.log(valid)
        if(!valid) //false
      })
```

#### #8.配置axios

后台交互发送数据包就必须先在main.js引入axios插件

```javascript
//导入axios
import axios from 'axios'
Vue.prototype.$http = axios
//挂载到vue原型对象上
```

这样每个vue组件都可以通过 this直接访问到$http,从而发起axios请求

#配置axios的基准地址

```javascript
// 设置根路径
axios.defaults.baseURL = 'http://127.0.0.1:8888/api/private/v1/'
//后台接口提供
```

然后就可以用this.$http发起axios请求

### 3.6主页布局

![image-20210620154331529](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620154331529.png)

#1.注册对应组件

## ==常见错误==

#### #1.Syntax Error: TypeError: this.getOptions is not a function

如果代码没错就是版本问题:

```
我在安装less-loader/sass-loader时报错,他的版本太高了
```

解决:卸载安装低版本

```javascript
sass
npm uninstall --save sass-loader // 卸载
npm i -D sass-loader@8.x // 安装
npm uninstall --save node-sass // 卸载
npm i node-sass@4.14.1 // 安装
// 如果node-sass安装失败，也可以直接在package.json中写上版本号，删除node_modules文件夹，重新npm i即可
```

![image-20210619212143077](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619212143077.png)

```
less
// 卸载
npm uninstall --save less-loader
// 安装
npm install -D less-loader@7.x
```

![image-20210619212848584](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619212848584.png)

改到要求版本,因为默认安装的是最新版本,修改在vscode终端内进行



#### #2.element 表单数据绑定失效无法校验

![image-20210620174625153](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620174625153.png)

原因是ele-ui里面的==表单本身==必须用 ==:model==绑定数据!!!!!

```html
      <el-form ref="loginFormRef" label-width="0px" class="login-box-form" :model="loginForm" :rules="loginFormRules">

```

表单==组件==用==v-model==绑定数据!!!!!

```html
          <el-input  prefix-icon="iconfont icon-yonghu" v-model="loginForm.username"></el-input>

```

否则所有数据都无法绑定报错





## ==实用技巧==

#### #1.把Chrome调试器位置换到右边

修改位置:

![image-20210619213951659](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619213951659.png)

#### #2.快速清理 vue 项目中的 node_modules,再重新安装

![image-20210620112826539](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210620112826539.png)

```
npm install rimraf -g
rimraf node_modules
```

注意要到对应项目文件夹中执行

如果无法删除报错的话

```
就用管理员身份运行cmd再删除
```



\1. 安装rimraf ： cnpm install rimraf -g

\2. 执行： rimraf node_modules 删除文件荚 

\3. 清空缓存： npm cache clean --force

\4. 重新安装淘宝镜像： npm install -g cnpm --registry=https://registry.npm.taobao.org

\5. 再次执行：cnpm i

#### #3.本地文件上传码云更新

#4.element UI组件名称就是一个类名
