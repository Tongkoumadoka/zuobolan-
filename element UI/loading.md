### 加载

v-loading="布尔值" 就可以显示加载动效![image-20210623160521813](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623160521813.png)

```HTML
    <el-table
      v-loading="listLoading"  //表单区域加载
      :data="list"
      @selection-change="setSelectRows"
    >
        //因为v-loading是一个属性,所以在vue中直接绑定对应元素即可
        之后通过调用方法让其随着请求加载而使用
      data() {
        listLoading: true, //加载显示
      }
```

### 服务