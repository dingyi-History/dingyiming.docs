# 【node初体验】【0.1】node建站 基础流程
> 这是我今天学习imooc.com中Node教程的笔记
> 本nodejs基础建站使用工具
> * 由``npm install `` 下载工具 `` express框架``、``jade模板引擎``、``mongoose``、``moment时间插件``
> * (全使用vim进行编辑)
## 步骤 1 . 新建项目文件
* 新建项目目录 `` mkdir imooc ``
* 进入 `` cd imooc ``
* 新建模板文件夹 views  `` mkdir views ``
* 在views目录中建立四个视图模板文件
 ``cd views ``
``  vim index.jade ``
``  vim admin.jade ``
``  vim list.jade ``
``  vim detail.jade ``
* 新建 入口文件 `` app.js vim app.js ``
* 在imooc文件夹中npm命令行获取组件依赖安装
`` npm install jade express mongoose moment ``
* 项目目录初始化命令
`` imooc/  ``
`` npm  install express ``
`` npm install jade  ``
`` npm install  mongoose ``
`` npm install moment  // 时间插件 ``
`` npm install bower -g  ``
`` bower install bootstrap  ``

## 步骤2.1  编写入口文件 app.js  `` vim app.js ``
> 基础内容
```
var express = require('express') //引入express模块
var app = express() //实例化express

app.set('view engine','jade') //设置模板引擎jade
app.set('port',3000) //设置端口

//路由设置
app.get('/', function(req,res){
    res.render('index',{title:'imooc'})  
   //'index'=>index.jade 文件 ； 并输入title变量
})
```

## 步骤 2.2 修正 ``app.js ``并加入详细路由内容

`` vim app.js ``
```
var express = require('express')
var port = process.env.PORT || 3000
var app = express()

app.set('views','./views')
app.set('view engine','jade')
app.listen(port)

console.log('imoooc started on' + port)


//index page
app.get('/',function(req,res){

   res.render('index',{
    title: '罗思菊'        
})
})

//detail page
app.get('/movie/:id',function(req,res){
    res.render('detail',{
    title: 'imooc 详情页'
})
})


//admin  page
app.get('/admin/movie',function(req,res){
    res.render('admin',{
    title: 'imooc 后台登陆页'
})
})


//list  page
app.get('/admin/list',function(req,res){
    res.render('list',{
    title: 'imooc 列表页'
})
})

```
## 步骤3. 在``/views``下四个模板文件基础内容
> jade视图模板
```
doctype
html
    head
         meta(charset="utf-8")
         title #{title}
    body
         h1 #{title}
```
* 注意缩进
* `` #{}`` 变量占位符
## 步骤4. 启动测试
* 在``/imooc ``下``cd imooc``，启动 `` node app.js ``
* 运行在默认端口`` localhost:3000 ``
* ``每次更改文件后都需要重启 ``

## vim简单用法
> 还只是接触了一点用法，在后续nodejs的学习中我会继续使用vim，同时多熟悉vim的操作，甚是喜欢这样干净的文本编辑器。
* ``vim ``  新建或打开文件
* ``i `` 插入内容
* `` dd `` 删除一行
* `` ECS `` 回到正常模式
* `` :set number ``显示行号
* `` y行数  复制几行``
* ``yy 复制当前行``
* ``p 粘贴``
* ``u 撤销``
* ``#G 跳到#行``
>其他待发现待学习，Vim很可爱。

## node初体验感受
* 之前一直在用php，js只是鲜有接触，只是学了点用在前端的基础内容，也一直困惑着没能多学学，没能更好地认知；
* 今天体验了下nodejs，发觉我已经喜欢上这个简洁、快捷的web建站工具了，将继续学习下去；
# 学习的教程地址
> 学习imooc node教程 笔记
> 视频教程地址 ： http://www.imooc.com/learn/75


> 地址：http://segmentfault.com/a/1190000003842725
