## vue-cli

### 1.vue-cli的安装

1.1前置操作

- 确认安装node
- 确认安装webpack

```
webpack -v
返回webpack版本和webpack-cli版本

因为4.0以上就要安装cli依赖了
```

![image-20210616144305047](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616144305047.png)

没有安装则

```
全局安装包和依赖
npm install webpack -g
npm install webpack webpack-cli -g
```



1.2全局安装vue-cli

```
npm install vue-cli -g
```

安装完成后记得检查版本号

```
vue -V
```



```cmd

```



### 2.vue-cli的使用

2.1初始化项目

- 首先创建一个英文路径文件夹存放项目

- cd 到该目录
- 初始化:

```
vue init webpack vue-demo 4 项目名称
```

```
? Project name vue-demo # 项目名称，直接回车，按照括号中默认名字（注意这里的名字不能有大写字母，如果有会报错Sorry, name can no longer contain capital letters），阮一峰老师博客为什么文件名要小写 ，可以参考一下。
? Project description A Vue.js project # 项目描述,随便写
? Author # 作者名称
? Vue build standalone # 我选择的运行加编译时
	Runtime + Compiler: recommended for most users
? Install vue-router? Yes # 是否需要 vue-router，路由肯定要的
? Use ESLint to lint your code? Yes # 是否使用 ESLint 作为代码规范.
? Pick an ESLint preset Standard # 一样的ESlint 相关
? Set up unit tests Yes # 是否安装单元测试
? Pick a test runner 按需选择 # 测试模块
? Setup e2e tests with Nightwatch? 安装选择 # e2e 测试
? Should we run `npm install` for you after the project has been created? (recommended) npm # 包管理器，我选的NPM
```

此时会下载模板,然后出现选项



- 之后进入项目目录

```
cd vue-demo 项目名称
```

- 安装项目的依赖包,也就是package.json里的包，用cnpm要快些

```
npm install
```

- 在开发模式运行

```
npm run dev
```

- 浏览器打开页面

```
http://localhost:8080
可以修改端口
```



### 3.vue-cli注意事项

#### 3.1一些常用的指令

###### 1.查看vue-cli版本

```
vue --version
vue -V
```

###### 2.进入vue-cli项目可视化管理工具

```
vue ui
```

###### 3.检查可使用的vue命令

```
vue
```

![image-20210616151635580](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616151635580.png)

#### 3.2需要注意的细节

#vue 项目可视化 是 vue/cli3.0 版本后更新

#vue-cli是脚手架,它的版本在package.json中找不到(包)

#vue.js支持中文路径,但是最好不要这么用

#### 3.3出现的错误

1.vue init webpack vue-demo 初始化报错

报错:

![image-20210616144926156](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616144926156.png)

解决方法:

```
npm i -g @vue/cli-init
```

再重新初始化

### 4.vue ui可视化界面

### 5.vue中package.jsonp配置文件优化

##### @1.cmd 输入 vue-cli -serve 时自动打开浏览器

```
cmd 输入 vue-cli -serve 时自动打开浏览器
```

```json
  "scripts": {
    "serve": "vue-cli-service serve --open",
    "build": "vue-cli-service build",
    "lint": "vue-cli-service lint"
  },

//加open
```

##### @2.eslint校验功能关闭

```
在全局新建vue.config.js文件
```

```
modules.exports = {
  // 关闭eslints
  lintOnSave:false
}
```

##### @3.给src文件配置别名@,方便路径插找

```
目录中存在jsconfig.json文件表示该目录是JavaScript项目的根目录。jsconfig.json文件指定根文件和JavaScript语言服务提供的功能选项。
```

```json
{
  "compilerOptions": {
    "baseUrl": "./",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "exclude": ["node_modules", "dist"]
}

// exclude 是不能使用@的文件夹
```

## vue-cli-3

### 1.配置vue.config.js

#### @1.配置不同场景下的环境变量方法

[博客](https://blog.csdn.net/w405722907/article/details/94720868)

1.创建方法

```
根目录创建
.env.development文件

VUE_APP_RES_URL = http//127.0.0.1:8081
// 设置静态资源的资源访问路径 
```

```
环境变量必须以 VUE_APP_ 开头 
```

2.使用该变量

```
${process.env.VUE_APP_RES_URL}  调用该环境变量
```

@2..env .env.production .env.development

![image-20220210200319483](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220210200319483.png)
