![image-20210714091944388](C:\Users\inui\AppData\Roaming\Typora\typora-user-images\image-20210714091944388.png)

vue实例可以直接调用的属性

```
vm.$options 之类的
```

### 1.$options

​	options主要用来设置和获取vm实例data外定义的的自定义属性

```javascript

<script>
export default {
  myoption: 'myoption',
  // 这就是自定义属性myoption 在data外定义
  data () {
    return {
      mydata: 11111
    }
  },
  methods: {
  }
}
</script>
 

this.$options 即可以获取自定义属性，也可以增加自定义属性，而且，获取自定义属性的方法有两种。
      this.mydata = this.$options['myoption']
      this.mydata1 = this.$options.myoption
```

### 2.$data

$data表示vm实例中的data对象,它可以观察里面定义的所有属性

并且使用数据代理的方式让 

```
vm.$data.property = $vm.property
方便我们更简单的书写
```

### 3.$props

### 4.$attr

