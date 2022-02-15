> 使用webpack搭建开发环境

> 使用webpack打包优化项目



### 1.webpack是什么

@1.构建工具的意义

原因:前端的项目会用到很多工具,需要写很多文件,除了最基础的html,css,js之外,引入的js库,框架,css的预处理器,less,scss等,es6等高级语法的向下兼容转化,都需要对应工具或者包来处理,以前是一个一个对应小公举解决,但是太繁琐了,于是构建工具的诞生就是把这些繁琐的处理一系列整合到应大工具里面,这急速构建工具



构建工具webpack是一个模块打包器().

它的主要目标是将JavaScript文件打包在一起,打包后的文件用在浏览器中使用

- 转换(transform)

![image-20210715233919092](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715233919092.png)



![image-20210522083811723](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522083811723.png)

可扩展语言的转换 sass,lass 到css

学习自动加载配置,手动是非常繁琐的

![image-20210604091007146](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091007146.png)

### 2.打包原理:

@1.树结构: 在一个入口文件(index.js)中引入所有资源,形成所有依赖关系树状图.

这些资源被称为静态模块

(把a.js b.js img/a.png b.png css/a.css b.css /a.sass b.less 全部引入到index.js中)

(使用import(ES6) 或者commonjs语法引入)

模块:这些可以导入的独立的文件资源,每一个都被称作模块(包括图片,js,css,扩展语言)

@2.chunk:把部分模块打包组成某种功能的集合体的过程(动词)

(比如几个模块打包后组成一级页面)

@3.bundle:各种chunk后的功能组块进行压缩优化代码检测的过程后得到bundel,是真正上线运行的文件,是完成打包后的文件

(绝大部分情况是chunk集合,所以最后优化产生的bundle数量可能不等于chunk数量)

(优化,压缩,翻译)

![image-20210522085151853](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522085151853.png)

### 3.webpack5的安装

默认在ternimal中进行

1.先初始化环境

```
npm init --yes
//生成一个默认的package.json包
```

2.安装webpack和cli脚手架

```
npm i webpack webpack-cli -g 全局安装,重新下载等于版本更新

//npm i webpack webpack-cli -D 添加到开发依赖
//-D 和--save-dev相同含义,开发环境
```

3.创建src文件夹夹

```
注意创建文件夹的方式:
//在源文件右击, new --> directory -->输入新建文件夹名称
会默认在对应目录生成文件夹
//注意一定是 new directory!!!
```

4.webpack 打包模式

```
webpack --mode development
//开发模式有非常详细的注释

webpack --mode production
//生产模式会压缩得很小

```

![image-20210522093749259](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522093749259.png)

5.手动指定打包文件(到指定目录)

```
webpack ./src/index.js ./bulid/build.js --mode development

//将index.js 输出为 build.js
//但是每指定一次就需要重复输入是非常麻烦的,所以我们现在都使用配置文件,在整个项目目录下设置配置JS文件
//它指示webpack 怎么干活
```



### 4.webpack的5个核心概念



![image-20210604091035805](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091035805.png)

```javascript
const path = require('path'); //调用path中的resolve方法
const webpack = require('webpack');
//引用插件
const HtmlWebpackPlugin = require('html-webpack-plugin');


module.exports = {
    //1.entry 入口 指示webpack从哪个文件作为入口起点开始打包,分析内部结构依赖图
    //如果单入口,使用字符串指定一个入口文件,打包一个chunk,输出一个bundle,chunk名称是默认名称

    entry: './src/index.js',
 
    // array :多入口则使用数组的格式
    // entry:["./src/index.js","./src/main.js"],
    // 所有的入口文件形成一个chunk,名称还是默认指定的,输出也是一个bundle,各个入口的树结构可以交叉或者不交叉

    //object :对象格式
    //有几个入口文件就会生成几个chunk,输出几个bundle,chunk名字是下标
    // entry: {
    //     one:'src/index.js',
    //     two:'src/main.js',
    // },


    //2.output 输出 指打包后的资源bundle 输出到哪里,以及如何命名
    output: {
        filename: 'bundle.js', //默认文件名称为 main.js
        path: path.resolve(__dirname, './dist')  //目标输出目录path的绝对路径

    },

    //3.loader 让它能处理非js 资源,比如css,img让他们能识别别的资源,可以理解为翻译过程,因为它本身只能识别.json和js文件

    //4.plugins 插件是对它功能的扩展,包括打包与优化和压缩,到重新定义环境中的变量等
    plugins:[
        //默认会创建一个空的,目的是伪类自动引入打包的资源
        new HtmlWebpackPlugin({
            template: './src/index.html',
            filename: "demo.html",
            minify: {
                //移除html结构中的空格,单实际文字内容不会该
                collapseWhitespace:true,
                //删除注释
                removeComments:true
            }
        }),

    ],

    //5.mode 模式 指示器使用相应模式的配置
    //生成模式production 开发模式 development

    mode:"development"


}
```





