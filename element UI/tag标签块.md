## el-tag

```html
         <div class="goods-price">
              <el-tag hit type="warning">{{ item.price }}</el-tag>
              <el-tag v-for="label in item.label" :key="label" hit>
                {{ label }}
              </el-tag>
            </div>
```

![image-20210628105715448](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210628105715448.png)