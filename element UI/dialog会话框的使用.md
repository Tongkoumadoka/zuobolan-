## dialog

```html
<el-dialog
    :title="title"
    :visible.sync="dialogFormVisible"
    width="500px"
    @close="close"
  >
    //分析属性
   1.  :title="title" 实际上等于
    v-bind:title = "title"
    它把会话中的title属性绑定了data中的title数据
   2. width 就是它的宽度,高度似乎是默认的
   3.visible 是它是否可见
```

![image-20210622161208273](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622161208273.png)

![image-20210622161439740](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622161439740.png)