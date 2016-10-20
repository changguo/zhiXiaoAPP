# 基于Vue.js重构知晓APP项目

##下载
1. 在空白目录直接clone该项目
```js
  $ git clone git@github.com:chping2125/zhiXiaoAPP.git
```

2. 创建本地工作分支
shy分支：
```js
  $ git checkout -b shy
```

lee分支：
```js
  $ git checkout -b lee
```

lxn分支：
```js
  $ git checkout -b lxn
```

chping分支：
```js
  $ git checkout -b chping
```
然后将本地你的分支提交与远程分支建立联系，开发的时候在你的本地分支上开发，提交你的本地分支，勿动master分支。

# 开发目录解释
```
  zhiXiaoAPP
  |__prd:输出目录
  |   |__images：图片目录
  |   |   |__index: 主页 图片目录
  |   |   |__lee: 排行榜 图片目录
  |   |   |__lxn: 发现 图片目录
  |   |   |__my: 我的 图片目录
  |   |__mock：mock数据目录
  |   |   |__index: 主页 mock数据目录
  |   |   |__lee: 排行榜 mock数据目录
  |   |   |__lxn: 发现 mock数据目录
  |   |   |__my: 我的 mock数据目录
  |   |__bundle.css    单页面应用入口css文件（不可更改,自动编译）
  |   |__bundle.js    单页面应用入口js文件（不可更改，自动编译）
  |   |__index.html    单页面应用入口文件（不可更改，自动编译）
  |__src:工作目录
  |   |__scripts: js工作目录
  |   |   |__libs: 第三方js库目录
  |   |   |__tpls: 模板库目录
  |   |   |__util: 工具类目录
  |   |   |__views: 页面入口目录
  |   |   |__app.js: 应用入口目录
  |   |__styles: js工作目录
  |   |   |__lib: Yo框架lib目录（不可更改）
  |   |   |__usage: Yo框架工作目录（只解释常用目录）
  |   |   |   |__page: 应用入口目录
  |   |   |   |__views: 页面入口目录
  |__.babelrc: babel配置文件
  |__.gitignore: git忽略上传配置文件
  |__package.json: npm组件管理配置文件
  |__README.md: 说明文档
  |__webpack.config.js: webpack配置文件

```
# 开始开发
1. 安装依赖模块
```js
  $ npm install
```

2. 运行
```js
  $ npm run build
```
建议：开启两个git bash，一个开启``webpack -w``，另一个开启``npm run build``。这样可以保证实时编译和浏览器刷新。
