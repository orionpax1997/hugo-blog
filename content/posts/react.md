---
title: "React 的使用"
date: 2019-07-23T21:45:22+08:00
tags: ["Frontend Framework"]
featuredImage: "https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Development/react-banner.3b3ttc6ic9q0.webp"
---

## 快速入门

{{< card "https://zh-hans.react.dev/learn" >}}

## 应用场景

### 如何解决 JAX 中 HTML 代码段被识别为字符串的问题?

#### 问题描述

React 的 JAX 语法中进行动态数据绑定时不能动态绑定 HTML。

#### 产生原因

JAX 的设计者，在设计时为了防止 XSS 攻击，特意限制了。

#### 解决方式

```JSX
//使用dangerouslySetInnerHTML(注意__html是两个_)
<div dangerouslySetInnerHTML={{__html: html}} />
```

> 不合时宜的使用 innerHTML 可能会导致 cross-site scripting (XSS) 攻击。 净化用户的输入来显示的时候，经常会出现错误，不合适的净化也是导致网页攻击的原因之一。我们的设计哲学是让确保安全应该是简单的，开发者在执行“不安全”的操作的时候应该清楚地知道他们自己的意图。dangerouslySetInnerHTML 这个 prop 的命名是故意这么设计的，以此来警告，它的 prop 值（ 一个对象而不是字符串 ）应该被用来表明净化后的数据。

### 如何处理 React 和直接修改 DOM 的前端框架的兼容性问题?

#### 问题描述

因为 React 的状态到虚拟 DOM 再到 DOM 绘制的框架实现和通过 JQuery 去直接修改 DOM 是有冲突的。所以如果使用了 React 框架的话，最好就不要再使用会直接修改 DOM 的 JQuery 框架。

##### React 和 JQuery UI Sortable

- 产生原因:  
  使用 Sortable 进行拖拽排序时，在放置时 Sortable 会先根据拖拽起始和目标修改一次 DOM。然后如果在拖拽后更新了数据，React 会 render DOM，但是 React 并不知道 Sortable 对 DOM 进行了修改，因此产生的冲突。

- 解决方式:  
  在 stop 回调方法里取消 Sortable 的排序，将排序操作交给 React 管理。

  ```JSX
  stop: function () {
      $schArLiBox.sortable("cancel");
  }
  ```

##### React 和 JQuery tipsy

- 产生原因:  
  React 修改 title 后，如果是置为`""`或删除 title 属性，都不会另 tipsy 重新加载
  original-title 属性，只有修改为其他值是才重加载。因此要删除的话就有问题。

- 解决方式:  
  使用 jQuery 手动删除修改的元素的 original-title 属性
