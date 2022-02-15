## vue-router

### 严格匹配静态路由方法

#### 1.页面实现 (在对应HTML模板中)

​	**一般app.vue中写**

-  <router-link ></router-link>

```html
 <router-link ></router-link>
 定义页面中点击的部分: 可以想象成 a链接 
 
 <router-link  to="/home">Home</router-link>
 同时 它的to属性规定了点击他会从哪里把组件
```

- <router-view></router-view>

```html
<router-view></router-view>
定义显示部分: 点击后,内容就显示在这里面
```



#### 2.在index.js 中配置路由

- 这个js文件一般在 router 文件下属 index.js(router.js)文件集体配置整个应用的路由

```javascript
先定义 route/routes

// 一条路由是一个对象,一组路由用数组存储这些对象
const routes = [
  { path: '/home', component: Home },
  { path: '/about', component: About }
]
```

- 引入 Router 插件

```javascript
import Router from 'vue-router'
```

![image-20210616173856656](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616173856656.png)

- 告诉vue要使用router插件

```javascript
Vue.use(Router)
绝对不能少,插件都得用进过use()方法
```

- 设置路由器 router

```javascript
export default new VueRouter({
 //构造函数和暴露接口一起干了
 routes: [
    {
      path: '/',
      name: 'HelloWorld',
      component: HelloWorld
    }
  ]
})


//当然也可以先定义再暴露
const router = new VueRouter({
      routes // routes: routes 的简写
})
export default router
```

#### 3.在vm实例中引入 router 

因为vm实例在 main.js文件中,所以还需要接收暴露的router对象

```javascript
import router from './router'
```

然后再vm实例中引入router属性

```javascript
const app = new Vue({
  router
}).$mount('#app')
```



#### 4.主页面的重定向问题

​	问题出现原因:

​	当首次进入页面的时候，页面中并没有显示任何内容。

​	这是因为首次进入页面时，它的路径是 '/'，我们并没有给这个路径做相应的配置。 

如果依旧在router中对应配置一个route

```
{ path: '/', component: Home }
结果会报错
原因在于: 两个不同的路径path,指向了同一个组件
```

==解决方法==:重定向

```
重定向本质是重新给你一个path ,虽然它访问的是 '/'这个地址,但是浏览器给它的确是'/home'这个设置好的地址,这样就自动跳转到home页面了
```

```javascript
const routes = [
    {
        path:"/home",
        component: home
    },
    {
        path: "/about",
        component: about
    },
    // 重定向
    {
        path: '/', 
        redirect: '/home'  // 重定向到初始页面 home
    }
]
```

// 比如写注册页面也得这样做,重定向到login.html



#### 5.执行过程

- 当用户点击 router-link标签 ,(超链接样式),就会寻找 to 属性指向的地址

- 然后比较:它的 to 属性和 js 中配置的路径{ path: '/home', component: Home} path 一一对应，从而找到了匹配的组件

- 最后把组件渲染到 <router-view> 标签所在的地方。所有的这些实现才是基于hash 实现的。



注意:

- 配置哪个子组件的路由,就要在index.js里面引入这个子组件

- index.js也要最基本的插件支持,比如 vue 比如 它自身的vuerouter

- router-link 和router-view 标签一一对应，成对出现

- 引入的文件 在module里面对应文件夹都能找到

  ![image-20210616174259335](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616174259335.png)

结论

1.配置路由本质配置的是 路由到组件的映射

#### 6.实现机理

#### 7.路由路径的引入方式

![image-20210622131826705](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622131826705.png)

```
@是webpack中设置的路径别名
```

#### 8.工程化中route的属性值

![image-20210622132906843](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622132906843.png)

meta属性中的信息可以用到配置菜单中

```javascript
component: () => import('@/views/setting/roleManagement'),
    子组件的按需注册
```



![image-20210622140243328](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622140243328.png)

#### 9.路由嵌套

注意children的路径不需要加'/',因为添加/默认从根路径开始

children路由配置类似于routes路径配置,不过把父路由的path作为起始路径位置了

![image-20210622135528449](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622135528449.png)

#### 10.路由访问

配置注入路由后,我们可以在**任何组件**中,使用 ==this.$router==访问路由器 router

