
# 新手入门

## 介绍

[spm](https://github.com/spmjs/spm) 是一套完整的浏览器端组件管理解决方案，包含对于 JavaScript、CSS 和模板的处理。

![SPM LOGO](https://i.alipayobjects.com/i/localhost/png/201404/2YQxOTYoFp.png)

所有 `spmjs.io` 上的组件都是以 CommonJS 的方式组织，并通过 [Sea.js](https://github.com/seajs/seajs) 运行的。同时，我们基于 [spm](https://github.com/spmjs/spm) 提供了一套完整的组件生命周期管理方案，包含以下特性：

- 初始化
- 依赖安装
- 本地开发
- 发布到 [spmjs.io](http://spmjs.io/)
- 单元测试
- 文档服务
- 构建

[spmjs.io](http://spmjs.io/) 是针对 spm 的组件管理服务。你可以在这里搜索需要的组件，也可以发布组件到这里。

## 安装

```bash
$ npm install spm -g
```

> `npm install spm@2.x -g` for old spm2.

## 基本操作

初始化组件：

```bash
$ mkdir example
$ cd example
$ spm init
```

安装依赖：

```bash
$ spm install jquery --save
$ spm install moment@2.6.0 --save
```

发布到 [spmjs.io](http://spmjs.io/)

```bash
$ spm publish
```

> 你可能需要先执行 `spm login` 来获取权限，登录 [spmjs.io](http://spmjs.io) 之后在 http://spmjs.io/account 可以找到 `authkey`。

如果组件包的尺寸过大，可以添加 `.spmignore` 来过滤掉不需要的文件。

## 贡献

欢迎通过以下方式来贡献 spm ：

- [Bug reports](https://github.com/spmjs/spm/issues)
- [Feature requests](https://github.com/spmjs/spm/issues)
- [Pull requests](https://github.com/spmjs/spm/pulls)
- 推广 spm 到你的朋友圈
