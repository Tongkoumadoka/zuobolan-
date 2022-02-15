```
这个小册子旨在快速查阅Nginx的指令

nginx是一个高性能的HTTP和反向代理服务器，也是一个通用的TCP/UDP代理服务器
```

### 1基本 流程

#### @1.[下载地址](http://nginx.org/en/download.html)

#### @2.基本认识

![img](https://pic3.zhimg.com/80/v2-36f9e8d35a7cd8403126783a177bb402_720w.jpg)

**正向代理**对我们是透明的，对服务端是非透明的，即服务端并不知道自己收到的是来自代理的访问还是来自真实客户端的访问。

也就是正向代理的请求ip地址是代理服务器的ip地址,通过这可以掩盖实际访问主机ip地址

这也是fq的原理



**反向代理**对服务端是透明的，对我们是非透明的，即我们并不知道自己访问的是代理服务器，而服务器知道反向代理在为他服务。

主要进行负载均衡,内容转发等

### 2.指令 速查

配置ngnix相关

#### @1.验证配置是否正确

```
nginx -t
```

配置完成后测试用

#### @2.查看Nginx的版本号

```
nginx -V
```

#### @3.启动Nginx

```
start nginx
// 可以全局使用
```

####  @4.快速停止或关闭Nginx

```
nginx -s stop
```

#### @5. 正常停止或关闭Nginx 

关闭cmd窗口是不能结束nginx进程

```
nginx -s quit
```

#### @6. 配置文件修改重装载命令

```
nginx -s reload
修改完ngnix文件后执行,等于刷新了配置
```

#### @7.查看nginx执行情况

```
tasklist /fi "imagename eq nginx.exe"

前两个nginx的控制服务，后面两个是此次启用的服务
```

![image-20220207200527928](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207200527928.png)

#### @8.访问服务器地址

```
http://127.0.0.1/  
//本机地址

或者8080端口
```

### 3.配置文件的基本结构

![img](https://pic3.zhimg.com/80/v2-de95e768f514f40b07484d7da27872ae_720w.jpg)

![image-20220207202837305](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207202837305.png)

```nginx

   server{                                                     
     listen 8081;                                           
     server_name source;                                  
     root  C:\Users\inui\Desktop\vue-ebook-tem\source;                          
     autoindex on;                                          
     location / {     
                                             
        add_header Access-Control-Allow-Origin *;              
        # 支持跨域
     }                                                      
     add_header Cache-Control "no-cache,must-revalidate";   
      # 每一次都需要重新验证,不进行缓存,文件经常变动就加
}        
```





### 4.各种踩坑

```
\resource中的\r会被识别为空格！
所以配置路径不能这么写
```

