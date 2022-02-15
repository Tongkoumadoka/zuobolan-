## uniapp

`uni-app`是一个使用`Vue.js` 开发所有前端应用的框架，开发者编写一套代码，可发布到`iOS`、`Android`、`H5`、以及各种小程序（微信/支付宝/百度/头条/QQ/钉钉）等多个平台

![image-20210713112542153](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713112542153.png)

![image-20210713112625308](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210713112625308.png)

#### 1.加载数据判断

![image-20210706092925980](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706092925980.png)

```javascript
 init() {
      if (this.loaded) return;
      service.getUnmkForType({ type: "ZBZC" }, (res) => {
        console.log(res);
        this.list = res.data[0];
        this.loaded = true;
      });
    },
        
         data() {
    return {
      list: [],
      loaded: false,
    };
  },
```

![image-20210706101956990](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706101956990.png)

![image-20210706102055958](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210706102055958.png)

#### 2.对于经常要隐藏和显示的组件,用 v-show 控制

#### 3.做一个带滚动条的(动态图片展示栏)

```javascript
    <scroll-view class="left" :scroll-top="scrollTop" scroll-y>
        <view
          class=""
          v-for="(item, i) in list"
          :key="i"
          :class="[item.ID == id ? 'active' : '']"
          @click="personnelChange(item)"
        >
          <!-- <image :src="item.personImage || '@/static/img/rmsp.png'"></image> -->
          <image src="@/static/icon/human.png"></image>
          <text>{{ item.A0101 }}</text>
        </view>
      </scroll-view>

```

```
scroll-view 组件
scroll-y 和 scroll-x 组件决定滚动条方向
scroll-top 决定刷新
```

#### 4.flex内没有设置高度就不显示,必须要撑开

一个flex盒子,它本身没有任何内容,但是设置 了padding值,box-sizing为content,那么他还是会占据位置,只不过占据高度由padding 和 margin 垂直距离决定 ,也就是padding在content情况下也能撑开flex盒子

#### 5.!important 在样式中的作用

```css
.text-color {
  color: #747c8b !important;
}
```

