---
title: "POI 的使用"
date: 2019-07-17T21:37:24+08:00
categories: ["Development"]
tags: ["Backend Framework"]
---

## 简介

{{< card "https://www.learnfk.com/apache-poi-word/apache-poi-word-tutorial.html" >}}

> Apache POI 是一种流行的 API，允许程序员使用 Java 程序创建，修改和显示 MS Office 文件。 它是由 Apache Software Foundation 开发和分发的开源库，用于使用 Java 程序设计或修改 Microsoft Office 文件。 它包含将用户输入数据或文件解码为 MS Office 文档的类和方法。

## 扩展

### 替代方案

#### Easyexcel

{{< card "https://easyexcel.opensource.alibaba.com/docs/current/" >}}

#### Hutool-poi

{{< card title="Hutool-poi是针对Apache POI的封装" description="Java针对MS Office的操作的库屈指可数，比较有名的就是Apache的POI库。这个库异常强大，但是使用起来也并不容易。Hutool针对POI封装一些常用工具，使Java操作Excel等文件变得异常简单。" url="https://www.hutool.cn/docs/#/poi/%E6%A6%82%E8%BF%B0" >}}

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
