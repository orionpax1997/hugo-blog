---
title: "IntelliJ IDEA 的使用"
date: 2021-03-24T17:40:56+08:00
categories: ["Development"]
tags: ["Tool"]
---

## 简介

> IntelliJ IDEA 主要用于支持 Java、Scala、Groovy 等语言的开发工具，同时具备支持目前主流的技术和框架，擅长于企业应用、移动应用和 Web 应用的开发。

## 安装

mac 下执行 `brew install intellij-idea`。

## 配置

{{< card "https://cdk8s.gitbook.io/github/" >}}

## 插件

### Official

{{< card "https://plugins.jetbrains.com/plugin/164-ideavim" >}}
{{< card "https://plugins.jetbrains.com/plugin/13360-ideavim-easymotion" >}}

### Beautification

{{< card "https://plugins.jetbrains.com/plugin/11938-one-dark-theme" >}}
{{< card "https://plugins.jetbrains.com/plugin/10080-rainbow-brackets" >}}

### **Productivity**

{{< card "https://plugins.jetbrains.com/plugin/10046-alibaba-java-coding-guidelines" >}}
{{< card "https://plugins.jetbrains.com/plugin/10119-mybatisx" >}}
{{< card "https://plugins.jetbrains.com/plugin/4441-jrebel-and-xrebel/" >}}
{{< card "https://plugins.jetbrains.com/plugin/12682-jrebel-mybatisplus-extension" >}}

### Others

{{< card "https://gitee.com/pengzhile/ide-eval-resetter" >}}

## 问题

### M**ac 下 IDEA 运行项目慢问题**

#### 问题描述

Spring Boot 项目使用 Mac 电脑启动很慢，但是使用 Windows 电脑启动就很快。

#### 产生原因

很有可能是项目中有识别主机名称的代码，需要更改您 Mac 的电脑名称。

#### 解决方式

`hostname` 查看自己的主机名称， `sudo vim /etc/hosts` 修改 host 文件 `127.0.0.1 localhost` 后添加主机名称

![idea-1](https://cdn.statically.io/gh/orionpax1997/picx-images-hosting@master/Development/idea-1.xs1ogs9e1ps.webp)

{{< card "https://www.cnblogs.com/ontoweb-zp/p/10855386.html" >}}
{{< card url="https://youtrack.jetbrains.com/issue/IDEA-161967" title="Freezes after saving caches when debugger connects on macOS Sierra" description="Freezes for about 9 seconds when performing Finished. Saving caches (see the attached screenshot and log). I noticed nothing obviously abnormal in the log. In fact, the freeze happens AFTER the last line of the log. This problem only shows up when Debugging, and does not show up when Running.">}}

## 参考

{{< card "https://github.com/judasn/IntelliJ-IDEA-Tutorial" >}}
{{< card url="https://zhile.io/2021/11/29/ja-netfilter-javaagent-lib.html" title="介绍一个牛逼闪闪开源库：ja-netfilter" description="上来先说点题外话，很多人最新私信我说我的开源项目IDE Eval Resetter不好用了。我就问他为什么不好用了，不好编译了吗？他说不是，是不能在IDE上重置了。我心说，这是个学习研究项目，重在学习插件写法，不能用也实在属于正常。于是我去测试了一下，得出了个结论：2021.2.2及以下版本很好用；2021.3以下（不含）堪堪能用，需要配合一些手法；2021.3版本开始正式失效，你可以卸载这个插件了！">}}
