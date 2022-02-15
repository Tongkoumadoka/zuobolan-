#### 1.多内容循环

对于多内容的组件循环,可以直接用template,它本身是不可见的

当然也可以用div或者view盒子作为父容器循环

![image-20210713141141915](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713141141915.png)

#### 2.单独语句循环

如果只循环单内容,可以直接在该内容内写v-for

#### 3.自定义组件循环

![image-20210713141902913](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713141902913.png)

#### 4.v-for中key 的存在是必须的,一定要写

它绑定的数据必须是唯一表示该组信息的值

比如id 或者什么,要和后端商量好

#### 5.v-for把一组数据分别传递给子组件

```
比如这个 my -component 子组件,它那边会设置 prop去接收 item!!
每一次循环会接收一个item,从而把父组件一组数据分个传个每一循环出来的子组件
```

![image-20210713142131087](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713142131087.png)

