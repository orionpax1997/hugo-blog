---
title: "Element UI 组件库的使用"
date: 2021-06-24T17:29:38+08:00
categories: ["Development"]
tags: ["Frontend Framework"]
featuredImage: "https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/element-ui-banner.5l10skpow6c0.webp"
---

## 简介

Element，一套为开发者、设计师和产品经理准备的基于 Vue 3.0 的桌面端组件库

{{< card "https://element-plus.gitee.io/zh-CN/" >}}

## 问题

### DatePicker 组件生成 input 和 Input 、Select 组件生成的 input 在设置宽度 100%后，宽度不一致的问题

#### 问题描述

DatePicker 组件生成 input 和 Input 、Select 组件生成的 input 在设置宽度 100%后，宽度不一致

#### 产生原因

DatePicker 组件生成的 input 在前面会有一个小图标，默认的样式 `padding-left: 30px` ，而不带图标的 input 的默认样式为 `padding-left: 15px` ，因此当单纯的设置 `width: 100%` 会导致 input 宽度不同。

![element-ui-1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/element-ui-1.khwlgr2x9t8.webp)
![element-ui-2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/element-ui-2.4wpdqmphikq0.webp)

#### 解决方式

`el-date-picker` 设置样式 `style="width:100%;margin-right:-15px"`
