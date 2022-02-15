

## echarts

- 免费开源,商用可

1.引入

```html
 <!-- 引入 echarts.js -->
    <script src="https://cdn.staticfile.org/echarts/4.3.0/echarts.min.js"></script>
```









### 1.怎么写一个echarts?

@1.option 对象是整个表格的数据抽象

首先,一个echart整体所有的结构数据全部被放置在

option变量中,option是一个变量

![image-20210706160754673](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706160754673.png)

@2.option下的其他对象属性描述表格的其余结构,他们被称为组件

- x轴
- y轴
- 网格

![image-20210706160937695](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706160937695.png)

@3.书写顺序

x轴,y轴,网格,系列

x轴考虑 type,data,axistick,axislabel,axisline



@4.注意用 || 赋值时

```
   this.option.series[0].data = [
          {
            value: res.data[0].nv30 || 0,
            //短路运算,左边true就直接返回左边值,false计算右边返回右边值
          },
```



### 2.组件一览

#### 1.网格 grid

![image-20210706161554740](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706161554740.png)

#### 2.x轴 xAxis 

直角坐标系 grid 中的 x 轴，一般情况下单个 grid 组件最多只能放上下两个 x 轴，多于两个 x 轴需要通过配置 [offset](https://echarts.apache.org/zh/option.html#xAxis.offset) 属性防止同个位置多个 x 轴的重叠。

- 单个组件最多两个x轴
- 多的用offset设置面得重叠



- 设置坐标轴最小值/最大值

  #### [xAxis.](https://echarts.apache.org/zh/option.html#xAxis) min  /max

  ![image-20210706163027331](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163027331.png)

![image-20210706163104340](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163104340.png)

- 设置坐标轴间最小/大间隔

![image-20210706163226496](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163226496.png)

- ####  [xAxis.](https://echarts.apache.org/zh/option.html#xAxis) axisLine

  ==设置x坐标轴线==

  1.隐藏坐标轴线

  ![image-20210706163508435](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163508435.png)

  在设置了网格grid的情况下,隐藏坐标轴线可能更加美观,尤其是在x轴以非数值为间隔时

![image-20210706163603149](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163603149.png)

- #### [xAxis.](https://echarts.apache.org/zh/option.html#xAxis) axisTick

==设置坐标轴刻度==

![image-20210706163721147](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163721147.png)

和上面的混用,隐藏轴线和刻度线

1.让刻度线和标签名称对齐

![image-20210706163811830](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163811830.png)

2.刻度线朝向问题

默认为true朝外

![image-20210706163925635](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706163925635.png)

3.length设置长度

4.也可以设置样式

- #### [xAxis.](https://echarts.apache.org/zh/option.html#xAxis) axisLabel  设置坐标轴标签

color设置标签字体颜色

![image-20210706164309228](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706164309228.png)

- #### [yAxis.](https://echarts.apache.org/zh/option.html#yAxis) [type](https://echarts.apache.org/zh/option.html#yAxis.type) 

设置轴的类型

![image-20210706165304005](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706165304005.png)

- #### [xAxis.](https://echarts.apache.org/zh/option.html#xAxis) splitLine

  网格分割线,x,y轴都有

  splitline网格分割线

  grid网格线

  axisLine 坐标轴

  axisTick 刻度

  axislabel 标签

  所有都可以设置颜色粗细大小位置等样式

![image-20210706165545521](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706165545521.png)

- 设置柱条宽度

  series

![image-20210706170141363](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706170141363.png)

![image-20210706170111043](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706170111043.png)



#### 3.系列 series 表组 

stack 可以设置堆叠柱状图

只需要控制stack值相同即可,stack是字符串

![image-20210706170518787](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706170518787.png)

### 3.类目数据是什么?

就是分类数据

它不是连续的数值数据,比如下面的周日到周一,他们本身无法被数值表示

![image-20210706165020157](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706165020157.png)

所以有个特别对应的type category轴

value设置类目属性的名称

![image-20210706165139139](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706165139139.png)

![image-20210707094529110](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707094529110.png)

![image-20210707095853898](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707095853898.png)

![image-20210707100014612](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707100014612.png)

![image-20210707100137022](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707100137022.png)

![image-20210707100248337](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707100248337.png)

图形颜色默认从option.color里面拿,所以要写

![image-20210707100459789](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707100459789.png)

![image-20210707101259003](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707101259003.png)

不写默认没有



静止鼠标悬停放大

![image-20210707101726138](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707101726138.png)

设置圆心相当容器坐标

![image-20210707105024840](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210707105024840.png)
