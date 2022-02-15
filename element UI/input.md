## input

```html
//表单组件都必须放到 <el-form-item>里面 ,无论button还是 input

<el-form-item>
            <el-input
              v-model.trim="queryForm.title"
              placeholder="请输入标题"
              clearable
            />
          </el-form-item>

```

### 属性

1.设置情况按钮

```
clearable 写入
```



![image-20210623164542451](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623164542451.png)

```javascript
```

![image-20210623164459848](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623164459848.png)

2.清除输入字符串的前后空格

```HTML
保证输入的时候没有空格
     <el-input
              v-model.trim="queryForm.title"
     />
在v-model后加.trim
```

![image-20210623165955328](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623165955328.png)

![image-20210623165959099](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210623165959099.png)

3.设置显示输入长度限制

![image-20210628101339461](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210628101339461.png)

![image-20210628101357337](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210628101357337.png)

4.输入提示建议

```
 autocomplete
```

5.设置tab键跳转顺序

```
    tabindex="1"
    tabindex="2"
    按tab键会跳转到对应顺序的输入框
```

6.设置密码可见框

![image-20210629180036955](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210629180036955.png)

7.可以设置文本域![image-20210629180203180](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210629180203180.png)
