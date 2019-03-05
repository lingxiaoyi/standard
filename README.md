# 前端团队规范

## 背景

- 前端团队不断的壮大；
- 项目越来越多、业务越来越复杂；
- 前端管理、维护越来越困难。

## 目的

提升前端团队开发效率，降低前端团队维护成本。

## 开发工具

- **[VsCode（必须）](https://code.visualstudio.com/)**
- Sublime Text（[CN](http://www.sublimetextcn.com/) [EN](https://www.sublimetext.com/)）
- [Atom](https://atom.io/)

## 开发环境：

- [node（下载最新 lts 版本）](https://nodejs.org/en/)（**请使用 nvm 来管理 node 版本：[nvm for windows](https://github.com/coreybutler/nvm-windows#node-version-manager-nvm-for-windows)、[nvm for mac & linux](https://github.com/creationix/nvm)**）
- [npm](https://github.com/npm/cli)（一般随 node 一起安装）
- [git](https://git-scm.com/)

## 编码规范

**请直接按照此教程来配置代码开发规范：** [VsCode 开发环境配置规范](./vscode_eslint_prettier.md)

如发现下面列出的规范与上面 VsCode 配置的规范有冲突，以上面配置的为准。

1. [git 规范](./git.md)
2. [目录和命名规范](./dir.md)
3. [HTML 编码规范](./html.md)
4. [CSS 编码规范](./css.md)
5. [JavaScript 编码规范 1](./javascript.md) - ~~[JavaScript 编码规范 2](./js.md)~~
6. [README 文件规范](./project_readme.md)
7. [上线规范](./online.md)
8. ~~[测试服使用规范](./server.md)~~

## 公共 js 库

针对公司业务整理的公共 js 库（未经过全面测试验证，有问题可以提工单或提合并请求参与维护）：

- [shfe-lib](http://codeio.dftoutiao.com/RESEARCH/shfe-lib/src/master/README.md)：适用于 H5 和 APP 开发，PC 不考虑兼容低版本浏览器也可以使用。
- [public-lib](http://codeio.dftoutiao.com/DFTTPC/public-lib/src/master/README.md): 适用于 PC 开发。

## 附

- [MarkDown 语法学习](./markdown.md)
- [前端工具集](./tools.md)
