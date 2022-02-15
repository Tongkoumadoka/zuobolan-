## checked

````html
  <el-checkbox-group v-model="checkList">
    <el-checkbox label="复选框 A"></el-checkbox>
    <el-checkbox label="复选框 B"></el-checkbox>
    <el-checkbox label="复选框 C"></el-checkbox>
    <el-checkbox label="禁用" disabled></el-checkbox>
    <el-checkbox label="选中且禁用" disabled></el-checkbox>
  </el-checkbox-group>
````

复选要用group,单选只要checkbox

返回数据需要用数组来接,另外,`label`与数组中的元素值相对应，如果存在指定的值则为选中状态，否则为不选中。

也就是选中则数组中放入对应label内容

```javascript
 data () {
      return {
        checkList: ['选中且禁用','复选框 A']
      };
    }
```

