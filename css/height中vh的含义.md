![image-20210702090238946](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210702090238946.png)

1.如图,height中设置100vh和100%相比有什么优势?

![image-20210702090420534](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210702090420534.png)

![image-20210702090705370](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210702090705370.png)

==100vh 不会给你来虚的,当前整个屏幕600px高,你在一个小内容区域设置100vh,效果和100%截然不同,它就算给滚动条也会给您600px!!!==

所以除非需要不要乱用vh!! 

用%就可以继承父盒子对应宽高

配合calc()已经很方便子组件宽高设置了

