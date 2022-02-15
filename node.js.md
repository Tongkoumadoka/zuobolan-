node.js

### 1.打开命令行窗口

命令行窗口,cmd窗口,终端terminal,运行窗口

---

方法1:

开始菜单-运行-cmd-回车

![image-20210515175007804](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515175007804.png)

最初没有Windows系统时,DOS系统来操作

默认显示的是当前所在目录

---

方法2:

在文件夹资源管理器-地址栏 加上cmd

![image-20210516171406873](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210516171406873.png)

![image-20210515232215743](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515232215743.png)

---

方法3:

以管理员身份运行,以给予最高权限

![image-20210515232356085](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515232356085.png)



#### 1.1cmd常用指令

```
#dir+回车
作用:列出当前目录下所有的文件
```

![image-20210515175714903](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515175714903.png)

------



```
#cd 目的地址(目录名) 
cd Desktop+回车 进入到了桌面

#cd .. +回车 返回上一级
作用:进入对应文件

注意: cd = change directory
```

![image-20210515175524496](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515175524496.png)

------



```
#md 文件(目录)名
md hello
作用:在当前目录下新建一个文件夹

#cd>文件名
作用:创建一个文件
#del 文件名
作用:删除一个文件
```

![image-20210515175942373](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515175942373.png)

```
#rd 目录名
rd hello
作用:在当前目录下删除对应文件夹
```

------

```
#文件名称.扩展名+回车

hello.txt +回车

作用:打开当前目录中的某个文件
注意:必须要在目录内有这个文件,否则报错
```

![image-20210515180607936](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515180607936.png)

![image-20210515180755011](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515180755011.png)

------

```
#e: +回车
作用:盘符切换,直接进入对应盘,d盘就是d:
```

![image-20210515182356932](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515182356932.png)

------

```
#node 文件+回车
node执行js文件
```

![image-20210515192926626](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515192926626.png)

------

```
#cls + 回车
清空控制台屏幕
```

---

```
#ipconfig + 回车
查看ip

#ping 命令
ping + ip地址

calc/mspaint/notepad 
打开应用
```

---







#### 1.2环境变量

##### 1.2.1如何打开Windows环境变量? 

计算机 -属性-高级系统设置-高级-环境变量

![image-20210515181042257](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515181042257.png)

1.2.2环境变量-系统变量分析

- path:保存了可以直接访问的文件路径

我们可以把其他文件的路径编辑到其中,则无论cmd在哪个目录地址,也可以直接通过 **文件名称.扩展名** 的方法调用该文件

- 原理 

  当我们在命令行窗口打开一个文件或者调用一个程序时

系统首先在当前目录寻找文件程序,如果找到则直接打开文件

没有则会依次在环境变量path中路径中寻找,直到找到为止

如果都没有则报错

- 总结
  1. 到公司工作第一件事是搭建环境变量,所以需要改
  2. 多个路径直接使用: (英文分号间隔)
  3. 修改之后需要重启命令行窗口才生效

2.进程和线程

2.1进程

​	进程负责为程序的运行提供一个必备的环境

​	(代码的运行需要载体,进程就提供了这个环境,好比工厂的某个生产车间)

2.2线程

​	他是计算机中最小的计算单元,线程负责执行进程中的程序

​	(类似工厂工作的工人)

2.3单线程和多线程

单线程:一个人干活(js   )

多线程:多个人干一个活



3.node(节点)

3.1node.js是什么?

- 他是一个能够在服务器端运行js的跨平台 **js运行环境**(之前都在浏览器(用户客户端)运行,而现在可以在后端运行了)
- 源码开放
- 使用谷歌V8引擎,特点:事件驱动/非阻塞/异步i/o模型
- node处理请求是单线程,后台有个i/o线程池(所以会多服务器来解决问题)

​	

------

小知识:

1.什么是高并发问题?

一个网站同时有很多人访问,如何保证其性能的稳定和高效



2.什么是i/o?

input/output 服务器对数据库的数据读写

![image-20210515191015420](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210515191015420.png)

磁盘速度的限制,有读写速度极限,是所有项目的瓶颈(硬件的短板                         )

3.阻塞的产生原因?

由于i/o速度的限制,当访问请求量超过某一额度(高性能并发),由于等待数据的传递,这就占据并且浪费了很多空间和时间



4.node的版本,奇数开发版,偶数稳定版

------

3.2node的用途

web服务器API,rest

后端web服务