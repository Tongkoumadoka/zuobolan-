主题切换

1.themes 对象

````js
themes 对象中的api
注册主题:主题名称 主题样式
this.register(name,styles)
切换主题
this.themes.select(name)

   // 注册主题
    initTheme() {
      console.log(this.themeList, 111)
      this.themeList.forEach((theme) => {
        // 注册名称和对应style
        this.rendition.themes.register(theme.name, theme.style)
      })

      // 选择默认样式
      this.rendition.themes.select(this.defaultTheme)
    },
````



```
themes配置项
themesList:[
{
	name:
	style{
	
	}
}
]
```

2.locations 对象

```
默认不生成,因为消耗性能,需要通过epubjs钩子函数来实现

this.book.ready.then(()=>{
	return this.book.locations.generate()
}).then(resulet=>{
	console.log(result)
})

输出结果就是定位符epubcfi
```

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

分页样式设置

![image-20220211204839664](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211204839664.png)

![image-20220211204910465](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211204910465.png)

![image-20220211204919952](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211204919952.png)

book.section

```
book.section(章节数)
获取当前章节

渲染当前章节页
this.currentBook.rendition.display(sectionInfo.href)

```

book.spine

获取总章节数目

![image-20220211215158854](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211215158854.png)

```
   const currentLocation = this.currentBook.rendition.currentLocation()
   获取当前位置
```

![image-20220211215941265](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20220211215941265.png)
