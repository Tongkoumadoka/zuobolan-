##### 1.存储空间 5M 

比起cookie 4k 要大很多

##### 2.引入

```
npm i --save web-storage-cache 引入库
```



##### 3.设置utils/localStorage.js文件

```javascript
import Storage from 'web-storage-cache'

// 注意Storage是自带的
const localStorage = new Storage()

export function setLocalStorage(key, value) {
  return localStorage.set(key, value)
}

export function getLocalStorage(key) {
  return localStorage.get(key)
}

export function removeLocalStorage(key) {
  return localStorage.delete(key)
}

export function clearLocalStorage() {
  return localStorage.clear()
}

```

##### 4.注意刷新页面没有初始化默认设置内容的过程

所以如果有初始化设置,也一定要进行缓存操作的设置!!!

在mounted() init()中对应设置