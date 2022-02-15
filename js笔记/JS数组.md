1.数组的一些性质

 首先在JS中数组的length属性是可以赋值修改的,当修改后length小于原长度时,调用超出的数组元素index部分会输出undefined,当 修改后大于原长度,调用未赋值部分也会输出undefined

可以利用length属性方便的给数组末尾添加新项

```
color [color.length] = "red";
```

判断该变量是否为数组

```
Array.isArray(arr)
返回布尔值,括号为要判断的数组变量名称
```

数组调用tostring()方法

```javascript
<script>
    var fruit = ["apple", "banana", "orange"];
    var mix = fruit.toString();
    console.log(mix); // apple,banana,orange
</script>
```

结论:无论数组内元素类型为何,都会被转换为字符串,用逗号隔开,除非存储的是对象元素

```javascript
    var fruit = ["apple", { name: "小花", age: 16 }, ["actioin", 6]];
    var mix3 = fruit.toString();
    console.log(mix3); // apple,[object Object],action,6
```

注意返回的对象类型为字符串!!

alter()方法内调用的是字符串参数,所以如果输入数组他会自动先在后台调用tostring()方法

join("分隔符")方法

```
join()方法可以修改分割分号,甚至删除分割符号
比如join("") 无分隔符
   join() 分隔符为默认的逗号,
```

![image-20210607095128933](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210607095128933.png)

数组的栈方法

检测数组里面有没有该字符

```javascript
let arr = ["action","act"."pass"];
let count =0;
for (let i =0 ; i<arr.length; i++) {
	if(arr[i].include("abc");){
	count++
	}
	//通过循环就可以查找数组中所有字符串元素是否有对应字符
}


//返回布尔值
//这个方法可以方便的查找
```

