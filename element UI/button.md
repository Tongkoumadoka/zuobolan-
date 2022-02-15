## MessageBox 弹框

```html
 <el-button type="text" @click="open">点击打开 Message Box</el-button>

本质是是一个简单的button
```

1.模拟系统的confirm确认消息

![image-20210623140759807](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623140759807.png)

```javascript
分别调用对应方法即可
 methods: {
      open() {
        this.$confirm('此操作将永久删除该文件, 是否继续?', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning'
        }).then(() => {
          this.$message({
            type: 'success',
            message: '删除成功!'
          });
        }).catch(() => {
          this.$message({
            type: 'info',
            message: '已取消删除'
          });          
        });
      }
    }
//$confrim $BaseConfirm函数都行
//对应参数有三个,分别用来设置: (警告内容,标题,{确认按钮内容/取消按钮内容/弹框类type})
message title 
//$message()则执行选择后的操作
```

![image-20210623141226669](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623141226669.png)

2.设置圆角按钮

```
  <el-button round type="primary"> 加round
```

