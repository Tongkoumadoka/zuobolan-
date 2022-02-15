H5新增

#### 1.怎么写

```html
// 这是默认的 
<input type="range" value="0" class="progress>
```

![image-20220211205824613](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211205824613.png)

![image-20220211210337813](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211210337813.png)

#### 2.清除默认样式

```
  -webkit-appearance: none;
  宽度一般都是自适应
   width: 100%;
   高度就是滑轨高
  	height: 
```

后面组件都是input的子类

#### 3.**给滑动轨道(track)添加样式**

```css
input[type=range]::-webkit-slider-runnable-track {
    height: 15px;
    border-radius: 10px; /*将轨道设为圆角的*/
    box-shadow: 0 1px 1px #def3f8, inset 0 .125em .125em #0d1112; /*轨道内置阴影效果*/
}
```

取消选中边框

原始的控件获取到焦点时，会显示包裹整个控件的边框，所以还需要把边框取消。

```css
input[type=range]:focus {
    outline: none;
}
```

#### 4.**给滑块(thumb)添加样式**

```css
input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    height: 25px;
    width: 25px;
    margin-top: -5px; /*使滑块超出轨道部分的偏移量相等*/
    background: #ffffff; 
    border-radius: 50%; /*外观设置为圆形*/
    border: solid 0.125em rgba(205, 224, 230, 0.5); /*设置边框*/
    box-shadow: 0 .125em .125em #3b4547; /*添加底部阴影*/
}
```



#### 5.更新轨道(track)颜色填充处理方式

```css
在input progress 样式中添加
background: -webkit-linear-gradient(#059CFA, #059CFA) no-repeat;
background-size: 0% 100%;
```

#### 6.对应的事件

```
@change
change事件指的是当输入框内容发生改变时触发的事件，前提是失去了焦点，才会触发到change事件


@input
input事件是指当输入框内容发生改变时就会触发，实时触发，不用失去焦点
拖动进度条就触发


vue中的$event.target.value 
获取当前事件所在dom的value
```



#### 7.range的html

```html
          <input class="progress"
                 type="range"
                 max="100"
                 min="0"
                 step="1"
                 @change="onProgressChange($event.target.value)"
                 @input="onProgressInput($event.target.value)"
                 :value="progress"
                 :disabled="!bookAvailable"
                 ref="progress">
```

