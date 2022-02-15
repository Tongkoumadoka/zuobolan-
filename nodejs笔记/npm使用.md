## NPM基础

### #1.npm是什么

npm(node package manager)是一个ndoe包管理器,它是使用vue框架之前的基础

>https://www.npmjs.com   (官网地址)

#因为写某些代码时可以看看别人写没有写过,通过npm可以浏览代码仓库,将可能需要的代码拿来使用.

- 有超过100w的软件包支持(数据这么多,所以需要一个管理器来管理)

- node.js默认的,以js编写的软件包管理系统

  ![image-20210604091233401](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091233401.png)

### #2.npm常用命令

![image-20210604090744597](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090744597.png)

#### 1.查看npm包的安装来源

```
//输入后得到对应网址
npm config get registry
//下图为淘宝镜像,如果没有tabao就是官网地址
```

![image-20210521141949055](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521141949055.png)



#### 2.设置npm包安装来源

```npm
//切换阿里路径
npm config set registry https://registry.npm.taobao.org --global
//注意切换后要重启cmd

//或者使用nrm工具切换
npx nrm use tabao

//切换为官方源
npx nrm use npm
```

#### 3.查看npm版本

```
# 查看npm版本
npm -v
```

#### 4.使用npm命令安装模块

```
npm install <module name>
//例如
npm install jquery
```

#### 5.查看已经全局安装的npm包

```
npm list -g

//npm list jquery
```

#### 6.指定切换安装包版本

```
//1.指定版本
npm install jquery@版本号

//2.怎么查看版本:
//打开 https://cdn.baomitu.com/ 
//搜索然后找到对应版本

例
npm install jquery@3.5.1

//3.检查版本是否成功切换为指定版本
//安装完成后输入
npm list jquery 

//4.更新版本
npm update jQuery

//5.卸载对应包 
npm uninstall jQuery
```

![image-20210521150207607](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521150207607.png)

![image-20210521150305537](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521150305537.png)

#### 7.更新npm自身版本

```
npm -g install npm@版本号
```

#### 8.在package文件对应节点写入依赖

##### 8.1运行时依赖

```java
//安装运行时依赖
//效果:在package文件的dependencies 节点写入依赖
-save

npm install -save <模块名>
```

##### 8.2开发时依赖

```java
//安装开发时依赖
//效果:在package文件的devdependencies 节点写入依赖
-save dev 

npm install -save dev <模块名>
```

#### 9.生成配置package.json文件

```
//1.自动配置
npm init --yes

//2.手动
npm init
```



#### 10.少用命令

![image-20210521172548743](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521172548743.png)

#### 10.删除所有依赖包

```
1.安装npm包–rimraf

npm install rimraf -g

2.在cmd指令下，进入所需删除的node_modules文件夹的位置，再输入指令

rimraf node_modules

3.等待删除完成
```



### #3.理解依赖

dependency 依赖 dependencies

- 运行时依赖
- 开发环境依赖

#### 1.运行时依赖

>运行时依赖: 指开发完成的产品(成品),在用户使用完成功能时(进入生产环境)还 需要使用的模块(依赖)
>
>上线运行还得调用的库,比如jQuery

#### 2.开发时依赖

> 开发时依赖: devdependencies  这些模块开发时使用,发布时就不需要了
>
> 类似于脚手架,生产车间的车床.
>
> 比如项目中的gulp,压缩css的模块等

### #4.Package.json文件说明

![image-20210604091059919](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091059919.png)

#### 1."script" 功能

```
npm run 脚本命令
```

![image-20210521153138901](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521153138901.png)

#### 2.依赖环境

![image-20210521170523234](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521170523234.png)

#### 3.^符号

![image-20210521171316016](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521171316016.png)

版本号说明

![image-20210521171835882](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521171835882.png)

#### 4.常见属性

##### 4.1 name 包名

##### 4.2 version 包的版本号

##### 4.3 description 包的描述

##### 4.4 homepage 包的官网(来源) url

##### 4.5 author 包的作者

##### 4.6 dependencies 依赖包列表 

没装会自动装到npm_module目录下

##### 4.7 repository 包代码存储的地方类型

(git,svn,git可在GitHub上)

##### 4.8 main 决定主入口文件 

require('modulename') 会加载该文件,默认值是index.js

##### 4.9 keywords 关键字

  用于搜索引擎

5..babelc

### #5.包的使用

### #6.webpack.config.js文件

![image-20210604091430299](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091430299.png)

关于 h函数
