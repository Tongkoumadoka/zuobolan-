> 基本linux命令

1）、cd : 改变目录。

2）、cd . . 回退到上一个目录，直接cd进入默认目录

3）、pwd : 显示当前所在的目录路径。

4）、ls(ll):  都是列出当前目录中的所有文件，只不过ll(两个ll)列出的内容更为详细。

5）、touch : 新建一个文件 如 touch index.js 就会在当前目录下新建一个index.js文件。

6）、rm:  删除一个文件, rm index.js 就会把index.js文件删除。

7）、mkdir:  新建一个目录,就是新建一个文件夹。

8）、rm -r :  删除一个文件夹, rm -r src 删除src目录

```
rm -rf / 切勿在Linux中尝试！删除电脑中全部文件！
```

9）、mv 移动文件, mv index.html src index.html 是我们要移动的文件, src 是目标文件夹,当然, 这样写,必须保证文件和目标文件夹在同一目录下。

10）、reset 重新初始化终端/清屏。

11）、clear 清屏。

12）、history 查看命令历史。

13）、help 帮助。

14）、exit 退出。

15）、#表示注释

> git配置

1.查看配置列表

```
git config -l
```

2.查看本地配置

````
//1.查看本地全局配置了什么,实际就是user自行配置了什么
//图中的用户名和密码告诉服务器来访的是谁
git config --global --list

2.查看系统配置
git config --system --list
````

![image-20210528145532176](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528145532176.png)

3.git配置的config的存储位置

1）、Git\etc\gitconfig  ：Git 安装目录下的 gitconfig   --system 系统级

2）、C:\Users\Administrator\ .gitconfig   只适用于当前登录用户的配置  --global 全局

```
用户配置
```

![image-20210528150404470](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528150404470.png)

```
系统配置
```

![image-20210528150424973](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528150424973.png)

4.设置自己的用户名和密码

必须学会,要不无法提交自己的项目

```javascript
git config --global user.name "kuangshen"  #名称
git config --global user.email 24736743@qq.com   #邮箱
```

![image-20210528151300498](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528151300498.png)

不报错就设置正确,然后在用户的config里面检查,存在就表示设置没有问题

3.

注意:

- 所有的配置文件,都保存在本地,可以直接修改config文件来更改配置
- git的环境变量是为了命令能全局使用,它在安装的时候就已经自动配置好了

> git的基本理论(核心)

1.git的工作区域

git在 **本地** 有三个工作区域 **远程**有git仓库

- 工作目录
- 暂存区
- 资源目录
- 远程





> git项目搭建

两种方式

1.本地仓库搭建

```
git init 
//在对应文件目录中输入
```

![image-20210528152547830](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528152547830.png)

![image-20210528153037728](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528153037728.png)

2.远程仓库

``` 
git clone url
//注意url就是gitee (国内) 或者 GitHub (国外)项目的分享链接,复制之后粘贴过来即可
//然后就会下载远程仓库的代码和文件
```

![image-20210528152758675](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528152758675.png)



> GIT文件操作

1.GIT文件的四种状态

- **Untracked:**
- **Unmodify:**
- **Modified:**
- **Staged:**

2.查看文件状态





3.实际流程

1.先在工作目录下创建需要的代码文件

```
//工作目录确定:看看有没有.git 隐藏文件夹
```

![image-20210528160924239](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528160924239.png)

2.使用add命令添加到暂存区

```
git add . 
//添加全部(all)文件到暂存区,也就是目录下所有文件

git status 
//检测提交文件状态
```

3.使用commit命令提交文件到本地仓库

```
git commit -m "这里输入备注信息,如:添加了hello.txt文件"

git status 
//再次检验
```

4.如果有不需要提交的文件(对应方法)

在主目录创建 ==.gitnore==文件

```
//比如.idea 目录下文件

```

有些时候我们不想把某些文件纳入版本控制中，比如数据库文件，临时文件，设计文件等

在主目录下建立".gitignore"文件，此文件有如下规则：

1. 忽略文件中的空行或以井号（#）开始的行将会被忽略。
2. 可以使用Linux通配符。例如：星号（*）代表任意多个字符，问号（？）代表一个字符，方括号（[abc]）代表可选字符范围，大括号（{string1,string2,...}）代表可选的字符串等。
3. 如果名称的最前面有一个感叹号（!），表示例外规则，将不被忽略。
4. 如果名称的最前面是一个路径分隔符（/），表示要忽略的文件在此目录下，而子目录中的文件不忽略。
5. 如果名称的最后面是一个路径分隔符（/），表示要忽略的是此目录下该名称的子目录，而非文件（默认文件或目录都忽略）。

 >码云的注册和使用

