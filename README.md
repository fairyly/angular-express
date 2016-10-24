# angular-express

>
运行这个demo步骤：本地需要node环境，安装了express;

1.git clone https://github.com/fairyly/angular-express.git

2.cd angular-express

3.node app.js

# angular+express入门搭建网站

**1、** 使用Angular JS框架开发好Html页面以及对应的JS文件；

**2、** 安装express到项目中：npm install express；
   可以全手动新建或者使用express创建项目：用express创建一个app项目命令：express hello-world -e （hello-world为项目名，-e表示支持ejs模板引擎，默认是jade），会自动生成下面这些需要的目录和文件（如:public,routes,views,还有app.js和package.json文件），然后使用npm install安装依赖；
   
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
打开本机浏览器访问：http://localhost:3000 即可看到angular应用中的页面效果
