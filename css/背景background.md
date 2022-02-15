## background

### 1.background-size

背景图片的尺寸设置

#### #图片宽度 图片高度

手动放缩,图片会拉伸而且变模糊

#### #只写一个

500px 那么宽度设置到500px ,高度随着圆尺寸的宽高比等比例拉伸到500px对应高度

#### #百分比为单位,相对于父盒子

100% 100% 就是拉伸铺满盒子

#### #cover 完全覆盖div盒子

cover是等比例拉伸到能把整个盒子盖住,一开始拉升会填满宽或者高,但是盒子还有空余,就继续拉升,直到剩下的边恰好填满,超出的部分不显示

![image-20210605231659406](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210605231659406.png)

#### #contain

等比例拉伸,哪一条边铺满div盒子就停止拉升,会有空白区域存在

![image-20210605231909877](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210605231909877.png)

![image-20210605231913837](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210605231913837.png)

![image-20210605231928736](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210605231928736.png)

>手机端背景图片就需要用该属性去调整两倍图,放置拉伸模糊

### 2.背景色的继承性(不可继承)

子盒子不会继承父盒子的背景色!!!!

如果不设置背景色,默认为transparent,透明!! 

实际上父亲的背景色因为子盒子透明从而显示出来,看起来好像继承了,实际上并不是这么一回事

