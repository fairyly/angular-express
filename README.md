# angular-express
angular-express入门搭建网站

**1、** 使用Angular JS框架开发好Html页面以及对应的JS文件；

**2、** 安装express到项目中：npm install express；
   新建public目录，放入angular应用里的文件；
   新建app.js建立一个server，
```javascript
var express = require('express');
var http    = require('http');
var path    = require('path');
var routes  = require('./routes/index');
 
var app = express();

 app.use(express.static(path.join(__dirname, 'public')));
 
 app.use('/', routes);
 
 http.createServer(app).listen(3000);
```
新建routes目录，在里面创建index.js文件；这个文件是关于路径/的路由信息
```javascript
var express = require('express');
var router = express.Router();

/* GET home page. */
router.get('/', function(req, res, next) {
  res.render('index', { title: 'Express' });
});

module.exports = router;
```
**3、**把服务运行起来
```
node app.js
```
打开本机浏览器访问：localhost:3000即可看到angular应用中的页面效果