#### 4.1 entry

指示webpack以那个未见作为入口起点开始打包,并以此为基准构建内部依赖图

#### 4.2 output

指示打包后的资源bundles输出到哪儿去,已经如何命名

#### 4.3 loader

让webpack能够处理那些非JS文件(类似翻译官一样,因为webpack本身只能理解js)

#### 4.4 plugins

插件可以用于执行范围更加广的任务,插件就相当于对应领域的专家

比如打包优化和压缩等,重新定义环境变量等

注意插件的区别在于还需要多引入这一步

![image-20210715225539956](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715225539956.png)

 安装HTML打包插件

```
npm i html-webpack-plugin -D
```

#### 4.5 mode

分为两种

![image-20210715220655875](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715220655875.png)

### 常见错误

#### 1.npm WARN root@1.0.0 No description和npm WARN root@1.0.0 No repository filed

```html
//1.结论:首先这两个报错的意思是没有描述内容/没有找到项目仓库字段
//但是安装实际是成功的

//2.出现原因 在用npm init -ymore配置时,是不会给 package.jon文件中 "description": "",添加内容的,也不会创立  "repository":

所以会报错

//3.npm WARN root@1.0.0 No description解决方法
"description": "随便写什么内容,只要不为空,实际生产肯定写相关描述",

//4.npm WARN root@1.0.0 No repository filed解决方法

//私人测试学习,添加下列代码到.package.json 文件即可
 "private": true,
 
 //实际开发:直接添加对应repository字段
  "repository": {
        "type": "git",
        "url": "http://baidu.com"
    },
```

```
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
 	entry: './src/index.js',
output: {
        filename: 'bundle.js', 
        path: path.resolve(__dirname, './dist')  
},
plugins:[new HtmlWebpackPlugin()],
mode: 'development'
}
```

### 5.打包HTML资源

![image-20210604090953608](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090953608.png)

