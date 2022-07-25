---
title: "Google Chrome 的使用"
date: 2022-02-25T08:40:21+08:00
categories: ["Geek"]
tags: ["Tool"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/chrome-banner.3gw9yc1adf60.webp"
---

## 简介

Google Chrome 是一款由 Google 公司开发的网页浏览器，该浏览器基于其他开源软件撰写，包括 WebKit，目标是提升稳定性、速度和安全性，并创造出简单且有效率的使用者界面。

## 插件

### 开发

{{< card "https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd" >}}
{{< card "https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi" >}}

### 生产力

{{< card "https://saladict.crimx.com/" >}}
{{< card "https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa" >}}

### 折腾

{{< card "https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo" >}}
{{< card "https://chrome.google.com/webstore/detail/gfbliohnnapiefjpjlpjnehglfpaknnc" >}}
{{< card "https://github.com/xifangczy/cat-catch" >}}

## 应用场景

### Chrome 您的连接不是私密连接解决办法

#### **问题描述**

最近 chrome 版本移除了关于 ssl 配置错误后，点高级没有继续访问的选项。

#### **解决办法**

解决办法就是在当前页面用键盘输入  `thisisunsafe` ，不是在地址栏输入，就直接敲键盘就行了，页面即会自动刷新进入网页。

#### 参考

{{< card "https://stackoverflow.com/questions/35274659/when-you-use-badidea-or-thisisunsafe-to-bypass-a-chrome-certificate-hsts-err" >}}
{{< card url="https://chromium.googlesource.com/chromium/src/+/d8fc089b62cd4f8d907acff6fb3f5ff58f168697%5E%21/#F0" title="Rotate the interstitial bypass keyword" description="The security interstitial bypass keyword hasn't changed in two years and awareness of the bypass has been increased in blogs and social media. Rotate the keyword to help prevent misuse." >}}
