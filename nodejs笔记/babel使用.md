## babel基础

### 1.babel是什么

 >babel 是一个 JavaScript **编译器**

### 2.babel的作用

>babel最主要的作用就是把ES6,ES7语法转换成ES5语法,从而在大部分浏览器中能够运行
>
>或者将JSX转换为JS

原因:因为语言的开发更新速度是远远超过业界回馈的,所以最新版本的JS语法很多浏览器还不能支持,现在普及的还是ES5,但是程序员开发已经用上了ES6,所以要有个转换器沟通两者差异,这也是折中的办法,以后ES6普及也会有ES8之类的开发,或许会重新催生新的工具吧

### 3.babel的执行过程

> 原始代码 --> [Babel Plugin] --> 转换后的代码

### 4.组成概念

#### 4.1 plugins (插件)

plugins就是我们加载的有各种转换功能的插件,比如说ES6-->ES5转换就有20+对应的插件,可以按需求引入

- 优点:模块化的插件可以让我们在开发时选择需要的功能插件,而不是一口气加载ES6全家桶,这种方式显然性能提高,扩展性更好

//想象一些HS2中的mod,一次性90多G,对于top程序员,显然自选会更加灵活

例:

```jsx
// index.js
// 箭头函数
[1,2,3].map(n => n + 1);

// 模板字面量
let nick = 'Rain';
let desc = `hello ${nick}`;
```

这里用到了两个ES6才支持的新特性：箭头函数、模版字符串。在只支持 ES5 的浏览器里，这两段代码会报错。

```json
// .babelrc
{
  "plugins": [
    "transform-es2015-arrow-functions",
    "transform-es2015-template-literals"
  ]
}
```

但是安装了对应的依赖之后，上面两段代码就可以正常执行了。

#### 4.2presets 预设

但是有时候插件引入很麻烦,二十多个逐个引入会非常浪费时间,所以很多时候使用preset 提前安装一些精选包或者懒人整合包,能够兼顾绝大部分功能,非常方便,这适合休闲程序员

可以把preset 看成是babel plugins的集合或者整合

```json
// .babelrc
// babel-preset-es2015 就包含了所有跟 ES6 转换有关的插件。
{
  "presets": [ "es2015" ]
}
```

#### 4.3 执行顺序

- 先插件-再预设
- 插件按声明顺序执行
- 预设按声明倒序执行

```json
// .babelrc 执行顺序
{
  "plugins": [ 
    "transform-react-jsx",  //1
    "transform-async-to-generator"  //2
  ],
  "presets": [ 
    "es2015",     //4
    "es2016"     //3
  ]
}
```

![image-20210604090850485](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090850485.png)

