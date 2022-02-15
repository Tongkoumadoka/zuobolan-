## layout

1.设置栅格间横向距离间隔![image-20210625161806532](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625161806532.png)

因为el-row是一个容器,装载el-col部件,如果不设置gutter属性,那么就是一个整体,设置gutter后,有几个col就分块成几个布局

![image-20210625162101972](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625162101972.png)

2.el-col 的响应式布局

![image-20210625162655622](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625162655622.png)

3. 布局把整个盒子宽度分为24份,span设置的值就是占据的份数

   所以在响应式布局中,由于窗口宽度px不断变小,就会把分开的卡片挤下去,原本12/12平分长宽度的的两张卡片,要占据整行短宽度,于是变成24 24

![image-20210625164059321](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625164059321.png)

4.用offset 设置
