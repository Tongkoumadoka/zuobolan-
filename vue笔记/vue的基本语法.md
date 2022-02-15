基本语法和对应

component.template ----创建自定义元素(标签)

component.props ------创建自定义元素的自定义属性

{{vuedata中变量}}--------绑定innerHTML内容

v-on ------事件响应

v-if ------属性中的条件判断(值为布尔类型),来决定这个元素(标签)是否被使用

v-for ------- 循环输出数组

v-bind ------绑定元素中属性和vue实例中属性---单向数据绑定

v-model -----绑定input(表格输出)显示内容---双向数据绑定

![image-20210608092626042](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608092626042.png)



v-model 后面无需写属性,因为它直接对接data中的数据,

![image-20220117100542758](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220117100542758.png)

![image-20220117100537910](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220117100537910.png)

v-model是表单元素独有,要实现双向绑定就一定需要用户输入,所以它默认绑定value

v-model = "msg"

![image-20210608092945766](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210608092945766.png)

v-for -----先接收数组[存储对象类型元素],本质接收单独的对象元素,他会声明一个新变量

v-html 让变量内的HTML内容变成指令而不是在{{}}中作为文本输出

事件触发的嵌套----子事件被触发对应父事件也会触发

click.stop ------停止事件的连续触发,只触发当前点击事件

v-bind:class 的使用方法 :它可以条件控制能应用多少class(样式),条件满足就能用,不满足就不能

而且因为是绑定条件,所以当vue实例中数据动态变化导致结果动态变化时,这边的class显示应用也随之变化

template 插入 v-if 来隐藏或者显示多个元素

v-show 也是条件判断,但它只是简单的将display样式做了修改

v-for遍历对象属性

组件中必须使用函数式data

data(){

}

![image-20210604090811546](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090811546.png)

7个属性

![image-20210604090824728](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604090824728.png)

![image-20210604091441103](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091441103.png)

![image-20210604091458855](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091458855.png)

![image-20210604091629516](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091629516.png)

![image-20210604091639524](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091639524.png)

![image-20210604091651968](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091651968.png)

![image-20210604091703040](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091703040.png)计算属性的作用

![image-20210604091726210](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091726210.png)

![image-20210604091731654](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091731654.png)

![image-20210604091736765](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091736765.png)

![image-20210604091744865](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091744865.png)

![image-20210604091811787](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091811787.png)

mvvm

![image-20210604091820468](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091820468.png)

![image-20210604091827948](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091827948.png)

![image-20210604091853406](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091853406.png)

![image-20210604091858883](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091858883.png)

![image-20210604091917045](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091917045.png)

![image-20210604091921209](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091921209.png)

![image-20210604091936901](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091948439.png)

![image-20210604091943503](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210604091943503.png)