#### 1.构造整个表格的结构

首先是容纳整个表格的标签

```html
<el-table>
    //1.第一列
 <el-table-column
        prop="date"
        label="日期"
        width="180">
  </el-table-column>
    //2.第二列
  <el-table-column
        prop="name"
        label="姓名"
        width="180">
   </el-table-column>
    //3.第三列,再表格中放交互操作和按钮
   <el-table-column align="center" label="操作" width="85">
        <template #default="{ row }">
          <el-button type="text" @click="handleEdit(row)">编辑</el-button>
          <el-button type="text" @click="handleDelete(row)">删除</el-button>
        </template>
    </el-table-column>
    ...想要多少列就加多少个  <el-table-column> </el-table-column>标签
</el-table>
```

//注意,最开始的表格是没有数据的

#### 2.设置各列的名称等

```html
 <el-table-column
        prop="date"  //设置列的
        label="日期"  //设置列的名称,会显示在列头
        width="180">  //设置列的宽度
  </el-table-column>
```

![image-20210622152105970](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622152105970.png)

#### 3.设置选择(多选)列

```HTML
 <el-table-column
      type="selection"
      width="55">
</el-table-column>
// 直接在需要的位置添加 一个列组件, 设置type="selection"即可
```

![image-20210622152425640](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622152425640.png)

#### 4.prop属性存储数据

![image-20210622153943263](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622153943263.png)

#### 5.手动拉伸表格时能自适应拉伸距离

```HTML
<el-table-column show-overflow-tooltip>
在表单添加属性show-overflow-tooltip
```

#### 6.表单选择项发生改变时触发事件

```html
  <el-table
      v-loading="listLoading"
      :data="list"
      @selection-change="setSelectRows"
    >
 //selection-change 这个事件就是selection
 //可以通过它接收触发方法接收选择的表格对象数据
 //data是接收整个表格数据     
```

![image-20210622154739372](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622154739372.png)

![image-20210622154305362](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622154305362.png)

![image-20210622150929021](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210622150929021.png)

#### 7.设置底部分页![image-20210623113739393](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623113739393.png)





### 功能的实现

如何在表单中单独一列用作操作按钮 operate button

![image-20210714133718399](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210714133718399.png)

```HTML
 <el-table-column
      align="right">
     //这一个作用域插槽是搜索栏
     //当然也可以不写这个 而是在item列中加label 属性用文字标题,根据需要来
     //header才会分发到对应的header slot中 ,也就是只显示在列标题
      <template #header= "{ scope }">
        <el-input
          v-model="search"
          size="mini"
          placeholder="输入关键字搜索"/>
      </template>
     
     // 这一行具名插槽是默认,所以填充列的所有内容格
      <template #default= "{ scope }">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">Edit</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">Delete</el-button>
      </template>
   </el-table-column>

流程如下
1. 单独取一个列item用来封装
2. scope包含所有数据

```

