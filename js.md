js

JSON

基于ES规范的子集,是一种数据交换格式

> JSON是什么?

XML:早期数据传输,因为比较规范,扩展性好

BSON:就是二进制的json  

- JSON(Object Notation， JS对象简谱):基于ES规范的子集,是一种数据交换格式

- 简洁,清晰的 **层次结构** 使其成为理想的数据交换语言
- 人:易于阅读和编写 机器:易于解析和生成 网络:提高传输效率

由于在JavaScript中一切都为对象,任何JS支持的类型都可以用JSON来表现(包括number,字符串,对象,数组)

#格式:

- 对象都用{}  {"name":"对象"}
- 数组都用[] 
- 所有的键值对 key:value

#JSON方法(有且只有两个)

- parse() 用于还原json字符串
- stringify() 用于将 JavaScript 值转换为 JSON 字符串

```javascript
//parse 意思为 解析,分析 
//stringify 意思为 字符串化

var user {
    name:"zudao",
    sex:"男",
    age:3,
};

    //把user 对象转化为json字符串
var jsonUser = JSON.stringify(user);

//结果分别在浏览器中用log输出,可以比较两者不同
    
//json本身还是一个字符串,{}大括号也是字符串的一部分
```

>JS对象 和 JSON 区别

```javascript
var obj = {
    a:'hello',
    b:'hellob'
};

var json = '{"a":"hello","b":"hellob"}';
```

5.3 ajax

