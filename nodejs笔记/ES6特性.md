1.es6的兼容性问题

> 兼容表 : http://kanggax.github.io/compat-table/es6/

#转换ES5的方法

- 在线转换 (每次都要加载转换包,会加大页面渲染时间)
- 提前编译 (在服务器端提前转换,不影响客户端渲染)

#比较通用的工具

- babel
- jsx
- traceur
- es6-shim

#浏览器支持

- ie10以上
- 





```javascript
//暴露接口
//注意如果暴露接口前后键值对相同,比如 add:add, 直接写一个就行 add,
//逗号间隔

module.exports = {
    n:n,
    add:add,
    subtract,
}
```

