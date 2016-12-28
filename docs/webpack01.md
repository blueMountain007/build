webpack
-------

前身: browserify(缺点：只能转化js)

1.	安装webpack命令环境 ----------------------

**基于node环境***node -v**npm -v***webpack作用\** - 一切都是模块化(js, css, 图片等) - 一个模块加载器、打包工具

**安装webpack***npm install webpack -g*  
验证: webpack --version

1.	package.json ---------------

*npm init*

1.	安装本地webpack ------------------

*npm install webpack -D*

---

**自动解决依赖** - 默认支持commonJS规范 - 默认只支持js文件

对于非js文件====> 需要 loader(转化器)

*css文件* - npm install style-loader css-loader -D - 在webpack中，多个loader加载时用" ! "连接

4.配置webpack.config.js
-----------------------

5.常用参数
----------

*webpack* 开发环境下编译(打包)*webpack -p* 生产环境下编译(压缩) webpack -w 监听文件改动,自动编译(速度快) webpack -d 开启/生成 source maps(用来调试)

webapck -wdp

如果不用webapck.config.js自定义配置文件名字config.js
----------------------------------------------------

*webpack --config config.js*

ES6 -> babel 转化
-----------------

*npm install babel-loader babel-core babel-preset-es2015 -D*

**ES6 中的模块** - 导出模块: export default {} - 引入模块: import 名字 from 模块名

**配置babel的preset** 1). webpack.config.js`javascript
    babel:{
        "presets": ['es2015']
    }
` 2). .babelrc 配置`javascript
{
    "presets": ['es2015']
}
`

---

第二部分:

### webpack-dev-server

**安装命令环境:***npm install webpack-dev-server -g*

listen EACCES 127.0.0.1:8080 *此端口号已经被监听过了*

**常用参数***webpack-dev-server --port 8088* 端口号*webpack-dev-server --inline* 改变完代码以后，自动刷新浏览器*webpack-dev-server -hot* 热重载(局部更改)

#### 使用方式

**1. 终端**`javascript
webpack-dev-server --port 8088 --inline --hot
`**2. webpack.config.js**`javascript
    devServer:{
        port: 8088,
        inline: true
    }
`**3. 把运行命令放到package.json文件**`javascript
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "webpack-dev-server --inline --hot --port 8088"
  },
` 终端： npm run dev

---

### resolve: 配置(在webpack.config.js中新增)

```javascript
    resolve: {
        "extensions": ['', '.js', '.css', '.json', '.jsx'] //可以省略的后缀名
    }

```

---

react 配置
----------

-	ES6 语法: babel-core babel-preset-es2015

babel-loader babel-preset-react //react的预设 react-hot-loader

---

*安装react相关库* react、react-dom

---

webpack高级功能: 插件、分片
---------------------------
