# 应用开发

## Demo

![](http://gtms04.alicdn.com/tps/i4/TB1iN.pGXXXXXa3XpXXDs3XUXXX-699-360.gif)

## 开发

新建 `package.json`：

```javascript
{
  "name": "helloworld",
  "version": "0.1.0",
  "spm": {
    "output": [
      "index.js",
      "index.css"
    ],
    "buildArgs": "--include standalone"
  }
}
```

安装依赖：`jquery` 和 `normalize.css`

```bash
$ spm install jquery normalize.css --save
```

新建 `index.js`：

```javascript
var $ = require('jquery');

$('body').append('<div>Hello World!</div>');
```

新建 `index.css`：

```css
@import 'normalize.css';

div {
  color: red;
}
```

新建 `index.html`：

```html
<link rel="stylesheet" href="index.css" />
<script src="index.js"></script>
```

## 调试

`spm-server` 是 spm 的应用调试工具，并且封装了一些常用的调试功能，比如 `livereload`, `https`，`less` 和 `coffee` 等预编译语言等，详见 [spm-server](spm-server.md)。

```bash
$ npm install spm-server -g
$ spm-server
         server: listen on 8000
```

然后在浏览器里打开 http://localhost:8000 。


## 构建

```bash
$ spm build

          start: build helloworld@0.1.0
      arguments: dest = dist
      arguments: cwd = $CWD
      arguments: include = standalone
      arguments: ignore =
      arguments: skip =
      arguments: idleading = {{name}}/{{version}}
      arguments: install = true
        install: normalize.css@3.0.1
          found: normalize.css@3.0.1
        install: jquery@2.1.1
          found: jquery@2.1.1
        package: analyse infomation
        package: dependencies: normalize.css,jquery
        package: files: index.js,index.css
         output: files: index.js,index.css
          start: task clean
            end: task clean
          start: task build
           size: index.js 29.07kB (gzipped)
           size: index.css 0.88kB (gzipped)
           size: total 29.95kB (gzipped)
            end: task build
         finish: build helloworld@0.1.0 (3080ms)
```

```bash
$ tree dist
dist
`-- helloworld
    `-- 0.1.0
        |-- index-debug.css
        |-- index-debug.js
        |-- index.css
        `-- index.js
```

## Tips

1. 可以通过 `spm-server --livereload` 开启 livereload 模式

