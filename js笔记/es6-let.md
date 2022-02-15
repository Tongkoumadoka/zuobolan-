var i  = 0 在循环体系中的后果

![image-20210624151128642](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210624151128642.png)

因为执行完成后,function()内没有 i 变量,所以根据作用域链,他会查找上一级内是否有 i . 

而var i = 0 是全局定义,i被设置为Windows 对象的属性,所以最后调用作用域Windows.i 的值,是 items.length -1

解决方法为 把var换为let,也就是循环过程中,每一次let定义的i都只能在该次循环块域生效,从而解决问题

![image-20210624151922362](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210624151922362.png)