```javascript
const {resolve} = require('path'); //调用path中的resolve方法,解构赋值的resolve方法
//也可以直接引用组件,然后调用path.resolve方法,不过还是按需引入更好
const webpack = require('webpack');

//插件 下载==>引入==>plugins中配置
//引入插件
const HtmlWebpackPlugin = require('html-webpack-plugin');


module.exports = {
    //1.entry 入口 指示webpack从哪个文件作为入口起点开始打包,分析内部结构依赖图
    //如果单入口,使用字符串指定一个入口文件,打包一个chunk,输出一个bundle,chunk名称是默认名称

    entry: {
        vendor:['./src/js/jquery' ,'./src/js/common.js'],
        index:"./src/js/index.js",
        cart:"./src/js/cart.js",
        //对应输出三个chunk
    },
    //entry: './src/index.js', // 或者main.js文件

    //array :多入口则使用数组的格式
    //entry:["./src/index.js","./src/main.js"],
    // 所有的入口文件形成一个chunk,名称还是默认指定的,输出也是一个bundle,各个入口的树结构可以交叉或者不交叉

    //object :对象格式
    //有几个入口文件就会生成几个chunk,输出几个bundle,chunk名字是下标
    // entry: {
    //     one:'src/index.js',
    //     two:'src/main.js',
    // },


    //2.output 输出 指打包后的资源bundle 输出到哪里,以及如何命名
    // __dirname是node.js的变量,代表当前文件的目录绝对路径(比如现在是webpack.config.js所在路径后面再加上)
    output: {
        filename: '[name].js', //默认文件名称为 built.js
        path: resolve(__dirname, 'build')  //目标输出目录path的绝对路径

    },

    //3.loader 让它能处理非js 资源,比如css,img让他们能识别别的资源,可以理解为翻译过程,因为它本身只能识别.json和js文件
    module:{
        rule:[
            //详细loader配置
            {
                   //test匹配那些文件/这里匹配的是后缀名以.css结尾的文件/
            test:/\.css$/,
            // use就是对应进行处理的loader
            use:[
            //注意!! use数组中的执行数据是从后到前!!从下到上
             // 创建style标签,将js中的样式插入到行,添加到head生效
            'style-loader',
            // 将css文件变成commonjs模块加载到js中,里面是样式字符串
            'css-loader'
                ] 
             },
             {
            test:/\.less$/,
             use:[
            'style-loader',
            'css-loader',
                 //将less 编译为css文件,注意不能复用!!必须写全
                 //下载less和less-loader
            'less-loader'
                ] 
             },
            //处理图片资源
              {
            test:/\.(jpg|png|gif)$/,
             // 使用一个loader就不需要写数组
             use:'url-loader',
             options:{
                 //图片达标小于8kb,会被base64编码处理,变成字符串方式
                 //但是图片会更大,请求会慢一点
                 //用于减少请求数量(减轻服务器压力)
                 limit:8*1024,
                 //单位是bit 所以*1024
                 esModule:false,
                 name:'[hash:10].[ext]'
                
             },
             // 处理html中img标签引入的图片
                  {
                  test:/\.html$/,
                  use:'html-loader'
              
              }
         	// 打包其他资源
         	{
               exclude:/\.(css|js|html)$/,
               loader:'file-loader'
            }
        ]
    }

    //4.plugins 插件是对它功能的扩展,包括打包与优化和压缩,到重新定义环境中的变量等
    plugins:[
        //功能:默认会创建一个空的html文件,目的是为了自动引入打包的所有资源(js/css)
    	//需求:我们需要有结构的HTML文件,所以要进行下列的配置
        new HtmlWebpackPlugin({
    //复制'./src/index.html'文件,自动引入打包的所有资源
            template: './src/index.html',
            filename: "index.html",
            chunks:['index','vendor'],
            minify: {
                // //移除html结构中的空格,但是实际文字内容不会被修改
                // collapseWhitespace:true,
                // //删除注释
                // removeComments:true
            }
       }),

        new HtmlWebpackPlugin({
            template: './src/cart.html',
            filename: "cart.html",
            chunks:['cart','vendor'],
            //chunk中js文件加载顺序从后到前,vendor --> cart
            //指定一起打包的jschunk包,比如index.html只要index.js和vendor.js
            minify: {
                // //移除html结构中的空格,单实际文字内容不会该
                // collapseWhitespace:true,
                // //删除注释
                // removeComments:true
            }
        }),
    ],

    //5.mode 模式 指示器使用相应模式的配置
    //生成模式production 开发模式 development

    mode:"development",
	//测试阶段用生产模式,开发模式会压缩代码不方便
	devServer:{
		 contentBase: resolve(__dirname,'build'),
 		//启动gzip压缩
		 compress:true,
		 //端口号
 		port:3000
	 }
}
```

![image-20210604091019273](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091019273.png)

### 6.打包css资源

安装npm指令

```
npm i css-loader style-loader -D
```

需要使用loader

两个css-loader

css-loader

style-loader

![image-20210715224416610](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715224416610.png)

![image-20210522201847872](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522201847872.png)

### 7.打包sass less资源

### ![image-20210522203812478](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522203812478.png)

下载对应包

```
npm i less less-loader -D
```

```
npm i node-sass sass-loader -D

//注意sass后缀名是 scss 不是sass文件!

//卸载
npm uninstall sass-loader

//安装最新版本
npm install sass-loader@latest

```

### 8.将css/less文件提取为单独文件

![image-20210522210228559](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522210228559.png)

