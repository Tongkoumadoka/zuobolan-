## idea 中vue环境的搭建

### 一.VUE的安装

#### 1.如何查找node.js的位置?

```
cmd 中输入
where node enter
```

#### 2.环境变量的搭建

安装后 node js环境变量已经自动写入

![image-20210520222601304](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520222601304.png)

#### 3.检测node .js 环境是否ok 

```
cmd 输入
node -v enter // 查看是否能正确打印出版本号

npm -v enter
```

如图:

![image-20210520222847813](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520222847813.png)

#### 4.安装npm 淘宝镜像

```
# -g 就是全局安装
npm install cnpm -g
//这就是在npm中找到npm再下载

# 查看npm版本
npm -v
```



#### 5.安装 vue-cli

```
cnpm install vue-cli -g 

//#测试是否安装成功
//在C:\Users\inui\AppData\Roaming\npm 查看是否有安装

//#检测模板目录
vue -list 
```

![image-20210520230852441](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520230852441.png)



#### 6.cmd创建第一个vue项目

```
//在cmd中输入
vue init webpack myvue(vue文件名)

//出现下面的选项控制
```

![image-20210520231739933](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520231739933.png)

![image-20210520231820461](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520231820461.png)



#### 7.初始化并运行

```
//cmd 中
cd myvue
//进入项目目录

npm install
//安装依赖环境

npm run dev
//webpack打包

查看node版本
//node -v
```

![image-20210520235800084](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520235800084.png)

#idea打开,file-open-对应文件目录

![image-20210520233527807](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520233527807.png)

![image-20210520233719278](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520233719278.png)

#cmd 输入npm run dev命令

显示打包完成,输入url可以在浏览器访问项目初始页面

![image-20210520234058175](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520234058175.png)

![image-20210520234100600](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520234100600.png)

#### 8.idea terminal的检测与使用

idea内terminal有时候无法识别命令,这是因为没有使用管理员权限打开cmd

![image-20210520235229529](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520235229529.png)

#解决方法:给予idea权限

![image-20210520235243372](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210520235243372.png)

### 二.vue-cli配置项目文件介绍

#界面总览

![image-20210521001002655](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521001002655.png)

#### 1.build文件夹

#webpack.....js文件(3)

![image-20210521001142382](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521001142382.png)

#### 2.package.json文件

当前该应用的整体描述文件包

![image-20210521001023900](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521001023900.png)

#### 3.config文件夹

##### 3.1 index.js文件

![image-20210521001106692](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210521001106692.png)

![image-20210616152442487](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616152442487.png)

是否自动打开页面 初始化时

#### 4.src 文件夹

#### 5.static文件夹

5.1.gitkeep文件

默认为空

为什么需要这个文件?

因为如果static文件夹什么也没有,就会被git自动忽略

但是我们又不希望被忽略,所以创建一个空文件

#### 6.node_modules 文件夹

#### 7. .babelrc 文件

babel的控制文件

作用:自动将 es6语法转换为 es5 更多细节看babel的笔记

```
rc : 意思是 runtime control 运行控制
```

#### 8.eslintignore 文件

因为eslint会进行语法检查,所以如果有一些不想检查的就要写到这里面

#### 9.gitignore文件

```
就是git 码云自动忽略的上传文件
```

#### 10.main.js文件

这个文件中的所有内容(js),都会被打包生成一个文件app.js文件,它总览全局,所有组件都经他之手传递到index.HTML页面

index.html中的 vue实例都在main.js中定义并初始化

inport 可以看成 src 引入的高级版本(es6)

![image-20210616154452150](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616154452150.png)

注意:

1.为什么要写template?
![image-20210616160335537](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616160335537.png)

vue在挂载前会判断vue实例中有没有 template属性,有的话,就对他进行编译,然后直接在挂载的HTML中进行渲染

![image-20210616164051324](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210616164051324.png)

作用:

- 初始化vue 实例 new vue
- 引入vue.js,vue.router,和其他子组件
- 

#### 11.components 文件夹

- 这个文件夹用来存放子组件

```
export default {
//向外默认暴露一个配置对象
}
```

- vue文件的模板

```
```

#### 12.App.vue

主组件文件,它引入所有的子组件

```vue
<script>
import helloworld from './components/helloworld.vue'

export default {
  name: 'App'
}
</script>
```



### 三.安装出现的常见问题

#### 1.deprecated request@2.88.2

```cmd
//安装npm install cnpm -g时出现
//返回一个已经废弃的支持,安装失败

npm WARN deprecated request@2.88.2: request has been deprecated, see https://github.com/request/request/issues/3142
npm WARN deprecated har-validator@5.1.5: this library is no longer supported

//deprecated  :已经被废弃的
//dependency :依赖(环境)
```

原因是资源的问题，电脑里没有配置淘宝镜像，需要配置淘宝镜像，配置方法

```java
npm config set registry https://registry.npm.taobao.org

配置完成后检验是否成功
npm config get registry
    
//成功会显示淘宝镜像网站
//重新安装项目依赖
```

#### 2.npm WARN ajv-keywords@3.2.0 requires a peer of ajv@^6.0.0 but none is installed. You must install peer dependencies yourself.

```
//#产生原因
就是告诉你没有装ajv@6.0.0 
直接手动装就行

npm install ajv@6.0.0  
//手动安装ajv@6.0.0
```

#### 3.npm WARN optional SKIPPING OPTIONAL DEPENDENCY: 

```
//#产生原因 
//fsevent是mac系统的，在win或者Linux下使用了，所以会有警告，忽略即可
```

#### 4.babel -v  error: unknown option `-v'

```
//#产生原因
版本号有时候要用大写V
输入
babel-V
```

