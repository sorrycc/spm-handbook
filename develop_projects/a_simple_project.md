# 一个简单的单页应用

假设需求是：

1. 通过 [normalize.css](https://github.com/necolas/normalize.css) 进行 css reset
1. 通过 jQuery 在页面上输出 `hello world`

## 目录初始化

目录文件列表如下，详见 [Standalone Example](https://github.com/sorrycc/spm-project-examples/tree/master/standalone) 。

```
- index.html
- index.css
- index.js
- package.json
```

注意：

1. package.json 需包含 `"buildArgs": "--include standalone"`
1. html 里引用 css 和 js 时，可以用开发状态的路径 `./index.js`，也可以用发布状态的路径 `./dist/{{name}}/{{version}}/index.js`
1. 如果你用 yeoman，也可以通过 `yo ...` (TODO)


## 开发

安装 jquery 和 normalize.css 依赖

```bash
$ spm install jquery normalize.css --save
```

编辑 `index.js`

```javascript
var $ = require('jquery');
$('body').append('<div>Hello World!</div>');
```

编辑 `index.css`

```css
@import 'normalize.css';
```

编辑 `index.html`

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Single Page Example</title>
</head>
<body>
  <link rel="stylesheet" href="./dist/todo/0.1.0/index.css" >
  <script src="./dist/todo/0.1.0/index.js"></script>
</body>
</html>
```

## 调试

项目调试需要安装 spm-server，用于开启服务器进行本地调试：

```bash
$ npm install spm-server -g
$ spm-server
```

正常情况下，会看到以下输出：

```bash
     livereload: listened on 35729
         server: listen on 8000
```

然后在浏览器里打开 http://localhost:8000 即可进行调试。(注：livereload 功能最好和 [chrome 插件](https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei)配合使用)

## 部署/发布

1. 执行 `spm build`
1. 部署/发布 `index.html` 和 `dist` 目录