注意为什么使用this.$router 而不是router ,是因为对于每一个独立的组件来说,使用router还需要import它

而我们在main.js引入 router后 ,同时也把$router 挂载到vue实例中vm上,各个组件vc由于继承性也能直接调用this.$router,就无需再额外进行多余的路由模块引用操作



##### @1.区别$route和$router

$route是路由路径相关信息的一个对象

比如动态路由的参数 $route.paramas

```
调用方法
this.$router
this.$route

```

Geography/2015_Book_PlantSelectionForBioretentionS



![image-20220208105321913](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220208105321913.png)



![image-20220208110021934](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220208110021934.png)

![image-20220208110020421](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220208110020421.png)

### 动态路由配置

#### 1.原因为什么要配置动态路由?

#因为静态路由实现跳转要求

- router-link 中 to 属性值和 路由表中对应path 必须一样

![image-20210616180608391](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616180608391.png)

#但是对于登录网站等有用户交互的界面

不同的用户映射到同一个组件上

用户登录后跳转的界面 会输出 欢迎 {该用户特有信息,比如id 之类的},这必然需要用到某个(多个)组件 user

如果写死的话,所有的用户的不同信息该怎么显示和配置

显然需要动态设置一部分,因为用户id等路由信息是变化的

```javascript
 { path:"/user/:id", component: user }.
 在 router中,动态路径参数”(dynamic segment) 以冒号开头
```



#### 2.获取动态部分的方式

​	其实，当整个vue-router 注入到根实例后，在组件的内部，可以通过==this.$route== 来获取到 router 实例

````
$route.params.id
路由中有属性params,它是一个对象

属性名，就是路径中定义的动态部分 id
属性值就是router-link中to 属性中的动态部分
````

![image-20210617092305952](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617092305952.png)

![image-20210623131829058](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623131829058.png)

设置多段路径参数

![image-20210623132021093](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623132021093.png)



### $emit , ref props 组件数据传递

| 类型  |        |
| ----- | ------ |
| ref   | 子传父 |
| $emit | 子传父 |
| props | 父传子 |

1.ref 

通过在子组件/原生DOM上设置ref 属性

```html
<child ref="msg">父组件中使用的子组件child</child>
等价于把整个子组件实例本身放到 msg这个变量(属性)中

通过调用this.$ref.msg.
就可以在父组件中调用子组件的方法和属性,实现子传父
```

2.$emit

```
通过触发事件将子组件数据以参数形式传递给父组件内方法(参数)

```

3.props

```html
prop是子组件的内置属性,它可以自定义子组件标签的属性
<child :child-tag-property="father-tag-data">父组件中使用的子组件child</child>
父组件data数据变量可以通过v-bind绑定这个自定义属性
然后子组件可以定义一个本地data接收这个数据
```

```javascript
props: ['initialCounter'],
data: function () {
  return {
    counter: this.initialCounter
      //用counter接收
  }
}
```

## router的一些常用的配置处理

#1.错误路由路径处理

输入的路由地址无法在routes匹配

```javascript
 {
    path: '*', //会匹配所有路径
    redirect: '/404',
    hidden: true,
  },
  //添加routes:
  //   当无法匹配自动跳转404页面,如果你做了404组件的话
      //通常放到routes最后
```

### 导航守卫





## @常见错误解决

#### @1.The "EbookReader" component has been registered but not used  vue/no-unused-components  

```html
报错原因
@1.组件引入了但是没有被该页面使用
也就是template中要有:
 <ebook-reader></ebook-reader>

@2.组件使用时标签错误
<ebook-reader></ebook-reader>
注意标签是全小写的,不能直接用注册名

@3.eslint规定引入组件注册组件名时必须大写字母开头
EbookReader
```

![image-20220208095308216](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220208095308216.png)

正确的组件引入页面的方式:

```vue
<template>
  <div class="ebook">
      // (3)必须调用组件,而且标签名小写
    <ebook-reader></ebook-reader>
  </div>
</template>

<script>
// (1)作为ebook父组件引入ebookreader实现动态路由
import EbookReader from '../../components/ebook/EbookReader.vue'
export default {
  components: {
    // (2)注册组件  
    EbookReader
  }
}
</script>
```

