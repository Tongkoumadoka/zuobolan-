### 一.NPM包管理器

#### 1.全局安装和本地安装

g ==> global

```javascript
npm install express          # 本地安装
npm install express -g       # 全局安装
```

区别为

##### @1.本地安装

- \1. 将安装包放在 ./node_modules 下（运行 npm 命令时所在的目录），如果没有 node_modules 目录，会在当前执行 npm 命令的目录下生成 node_modules 目录。	

  也就是根据cmd 执行npm install命令所在目录决定

- \2. 可以通过 require() 来引入本地安装的包。

##### @2.全局安装

- \1. 将安装包放在 /usr/local 下或者安装了 node 的安装目录。
- \2. 可以直接在命令行里使用。

#### 2.查看全局安装的模块目录

```
npm list -g
```

#### 3.卸载模块

```
npm uninstall express  后面加模块名

卸载完成后查看是否卸载完毕
npm ls
```

##### @1.删除所有依赖包

```
npm install rimraf -g
// 先全局安装该插件 已安装

命令卸载
rimraf node_modules
```





#### 4.更新/搜索模块

```
npm update/search 模块名称
```

#### 5.创建模块

##### @1.初始化package.json文件

```
npm init -y 是最快的安装
不需要打回车
```

![image-20220212180208087](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220212180208087.png)

```
npm init 
之后根据顺序依次回车进行初始化package.json文件

如果终止初始化就使用ctrl c


选项的一些信息
name: (node_modules) runoob                   # 模块名
version: (1.0.0) 
description: Node.js 测试模块(www.runoob.com)  # 描述
entry point: (index.js) 
test command: make test
git repository: https://github.com/runoob/runoob.git  # Github 地址
keywords: 
author: 
license: (ISC) 
About to write to ……/node_modules/package.json:      # 生成地址
```

##### @2.在npm资源库中注册

```
npm adduser


Username: mcmohd
Password:
Email: (this IS public) mcmohd@gmail.com
```

##### @3.发布模块

```
npm publish
```

#### 6.使用淘宝镜像安装npm包

```
npm install -g cnpm --registry=https://registry.npmmirror.com
设置镜像源

之后cnpm install [name] 安装模块

```

#### 7.清除本地安装的缓存,如果npm包安装过程中反复报错

```
npm cache clean
npm install
```

#### 8.简写方式

```
@1.install == > i
instance:
npm i sass
@2.-s ==> --save
```

##### @1.写入不同的依赖

devDependencies  里面的插件只用于开发环境，不用于生产环境，而 dependencies  是需要发布到生产环境的。

![image-20220130174535851](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220130174535851.png)

```
npm i module_name  -S  = >  npm install module_name --save    写入到 dependencies 对象

npm i module_name  -D  => npm install module_name --save-dev   写入到 devDependencies 对象 开发时所需要的依赖

npm i module_name  -g  全局安装
```

##### @2.结论 -D

```
一般安装到开发环境
npm i 包 -D 注意必须大写!!!,小写会无视-d直接安装到生产环境中
```

### 二.nrm包源管理器

#### 1.全局安装

````
npm i nrm -g
````

#### 2.常用命令

##### @.1查看安装源

```
nrm ls
```

![image-20220214083741917](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220214083741917.png)

##### @2.帮助

```
nrm -h
```

![image-20220214083924515](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220214083924515.png)

##### @3.查看版本号

```
nrm -V
```

![image-20220214083913043](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220214083913043.png)



##### @4.切换下载的源

```
nrm use 源名称
```

##### @5.添加自定义的源

```
nrm add <registry> <url>
```

![image-20220214084505423](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220214084505423.png)

#### 3.作用

[nrm](https://links.jianshu.com/go?to=https%3A%2F%2Fgithub.com%2FPana%2Fnrm)（NPM registry manager）是 NPM 的镜像源管理工具，使用它可以快速切换 `npm` 命令镜像源。

### 三.nvm node版本管理器

#### 2.常用命令

```
nvm list available
```

### 四.nodemon刷新

```
npm i nodenon -D
```



### 五.接口调试postman

### 六.express框架

```

```

