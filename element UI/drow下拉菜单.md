## 下拉菜单

<el-dropdown>

```html
    <el-dropdown @command="handleCommand" @visible-change="handleVisibleChange">
      <span class="more">
        {{ translateTitle('更多') }}
        <vab-icon
          :class="{ 'vab-dropdown-active': active }"
          class="vab-dropdown"
          icon="arrow-down-s-line"
        />
      </span>
      <template #dropdown>
        <el-dropdown-menu class="tabs-more">
          <el-dropdown-item command="closeOthersTabs">
            <vab-icon icon="close-line" />
            {{ translateTitle('关闭其他') }}
          </el-dropdown-item>
          <el-dropdown-item command="closeLeftTabs">
            <vab-icon icon="arrow-left-line" />
            {{ translateTitle('关闭左侧') }}
          </el-dropdown-item>
          <el-dropdown-item command="closeRightTabs">
            <vab-icon icon="arrow-right-line" />
            {{ translateTitle('关闭右侧') }}
          </el-dropdown-item>
          <el-dropdown-item command="closeAllTabs">
            <vab-icon icon="close-line" />
            {{ translateTitle('关闭全部') }}
          </el-dropdown-item>
        </el-dropdown-menu>
      </template>
    </el-dropdown>
```

1.基本结构

![image-20210625154920400](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210625154920400.png)

```html
//span标签和菜单栏并列,它放置蓝色的菜单标题
//menu存放所有下拉选项,它被设置成一个插槽
  1.<el-dropdown-menu slot="dropdown">
 
  2.<template #dropdown>
        <el-dropdown-menu class="tabs-more">
      
```

2.修改激活方法

```html
    <el-dropdown trigger="click">
        //点击下拉
        //默认是hover
```

