#### 1.用循环给子组件分别进行修改(背景色.边框/阴影/字体大小等)@each



(背景色,边框等很多东西都可以)

在业务场景中常见给多个相同子组件添加不同的颜色或者背景图片等要求

![image-20210715161556297](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715161556297.png)

写法

```scss

// 定义变量数组，数组元素用逗号隔开 
$liColor:#f5ad1b,#5f89ce,#94bf45,#da8ec5,#78bfc2,#bec278;
// 注意结尾要分号;
 
// 开始 @each 循环遍历数组

// $c 作为循环变量，代表了数组的元素，不是索引~！！！
@each $c in $liColor{
     $i:index($liColor,$c);       // 获取 $c 在数组中的索引，并赋值给 $i 赋值用冒号，不是等号~！ $1变量就是索引值
     &:nth-child( #{$i} ){      // 经典的地方来了，SCSS 循环是从 1 开始，不是 0 哦~
       background: $c;           // 背景色
       &:hover{
         background: lighten($c,10%);    // hover 后的颜色
       }
     }
```

```html
   <view
            class="select-card"
            v-for="(item, index) in cardList"
            :key="index"
          >
            <view class="card">
              <image :src="item.imgSrc" mode="" />
            </view>
            <text>{{ item.title }}</text>
          </view>
// 注意,如果v-for循环的是一个小组件,里面s实际上要赋值的是组件中的某个盒子或者图片,就必须在赋值选择器中再进行选择!!!
  &:nth-child( #{$i} ) 只能拿到循环后整个大盒子的子元素,而子元素只有view 和 image
所以必须再在其中基础上选择.card盒子 :&:nth-child( #{$i} ) .card 才能给所有对应.card盒子修改背景色
```

#### 2.vue安装sass / node-sass /sass-loader 中和node的版本冲突问题

node-sass 是什么?

node中运行sass需要对应依赖,node-sass就是依赖包,它的版本号和node版本有对应关系,如果任意安装就会有兼容性问题

![image-20220206194458176](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206194458176.png)

sass-loader是什么?

sass-loader类似一个翻译工具,因为vue中默认使用打包工具为webpack,但是webpack只识别js,css,html等最基础的原生文件,所以基于css的scss/sass都需要一个"翻译"来使其能够被理解好加载. 

sass-loader就可以使scss转换为css文件,而之后还有css-loader对齐进一步打包

sass-loader 和node-sass 有版本对应问题,也必须考虑兼容性



安装sass,首先判断当前vue-cli支持的node-sass sass-loader版本,他们保证兼容性后,再对应选择满足版本的node,用nvm安装更换node版本即可

#### 3.手写一个sass-loader

#### 4.在一个组件中引入sass文件

```scss
@import "urt/xxx.sass"
    
@import解决了这个问题，它能将多个scss合并为一个。    
```

注意引入外部css文件不要使用css3的

```scss
@import url("style/index.css");

//不推荐css3中的@import可能会造成延迟加载，有的地方没有样式。
```

#### 5.设置全局样式文件 global.scss

```
常见的布局补充


```

#### 6.设置全局默认配置样式文件 reset.scss

```
主要用来解决个浏览器不同的标签默认样式问题
先同一清除,再后续使用
```

#### 7.动态切换全局样式的思路

```
动态删除混入添加dom的css文件
```

```js
// 全局样式切换
export function addCss(href) {
  // 创建一个link标签
  const link = document.createElement('link')
  // 进行属性设置
  link.setAttribute('ref', 'stylesheet')
  link.setAttribute('type', 'text/css')
  link.setAttribute('href', href)
  // 将link标签添加到head标签最后
  document.getElementsByTagName('head')[0].appendChild(link)
}

```

