---
title: "Node.js 的使用"
date: 2019-09-23T17:11:43+08:00
categories: ["Development"]
tags: ["Environment"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/nodejs-banner.6rfb93mmq280.webp"
---

## 简介

> Node.js 是一个基于 Chrome V8 引擎的 JavaScript 运行环境。 Node.js 使用了一个事件驱动、非阻塞式 I/O 的模型，使其轻量又高效。

{{< card "https://nodejs.dev/learn/introduction-to-nodejs" >}}

## 安装

{{< card "https://nodejs.dev/download/" >}}
{{< card "https://nodejs.dev/download/package-manager/" >}}

## 基础

### 您需要了解多少 JavaScript 才能使用 Node.js？

{{< card "https://nodejs.dev/learn/how-much-javascript-do-you-need-to-know-to-use-nodejs" >}}

### 从命令行运行 Node.js 脚本

{{< card "https://nodejs.dev/learn/run-nodejs-scripts-from-the-command-line" >}}

### 使用 Node.js 输出到命令行

{{< card "https://nodejs.dev/learn/output-to-the-command-line-using-nodejs" >}}

### 错误处理

{{< card "https://nodejs.dev/learn/error-handling-in-nodejs" >}}

### Node 模块系统

#### 概述

> Node.js 采用模块化结构，按照 CommonJS 规范定义和使用模块。模块与文件是一一对应关系，即加载一个模块，实际上就是加载对应的一个模块文件。

{{< card "https://nodejs.dev/learn/expose-functionality-from-a-nodejs-file-using-exports" >}}
{{< card "https://blog.csdn.net/zhangyuan19880606/article/details/51508699" >}}

#### 什么是模块化？

- 存在文件作用域
- 存在通信规则
  - 加载(require)
  - 导出(module.exports)

#### 导出 `exports`

node 中每个 js 文件，都有一个 module 对象，其 exports 属性相当于其暴露的接口对象。可以使用`module.exports.xxx = xxx`添加向外暴露的接口。如果一个文件只向外暴露一个方法或者其他类型的属性，可以直接使用`module.exports = xxx`。注意在 Node 解释 js 文件时，会在其头部加上隐式的`let exports = module.exports`因此只要不改变指针指向的情况下，可以使用`export`代替`module.exports`。

#### 加载 `require`

- 加载规则
  - 会执行加载模块中的代码
  - 重复 require，不会执行模块中的代码，仅能拿到`module.exports`接口对象。
- 模块标识
  - 核心模块
    - 被编译到二进制文件中，直接使用名字加载。
  - 第三方模块
    - 凡是第三方模块都需要使用 npm 来下载
    - 加载的时候使用`require(’packageName’)`
    - 加载的文件的位置在`node_modules/packageName/package.json` 中`{”main”:”加载文件“}`
    - 没有配置加载文件的情况会默认为`index.js`
    - `node_modules`文件夹会从当前文件所在路径，向上迭代查找使用最近的一个。
  - 自定义模块
    - `./`开头，代表当前路径,不可省。
    - `../`开头，代表上级路径,不可省。
    - 引入时`.js`后缀可省

### npm 包管理器

{{< card "https://nodejs.dev/learn/an-introduction-to-the-npm-package-manager" >}}
{{< card "https://nodejs.dev/learn/where-does-npm-install-the-packages" >}}
{{< card "https://nodejs.dev/learn/how-to-use-or-execute-a-package-installed-using-npm" >}}
{{< card "https://nodejs.dev/learn/find-the-installed-version-of-an-npm-package" >}}
{{< card "https://nodejs.dev/learn/uninstalling-npm-packages" >}}
{{< card "https://nodejs.dev/learn/npm-global-or-local-packages" >}}
{{< card "https://nodejs.dev/learn/npm-dependencies-and-devdependencies" >}}

### package.json 和 package-lock.json 指南

{{< card "https://nodejs.dev/learn/the-package-json-guide" >}}
{{< card "https://nodejs.dev/learn/the-package-lock-json-file" >}}

### 常用标准库

#### fs

{{< card "https://nodejs.dev/learn/the-nodejs-fs-module" >}}

#### path

{{< card "https://nodejs.dev/learn/the-nodejs-path-module" >}}

#### os

{{< card "https://nodejs.dev/learn/the-nodejs-os-module" >}}

#### events

{{< card "https://nodejs.dev/learn/the-nodejs-events-module" >}}

#### http

{{< card "https://nodejs.dev/learn/the-nodejs-http-module" >}}

#### Buffers

{{< card "https://nodejs.dev/learn/nodejs-buffers" >}}

#### Streams

{{< card "https://nodejs.dev/learn/nodejs-streams" >}}

## 扩展

### 其他包管理器

#### Yarn

{{< card "https://yarn.bootcss.com/docs/getting-started" >}}

#### pnpm

{{< card "https://pnpm.io/zh/installation" >}}

### 如何在 Node.js 中接受来自命令行的输入

{{< card "https://nodejs.dev/learn/accept-input-from-the-command-line-in-nodejs" >}}

### npx 包运行器

{{< card "https://nodejs.dev/learn/the-npx-nodejs-package-runner" >}}

### 事件轮询

{{< card "https://nodejs.dev/learn/the-nodejs-event-loop" >}}
{{< card "https://nodejs.dev/learn/understanding-process-nexttick" >}}
{{< card "https://www.php.cn/js-tutorial-408369.html" >}}

### 异步编程

{{< card "https://nodejs.dev/learn/javascript-asynchronous-programming-and-callbacks" >}}
{{< card "https://nodejs.dev/learn/understanding-javascript-promises" >}}
{{< card "https://nodejs.dev/learn/modern-asynchronous-javascript-with-async-and-await" >}}
{{< card "https://nodejs.dev/learn/the-nodejs-event-emitter" >}}

### 构建 HTTP 服务器

{{< card "https://nodejs.dev/learn/build-an-http-server" >}}
{{< card "https://nodejs.dev/learn/get-http-request-body-data-using-nodejs" >}}

### 发出 HTTP 请求

{{< card "https://nodejs.dev/learn/making-http-requests-with-nodejs" >}}

### 文件读写

{{< card "https://nodejs.dev/learn/nodejs-file-stats" >}}
{{< card "https://nodejs.dev/learn/nodejs-file-paths" >}}
{{< card "https://nodejs.dev/learn/reading-files-with-nodejs" >}}
{{< card "https://nodejs.dev/learn/writing-files-with-nodejs" >}}
{{< card "https://nodejs.dev/learn/working-with-folders-in-nodejs" >}}

### 如何在 Node.js 中打印对象

{{< card "https://nodejs.dev/learn/how-to-log-an-object-in-nodejs" >}}

### Node.js 最佳实践

{{< card "https://github.com/i0natan/nodebestpractices/blob/master/README.chinese.md" >}}
