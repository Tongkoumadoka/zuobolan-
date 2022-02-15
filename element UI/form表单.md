from

1.inline 属性 

为true就是表单组件排一行

```html
 <el-form :inline="true" :model="queryForm" @submit.native.prevent> 
```

阻止表单提交

````html
@submit.native.prevent
````



![image-20210623164935933](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623164935933.png)

![image-20210623165023491](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623165023491.png)

3.**表单元素绑定**

```html
<el-form :inline="true" :model="queryForm" @submit.native.prevent>
     <el-form-item>
            <el-input
              v-model.trim="queryForm.title"
              placeholder="请输入标题"
              clearable
            />
          </el-form-item>
      </el-form>
// 注意:
整个表单 <el-form> 他用:model=""绑定vue中data
    表单组件<el-input></el-input>用 v-model =""绑定数据
    这是最重要的区别,否则会报错!!!!!
```

4.设置表单排序

![image-20210625141949483](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625141949483.png)

```html
//1.首先在el-table标签内设置 default-sort 属性
// order是排序的方式,默认升序默认从小到大, prop是排序的列对应的数据名,
<el-table
	// 设置默认排序类和方式
    :default-sort = "{prop: 'date', order: 'descending'}"
    >
    // 2.在对应需要排列的列item中设置sortable,表示要排序
    
    <el-table-column
      prop="date"
      sortable
      width="180">
    </el-table-column> 
    
      </el-table>
```

5.接收table数据

用:data 接收传来的table

子列 用  prop="name" 接收对应data中属性的数据

laber 设置子列的第一行名称

![image-20210625142648918](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625142648918.png)

6.设置input前文字对齐方式

![image-20210628094415101](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210628094415101.png)

```html
     <el-form
          ref="form"
          :model="form"
          :rules="rules"
          class="login-form"
          label-position="left" //设置左对齐
        >
```

