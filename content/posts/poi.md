---
title: "POI 的使用"
date: 2019-07-17T21:37:24+08:00
categories: ["Development"]
tags: ["Backend Framework"]
---

## 简介

> Apache POI 是一种流行的 API，允许程序员使用 Java 程序创建，修改和显示 MS Office 文件。 它是由 Apache Software Foundation 开发和分发的开源库，用于使用 Java 程序设计或修改 Microsoft Office 文件。 它包含将用户输入数据或文件解码为 MS Office 文档的类和方法。

## 基础

{{< card "https://iowiki.com/apache_poi/apache_poi_quick_guide.html" >}}
{{< card "https://juejin.cn/post/6844903733004894221" >}}

## 应用场景

### POI 单元格数据过长如何处理？

#### 问题描述

POI 单元格数据过长报错。

#### 报错信息

```
java.lang.IllegalArgumentException: The maximum column width for an individual cell is 255 characters.
```

#### 产生原因

导出 excel 时，excel 表中的某个单元格数据过大，然而在创建时，使用了`localHSSFSheet.setColumnWidth()`控制住了单元格的列宽，所以会显示单元格最大列宽 255 错误。

#### 解决方式

```java
if(colWidth<255*256){
    sheet.setColumnWidth(i, colWidth < 3000 ? 3000 : colWidth);
}else{
    sheet.setColumnWidth(i, 65000);
}
```
