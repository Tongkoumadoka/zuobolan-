

### 1.对比![image-20210619170400589](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619170400589.png)

### 2.布局原理

弹性布局,任何类型都能指定为flex布局

float clear vertical-align会失效

![](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619171259335.png)

用父盒子控制里面子盒子

### 3.父盒子常见属性

6个属性

align 排列的意思

justify对齐

![image-20210619171402540](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619171402540.png)

#### 3.1设置子盒子垂直还是水平排列

![image-20210619171456947](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619171456947.png)

默认从左到右  row![image-20210619171516101](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619171516101.png)

#### 3.2 设置子盒子在主轴的排列方式

![image-20210619171847982](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619171847982.png)

子元素display不要写,因为父盒子是flex子元素就变成flex项目,inline类型会拥有宽高,block类型会随主轴方向排列

相对于都变成了block-inline一样

```
 justify-content: flex-start;
```

![image-20210619172416446](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172416446.png)

```
 justify-content: center;
```



![image-20210619172442835](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172442835.png)

```
    justify-content: space-around;
```

![image-20210619172545377](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172545377.png)

![image-20210619172723308](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172723308.png)

左右不需要margin值的平分剩余空间(先两边贴边再分配剩余空间)

```
 justify-content: space-between;
```

![image-20210619172816202](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172816202.png)

![image-20210619172901105](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619172901105.png)

```
 justify-content: space-evenly;
```

对应贴边也有相同边距

![image-20210619173147030](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173147030.png)

#### 3.2 子盒子如果排列大于父盒子宽高会怎么做

传统布局:

![image-20210619173300943](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173300943.png)

![image-20210619173303082](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173303082.png)

flex布局:

![image-20210619173348017](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173348017.png)

![image-20210619173502128](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173502128.png)

他会自动缩小子盒子大小来放到同一行,==默认不换行==!!

装不开就自动缩小子元素宽度放到父盒子里面



但是我想要另起一行显示 8个子盒子:

![image-20210619173628189](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173628189.png)

![image-20210619173706086](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173706086.png)

所以用 flex-wrap 属性设定是否换行



#### 3.4 设置水平垂直居中(侧轴排列设置)

![image-20210619173829796](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173829796.png)

![image-20210619173903677](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619173903677.png)

```
 justify-content: center;
 align-items: center;
```

stretch

当没有设置子盒子高度时他会沿着侧轴拉升到和父盒子一样大小

![image-20210619174338173](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619174338173.png)

#### 3.5 多行的布局

align-item只能布局单行

![image-20210619174519464](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619174519464.png)

![image-20210619174533339](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619174533339.png)

![image-20210619174641097](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619174641097.png)

如何做?

align-content 适用于子项出现换行!!! wrap情况有效

![image-20210619174725296](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619174725296.png)

```
需要有
flex-wrap:wrap
alilgn-content:center
所以盒子整体水平垂直居中
```

不设置外边距就完全贴边

````
around-between 贴边
````



![image-20210619175047280](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175047280.png)

不贴边用 around

![image-20210619175206338](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175206338.png)

#### 3.6复合写法

flex-flow: column wrap

![image-20210619175509749](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175509749.png)

![image-20210619175532936](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175532936.png)

### 4.子项常见属性

4.1 flex分份数

![image-20210619175614355](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175614355.png)

![image-20210619175631701](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175631701.png)

默认0 

注意分配的是==剩余空间==!!!

![image-20210619175715482](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619175715482.png)

左右固定,中间自适应怎么做?

![image-20210619180232333](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619180232333.png)

flex可以做上下平均分份数

![image-20210619180413986](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210619180413986.png)

4.2 align-self 

自己在侧轴的排列方式变化

4.3 利用gap属性,必须在flex父盒子里,非常方便

4.4调整宽度

![image-20210701162117194](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210701162117194.png)

##### 4.5当布局时有padding 就 需要考虑写box-sizing

因为content类型影响子盒子对于width百分比的计算,父盒子的padding减去就可以求

calc(子盒子百分比- 父盒子padding)

百分比宽度是父盒子有多宽,子盒子就原原本本继承它的百分比width,如果子盒子有padding而且为content盒子,那么实际宽度就是原父盒子宽+padding,就一定会溢出或者挤到第二行,所以有padding一定要有 box-sizing border-size

#### 5.两个flex盒子,第一个设置宽度,第二个内部文字超过第一个宽度会怎么样?

第一个不设置宽度会怎么样,怎么设置不换行,

都是需要测试的问题

### 6.flex的圣杯布局

```
flex 0 0 40px  的意思是什么
```

*flex*是*flex*-grow, *flex*-shrink, *flex*-basis三个属性的简写，后两个属性是可选的，

https://www.jianshu.com/p/dabae5e58552

flex-shrink == 0 绝对不缩小,哪怕会溢出

flex-shrink == 0 绝对不放大

flex: n , n auto  放大部分所有根据n分到对应份,缩小同理