```javascript
npm i mini-css-extract-plugin

//下载后插件同样需要在package.config.json中引入

const MiniCssExtractPlugin = require("mini-css-extract-plugin");

//引入之后如何使用?
在plugins内new一个对象

new MiniCssExtractPlugin()

//然后将modules中的 style-loader 替换成对应的
MiniCssExtractPlugin.loaderMiniCssExtractPlugin.loader
MiniCssExtractPlugin.loader即可


 {test:/\.css$/, use:[MiniCssExtractPlugin.loader, 'css-loader']},
 //注意 ,MiniCssExtractPlugin.loader不需要''包围!!
```

![image-20210522211527691](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522211527691.png)

```
filename 同样可以设置生成的.css文件名称
```

### 9.处理css兼容性 postcss

下载两个包 

```
npm i postcss-loader postcss-preset-env -D
```



```
需要新建一个配置文件
postcss.config.js

package 中module-rules 中的postcss-loader会自动调用这个配置文件中的配置,然后完成兼容性转换工作

//原因就是直接写package配置里面太麻烦了不美观
```

![image-20210522213327668](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522213327668.png)



![image-20210522213411432](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522213411432.png)

### 10.压缩css(优化)

使用 

```javascript
//对于5.0版本以上用
npm install css-minimizer-webpack-plugin --save-dev


//这些都是4.0才用的,官方不支持了
npm i optimize-css-assets-webpack-plugin -D
```

配置css-minimizer

```javascript
//在package.config.json中引入
const CssMinimizerPlugin = require('css-minimizer-webpack-plugin')

//在modules中引入
 optimization: {
    minimize: true,
    minimizer: [
      // 在 webpack@5 中，你可以使用 `...` 语法来扩展现有的 minimizer（即 `terser-webpack-plugin`），将下一行取消注释
      // `...`,
        
      //此项设置为在生产环境开启css优化
      new CssMinimizerPlugin(),
    ],
  },
```

压缩后的css

![image-20210522225341533](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522225341533.png)

### 11.打包图片资源

url-loader 和file-loader

```
npm i url-loader file-loader -D
base64编码是非常长的字符串,也不会输出图片
```

![image-20210715231154834](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715231154834.png)

base64不会在打包结果中显示

![image-20210715231018169](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715231018169.png)

![image-20210522225430399](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210522225430399.png)      @1. 那么loader如何解析img标签引入的图片?

答案是处理不了,需要使用html-loader来处理HTML中img图片的

实际就是负责引入img,然后让其能把被url-loader处理

html-loader

```
npm i html-loader -D
```

> 将 HTML 导出为字符串。当编译器需要时，将压缩 HTML 字符串

@2但是引入后还是会有问题:因为url-loader默认使用es6模块化解析,而html-loader引入图片使用是commonjs

解决方法:关闭es6,用commonjs解析,统一解析方式

![image-20210715231821136](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715231821136.png)

@3生成的图片字段太长,用哈希值命名,想进行修改

```
option:{
name:'[hash:10].[ext]'
}
```

![image-20210715232135651](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715232135651.png)

12.web![image-20210715231932202](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715231932202.png)pack.config.js核心配置

![image-20210604090338051](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090338051.png)

初始化

![image-20210604090628891](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090628891.png)

![image-20210604091028385](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091028385.png)

### 12.打包对应文件的构建

@1.build 

打包输出的文件存放位置

@2.index.js /main.js 

入口起点文件



#运行指令

![image-20210715221429557](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715221429557.png)

![image-20210715221513140](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715221513140.png)

![image-20210715221641332](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715221641332.png)

打包后的js照样可以引入和运行

基础的webpack功能:

![image-20210715222142567](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715222142567.png)

### 13.webpack的配置文件

webpack.config.js

由于webpack是写配置的代码,它是基于common.js规范而es6的import规范.该文件的作用在于指示运行webpack指令时,应该加载那些配置,从而能够满足哪些额外的功能

```
暴露模块的方法为
module.export = {
	// webpack配置
}
```

### 14.字体文件的打包

在index.js中引入样式文件iconfont.css == > 

![image-20210715232636713](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715232636713.png)

### 15.自动化构建 devServer

![image-20210715233745731](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210715233745731.png)

```javascript
和5个概念平级
devServer:{
 contentBase: resolve(__dirname,'build'),
 //启动gzip压缩
 compress:true,
 //端口号
 port:3000
 }
```