码云的三种使用方法

- 使用gitbub,需要vpn
- 使用gitee,国内
- 公司搭建自己的gitlab



设置本机的绑定SSH公钥,实现免密码登录 (免密码登录,重要)

```
//因为码云是远程仓库,工作是本地操作,所以每次都要登录很麻烦

方法:
1.进入 C:\Users\Administrator\.ssh 目录
2.生成公钥
ssh-keygen -t rsa -C "xxxxx@xxxxx.com"  

3.获取public key
cat ~/.ssh/id_rsa.pub

4.将对应的公钥复制,然后在码云ssr公钥中设置添加

5.ssh -T git@gitee.com
首次使用需要确认并添加主机到本机SSH可信列表

6.完成操作开始clone
git clone 复制的码云仓库提供的http地址
```



### 使用idea集成git

#### 1.打开idea,创建对应项目并绑定

把远程的.git项目直接拷贝过来

![image-20210528212731977](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210528212731977.png)

#### 2.控制台三次输入

```
git add .
git commit -m ""
git push //提交到远程
```

#### 3.配置.gitignore

```
//1.用来忽略某些文件不提交上去
```



### 常见问题

#### 1.本地没有找到.ssh文件夹

解决方法如下:

```
//1.打开GIT Bash
```

```
//2.输入如下
ssh-keygen -t rsa -C "xxxxx@xxxxx.com"   

//注意只要满足邮箱格式就行,推荐常用方便记忆
```

```
3.连续三次回车
其中的第一次回车会自动生成.ssh文件夹

所在位置为c盘用户目录内
```

![SSH生成](https://images.gitee.com/uploads/images/2018/0814/170141_5aa5bc98_551147.png)

#### 2.clone push报权限错

```
错误样式:
The authenticity of host 'gitee.com (xxx.xxx.xxx.xxx)' can't be established.
ECDSA key fingerprint is SHA256:xxxxxxxxxxxxxxxxxxxxxxxx.
```

错误原因:

```
在.ssr文件夹中缺少一个known_hosts文件,需要生成
所以一共要有3个文件
```

解决方法如下:

```
//1.输入
cat ~/.ssh/id_rsa.pub
//2.再输入yes

这时会自动生成对应known_hosts文件,并且告诉你成功授权
//3.完成后即可重新clone
```

![SSH添加提示](https://images.gitee.com/uploads/images/2018/0814/170837_4c5ef029_551147.png)

#### 3.怎么查看提交版本idea

在最下面的log选项中查看commit 的"message"

4.

### git的概念

#### 1.工作区/暂存区/版本库

![image-20220206215756021](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206215756021.png)

- **工作区：**就是你在电脑里能看到的目录。

- **暂存区：**英文叫 stage 或 index。
- 一般存放在 **.git** 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。

- **版本库：**工作区有一个隐藏目录 **.git**，这个不算工作区，而是 Git 的版本库。

![image-20220206215857091](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206215857091.png)

![image-20220206220507446](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206220507446.png)

#### 2.创建一个仓库

![image-20220206221615014](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206221615014.png)

```
在当前目录 git bash 启动后

git init 初始化一个仓库 ,出现.git文件夹
```



#### 3.拷贝远程仓库到本地

```
比如在gitbub发现一个项目不错,想本地运行
git clone + 复制的地址即可

会在执行命令的本地目录创建对应项目文件夹
```

![image-20220206220831725](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206220831725.png)

#### 4.图解

![image-20220206221624370](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206221624370.png)

#### 5.提交修改

##### @1.提交到暂存区 add

```
git add .
```

##### @2.提交到本地仓库 -- 新版本 

```
git commit -m "这次修改的备注"  //注意备注一定要加!!!,否则报错
```



![image-20220206221703176](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220206221703176.png)

#### 6.配置全局用户名/邮箱

```
git config --global user.name “zuobolan”
git config --global user.email “Madokasukii@163.com”
```

```
git config --list
查看全局的配置项
```

#### 7.链接到远程仓库

```
git commit 所有内容后就要将本地仓库内容提交到远程仓库

远程仓库创建后关联 仓库地址
git remote add origin 
ssh码

git branch -M master
这是给主分支的命名,master是自命名,叫啥都行


// origin是远程仓库默认名字,这里的意思就是把文件从master主分支push到本地仓库
git push -u origin master
```

#### 8.验证是否成功

```
ssh -T git@github.com
```

![image-20220207214717271](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220207214717271.png)

#### 9.查看全局配置

```
git config --list
```

