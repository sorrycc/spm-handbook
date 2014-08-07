# 一个简单的单页应用


## 目标

1. 通过 [normalize.css](https://github.com/necolas/normalize.css) 进行 css reset
1. 通过 jQuery 在页面上输出 `hello world`

## Demo

![](http://gtms04.alicdn.com/tps/i4/TB1Ger3FVXXXXb.XpXXpOKi7VXX-759-425.gif)


## 目录初始化

```bash
$ mkdir spm-project
$ cd spm-project
$ yo spm
```

```bash
[?] Project Name: spm project
[?] Project Version: 0.1.0
[?] Include Mode: standalone
[?] Dependencies: normalize.css jquery
[?] Project Type: simple
   create package.json
   create index.css
   create index.js
   create index.html

        install: normalize.css@stable
          fetch: normalize.css@stable
        extract: ~/.spm/cache/normalize.css-3.0.1.tar.gz
      installed: sea-modules/normalize.css/3.0.1
     deps saved: normalize.css@3.0.1
        install: jquery@stable
          fetch: jquery@stable
        extract: ~/.spm/cache/jquery-2.1.1.tar.gz
      installed: sea-modules/jquery/2.1.1
     deps saved: jquery@2.1.1
```

生成出来的目录结构如下：

```
- index.html
- index.css
- index.js
- package.json
```


## 开发

编辑 `index.js`

```javascript
var $ = require('jquery');
$('body').append('<div>Hello World!</div>');
```

编辑 `index.css`

```css
@import 'normalize.css';
```


## 调试

```bash
$ spm-server
```

```bash
         server: listen on 8000
```

浏览器会自动打开 http://localhost:8000 。


## 部署/发布

1. 执行 `spm build`
1. 部署/发布 `index.html` 和 `dist` 目录

## Tips

1. 可以通过 `spm-server --livereload` 开启 livereload 模式
1. html 里引用 css/js 时可以是源码路径 `./index.js`, 也可以是构建后的路径 `./dist/{{name}}/{{version}}/index.js`。通过 spm-server 调试时，构建后的路径会被代理到源码路径上。

