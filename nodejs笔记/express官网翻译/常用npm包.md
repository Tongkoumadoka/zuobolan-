#### 1.cors 

解决跨域问题

##### Simple Usage (Enable *All* CORS Requests)

允许任何跨域请求

```js
var express = require('express')
var cors = require('cors')
var app = express()
 
app.use(cors())
 
app.get('/products/:id', function (req, res, next) {
  res.json({msg: 'This is CORS-enabled for all origins!'})
})
 
app.listen(80, function () {
  console.log('CORS-enabled web server listening on port 80')
})
```

##### 允许向单个route的跨域请求

对于/products/:id 的http GET报文,允许跨域访问

```js
var express = require('express')
var cors = require('cors')
var app = express()
 
app.get('/products/:id', cors(), function (req, res, next) {
  res.json({msg: 'This is CORS-enabled for a Single Route'})
})
 
app.listen(80, function () {
  console.log('CORS-enabled web server listening on port 80')
})
```

##### 对跨域白名单进行配置

```
```

