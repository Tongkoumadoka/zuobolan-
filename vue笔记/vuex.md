## vuex

#### 1.vuex是什么

vuex是vue 的 一个插件 集中式

>对vue应用中 多个组件的 共享状态 进行集中的管理(读写)

vue的应用就是状态自管理应用

1.1什么是状态自管理应用

![image-20210617100536251](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617100536251.png)

![image-20210617100418332](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617100418332.png)

注意:

state:本质就是数据

声明方式:就是{{data}},插值语法

actions: 就是多个函数代表的多个行为



1.2多组件共享状态问题

 就是多个组件同时公有一个状态,并且还要进行操作

不同视图的行为需要变更同一个状态(state)



以前解决方式为:

- 把数据和操作数据的行为全放父组件
- 然后传递给子组件,要多级传递

vuex就是解决这个问题产生的

#### 2.vue的核心概念和API

![image-20210617101102662](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617101102662.png)

通过mutations来更新state

state 和 getters 作用一样

##### 2.1 state

对象

![image-20210617101302723](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617101302723.png)

##### 2.2mutations

对象

##### 2.3actions

对象

commit() 执行后返回一个promise对象,可以直接进行异步处理 

promise.then()

##### 2.4getters

属性的get()方法

##### 2.5 store

对象

所有vuex管理的组件都多了一个属性$store

##### 2.6 backend API

和后台交互,发送ajax请求

因为action可能要从后台获取数据再请求mutations

##### 2.7 devtools

Chrome的开发工具

监视mutations的调用,只要调用就记录

#### 3.vuex 的安装

##### 3.1下载vuex

```
npm install --save vuex
```

##### 3.2创建store.js vuex核心配置文件

和main.js同级

- 在其中引入vuex 和 vue

```
import Vuex from 'vuex'
import Vue from 'vue'
```

- 让vue使用vuex插件

```
Vue.use(Vuex)
```

- 暴露vuex模块 store对象

```javascript

//状态对象
const states = {

}

// 包含多个更新state函数的对象
const mutations = {

}

//包含对应事件回调函数的对象
const actions = {

}

//包含多个getter计算属性函数的对象
const getters = {

}

export default new Vuex.Store({
  state, //状态对象
  mutations, // 包含多个更新state函数的对象
  actions, //包含对应事件回调函数的对象
  getters //包含多个getter计算属性函数的对象
})

```

- 在main.js引入 暴露的store对象 

```
import store from './store.js
```

- 把公共管理的属性写到store.js中states对象里

注意:

- state 属性没有s
- 其他属性为复数,有s
- 实际的调用

![image-20210617104009097](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617104009097.png)





##### 3.3组件如何和vuex关联	

![image-20210617103120831](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617103120831.png)

只要得到store对象就可以调用它的属性 data,从而调用数据

问题变成了组件怎么得到store对象

解决方法:在main.js文件中vue实例映射store对象

![image-20210617103313586](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617103313586.png)

因为所有组件vc都继承vm实例的属性和方法,所有所有的组件也继承了在vm中的store对象

他们可以调用 $store 

```
{{$store.state.count}}
```



##### 3.4 4属性关联步骤

- 首先把共用的属性放到state里

![image-20210617110331841](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617110331841.png)

- 把函数的methods改写到

![image-20210617110444933](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617110444933.png)

this.$store.dispatch('action中的方法名称')

- 改写对应的action中函数

![image-20210617110526456](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617110526456.png)

- 改写前把这些函数的最基本功能组件拆分到mutations

![image-20210617110613525](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617110613525.png)

- 获取计算属性就调用getters属性

![image-20210617110716240](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617110716240.png)

组件改写为

```
$store.getters.方法名
//注意无()
```

#### 4.组件中的vuex优化

##### 4.1引入映射函数

```
import {mapState,mapGetters,mapActions} from 'vuex'
```

mapgetters() 返回值 为对象 {}

![image-20210617111620666](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210617111620666.png)

```javascript
  methods: {
    ...mapActions(['increment','decrement','incrementIfOdd','incrementAsync'])
  },
```

全部改写为这种字符串形式,调用就不要加$store.state(actions/getters)

- 注意...三点

- 注意 methods中的回调函数名称要和action中一致

- 传送的参数都是数组字符串形式(['str1', 'str2',])

#### 5.vuex模块化

![image-20220207185812713](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207185812713.png)

![image-20220207185700679](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207185700679.png

![image-20220207185709788](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207185709788.png)

book.js写实际的state等属性逻辑,并暴露为一个对象

#### @6.mixin

##### 1.利用mixin优化重复的代码

mapgetters / import 等
