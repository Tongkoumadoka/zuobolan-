流程如下

- 配置顶部查询栏
- 配置新增,批量删除导出,显示功能栏
- 配置vxe-grid表格数据(里面一列写编辑和删除功能)
- 配置底部页面控制栏

对于表格中复选栏

![image-20210713170924823](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713170924823.png)

权当参考

![image-20210713171027736](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171027736.png)

 keep-source

是否保存原始数据,方便reset时恢复

![image-20210713171554121](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171554121.png)



![image-20210713171714517](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171714517.png)

stripe 控制是否会灰白间隔

![image-20210713171734606](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171734606.png)

resizable

是否允许拖动列宽调整大小

![image-20210713171839779](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171839779.png)

border

边框存在与否,最好是写,不然列之间没边框很难看

![image-20210713171946301](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713171946301.png)

:loading="布尔值"

是否显示加载

控制序号对应显示的值,如果不设置那么无论你到那一页都会从1开始计数

![image-20210713172423437](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713172423437.png)

```
    :seq-config="{
          startIndex: (tablePage.currentPage - 1) * tablePage.pageSize,
          
        }"
```

表单数据的导出

```
 :export-config="exportConfig"
 绑定一个对象
```

![image-20210713172550392](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713172550392.png)

![image-20210713172638979](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713172638979.png)

配置页面底部栏

![image-20210713173351562](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713173351562.png)

![image-20210713173412844](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713173412844.png)

vxe-model]是弹窗!

v-model根据布尔值控制它的显示

![image-20210713174541120](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713174541120.png)

