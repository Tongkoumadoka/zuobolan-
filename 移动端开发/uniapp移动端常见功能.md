1.修改全局样式

​	@1.设置全局背景色

在app.vue中可以设置

![image-20210714205528680](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210714205528680.png)

​	包括全局背景色之类的

2.全局取消使用原生导航栏

![image-20210714205127816](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210714205127816.png)

```json

"navigationStyle": "custom",
			"app-plus": {
			"titleView": false
		}
	// 这是取消H5上的原生导航栏
	// app-plus写到单独页面就是取消单独页面导航栏
	// 全部写到"globalStyle"内
```

3.小程序适配的单位rpx

@1.rpx在vscode不显示颜色是不起效果吗?

起效果,只是显示灰色而已

![image-20210714205857738](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210714205857738.png)

@2.为什么要用rpx适配微信小程序

4.2倍图 @2x.png图片的处理