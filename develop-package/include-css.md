# 引入 CSS

> 以下方法同样适用于相对的 CSS 文件。

spmjs.io 上有不少 CSS 组件，比如 [normalize.css](http://spmjs.io/package/normalize.css) 和 [bootstrap.css](http://spmjs.io/package/bootstrap.css) 。

可以通过两种方法来引入他们：

1. css 文件里 `@import`
1. js 文件里 `@require`

## CSS 文件里 `@import`

```css
@import 'b';
```

构建时会合并依赖的 CSS 组件。

## js 文件里 `@require`

```javascript
@require 'b';
```

构建时：

1. 转化 css 文件为 cmd 模块
1. 自动安装 [import-style](http://spmjs.io/package/import-style) 并保存到 `spm/dependencies`



