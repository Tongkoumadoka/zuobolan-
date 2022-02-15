![image-20210623113752958](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623113752958.png)

![image-20210623114439103](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623114439103.png)



![image-20210623114652830](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623114652830.png)

```html
    <el-pagination
      :current-page="queryForm.pageNo"
      :layout="layout"
      :page-size="queryForm.pageSize"
      :total="total"
      background
      @current-change="handleCurrentChange"
      @size-change="handleSizeChange"
    />
```

//单标签,放于句末

因为页面能显示的页数有限

所以需要考虑

- pageNo 当前页数,显示该页数据
- pageSize 每次显示多少条(比如20条一页之类的)
- ​      @current-change="handleCurrentChange"  当前页数改变应该触发页数跳转跳转
-   @size-change="handleSizeChange" 页面尺寸改变也应该触发对应方法 

- ​      :total="total" 总条数,一共有多少数据

![image-20210628110503883](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210628110503883.png)

点击时会返回对应参数到触发函数
