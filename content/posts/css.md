---
title: "CSS 知识总结"
date: 2019-07-17T22:54:08+08:00
categories: ["Development"]
tags: ["Language"]
---

## 简介

> 定义：层叠样式表(英文全称：Cascading Style Sheets)是一种用来表现 HTML（标准通用标记语言的一个应用）或 XML（标准通用标记语言的一个子集）等文件样式的计算机语言。  
> 产生原因：单用 HTML 写出的页面显示的难看。

{{< card "http://css.doyoe.com/" >}}

## 常用样式

### 字体

- font-family : 字体类型
- font-size : 字体大小

### 文本

- color : 颜色
- line-height : 行高
- text-align : 对齐
- text-shadow : 设置文字阴影

### 显示和隐藏

- display
  - none : 隐藏不占位
  - block : 块显示
  - inline : 行内显示
- visibility
  - hidden : 隐藏占位
  - visible : 显示
- opactity : 设置透明度

### 尺寸

- width : 设置宽度(屏幕自适应宽度 100%)
- height : 设置高度
- max-width
- min-width
- max-height
- min-height

### 定位

- position
  - absolute : 绝对定位(释放文档流中的位置，第一个定位的父标签左上角是原点)
  - relative : 相对定位(不释放文档流中的位置，自己是原点)
  - fixed : 固定定位
- left : 设置左侧距原点的长度
- top : 设置上方的距原点的长度
- right : 设置右侧距原点的长度
- bottom : 设置底部距原点的距离
- z-index : 定义 z 轴高度(不设置为 0)
- vertical-align : 设置元素的垂直对齐方式。

### 内外边距

- margin-top : 上部外边距
- margin-right : 右侧外边距
- margin-bottom : 底部外边距
- margin-left : 左侧外边距
- margin(缩写) : 全部、上下/左右、上/左右/下、上/右/下/左
- padding-top : 上部内边距
- padding-right : 右侧内边距
- padding-bottom : 底部内边距
- padding-left : 左侧内边距
- padding(缩写) : 全部、上下/左右、上/左右/下、上/右/下/左

### 浮动和清除浮动

- float : 设置浮动(只能在浮动之前文档流中的位置的往左或往右浮动)
- clear : 清除浮动(如果一个盒子里的 div 都浮动，就要在添加一个清除浮动的 div 把盒子的位置撑开)

### 背景

- background-color : 背景颜色
- background-image : 背景图片
- background-repeat : 背景图是否重复
- background-attachment : 背景图片是否固定
- background-position : 背景图片定位(可以使用%和 px 值和英语单词)
- background(缩写形式) : #ccc url('xxx.png') no-repeat fixed 50% 50%
- background-size : 设置背景图片的尺寸
- background-origin : 设置背景图的位置(padding-box\border-box\content-box)

### 边框

- border-width : 边框粗细
- border-style : 边框样式
- border-color : 边框颜色
- border(缩写形式) : 1px solid #ccc
- border-left : 左侧边框
- border-top : 顶部边框
- border-right : 右侧边框
- border-bottom : 底部边框
- border-radius : 设置圆角
- box-shadow : 设置阴影

### 鼠标

- cursor : 改变鼠标样式(text\pointer\default\wait\help\crosshair)

### 表格

- border-collapse : 表格边框是否合并
- border-spacing : 表格边框之间的距离

### 滚动条

- overflow : 设置滚动条状态(hidden、auto、scroll)

## 选择符

### 元素选择符

- 通配选择符

```css
* {
  color: #f00;
}
```

- 类型选择符

```css
p {
  font-size: 13px;
}
```

- ID 选择符

```css
#id {
  color: #f00;
}
```

- 类选择符

```css
.className {
  color: #f00;
}
```

### 关系选择符

- 包含选择符

```css
ul li {
  color: #f00;
}
```

- 子选择符

```css
.test > li > a {
  color: #f00;
}
```

- 相邻选择符

```css
p + p {
  color: #f00;
}
```

- 兄弟选择符

```css
h3 ~ p {
  color: #f00;
}
```

### 属性选择符

| 选择符           | 描述                                                                                                       |
| ---------------- | ---------------------------------------------------------------------------------------------------------- |
| E[att]           | 选择具有 att 属性的 E 元素。                                                                               |
| E[att = "val"]   | 选择具有 att 属性且属性值等于 val 的 E 元素。                                                              |
| E[att ~= "val"]  | 选择具有 att 属性且属性值为一用空格分隔的字词列表，其中一个等于 val 的 E 元素。                            |
| E[att ^= "val"]  | 选择具有 att 属性且属性值为以 val 开头的字符串的 E 元素。                                                  |
| E[att $= "val"]  | 选择具有 att 属性且属性值为以 val 结尾的字符串的 E 元素。                                                  |
| E[att \*= "val"] | 选择具有 att 属性且属性值为包含 val 的字符串的 E 元素。                                                    |
| E[att \|= "val"] | 选择具有 att 属性且属性值为以 val 开头并用连接符"-"分隔的字符串的 E 元素，如果属性值仅为 val，也将被选择。 |

### 伪类选择符

<table>
	<thead>
		<tr>
			<th>选择符</th>
			<th>版本</th>
			<th>描述</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>E:link</td>
			<td>CSS1</td>
			<td>设置超链接a在未被访问前的样式。</td>
		</tr>
		<tr>
			<td>E:visited</td>
			<td>CSS1</td>
			<td>设置超链接a在其链接地址已被访问过时的样式。</td>
		</tr>
		<tr>
			<td>E:hover</td>
			<td>CSS1/2</td>
			<td>设置元素在其鼠标悬停时的样式。</td>
		</tr>
		<tr>
			<td>E:active</td>
			<td>CSS1/2</td>
			<td>设置元素在被用户激活（在鼠标点击与释放之间发生的事件）时的样式。</td>
		</tr>
		<tr>
			<td>E:focus</td>
			<td>CSS1/2</td>
			<td>设置元素在成为输入焦点（该元素的onfocus事件发生）时的样式。</td>
		</tr>
		<tr>
			<td>E:first-child</td>
			<td>CSS2</td>
			<td>匹配父元素的第一个子元素E。</td>
		</tr>
		<tr>
			<td>E:last-child</td>
			<td>CSS3</td>
			<td>匹配父元素的最后一个子元素E。</td>
		</tr>
		<tr>
			<td>E:only-child</td>
			<td>CSS3</td>
			<td>匹配父元素仅有的一个子元素E。</td>
		</tr>
		<tr>
			<td>E:nth-child(n)</td>
			<td>CSS3</td>
			<td>匹配父元素的第n个子元素E。</td>
		</tr>
		<tr>
			<td>E:empty</td>
			<td>CSS3</td>
			<td>匹配没有任何子元素（包括text节点）的元素E。</td>
		</tr>
		<tr>
			<td>E:checked</td>
			<td>CSS3</td>
			<td>匹配用户界面上处于选中状态的元素E。(用于input type为radio与checkbox时)</td>
		</tr>
		<tr>
			<td>E:disabled</td>
			<td>CSS3</td>
			<td>匹配用户界面上处于禁用状态的元素E。</td>
		</tr>
	</tbody>
</table>

### 伪对象选择符

| 选择符          | 描述                                                                        |
| --------------- | --------------------------------------------------------------------------- |
| E::first-letter | 设置对象内的第一个字符的样式。                                              |
| E::first-line   | 设置对象内的第一行的样式。                                                  |
| E::before       | 设置在对象前（依据对象树的逻辑结构）发生的内容。用来和 content 属性一起使用 |
| E::after        | 设置在对象后（依据对象树的逻辑结构）发生的内容。用来和 content 属性一起使用 |
| E::placeholder  | 设置对象文字占位符的样式。                                                  |
| E::selection    | 设置对象被选择时的颜色。                                                    |

## 扩展

### 交互式游戏化教程

{{< card "https://flukeout.github.io/" >}}

### Flex 布局

{{< card title="Flex 布局语法篇" url="https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html" description="2009年，W3C 提出了一种新的方案----Flex 布局，可以简便、完整、响应式地实现各种页面布局。目前，它已经得到了所有浏览器的支持，这意味着，现在就能很安全地使用这项功能。" >}}

网页布局（layout）是 CSS 的一个重点应用。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071001.gif)

布局的传统解决方案，基于[盒状模型](https://developer.mozilla.org/en-US/docs/Web/CSS/box_model)，依赖 [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) 属性 + [`position`](https://developer.mozilla.org/en-US/docs/Web/CSS/position)属性 + [`float`](https://developer.mozilla.org/en-US/docs/Web/CSS/float)属性。它对于那些特殊布局非常不方便，比如，[垂直居中](https://css-tricks.com/centering-css-complete-guide/)就不容易实现。

2009 年，W3C 提出了一种新的方案----Flex 布局，可以简便、完整、响应式地实现各种页面布局。目前，它已经得到了所有浏览器的支持，这意味着，现在就能很安全地使用这项功能。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071003.jpg)

Flex 布局将成为未来布局的首选方案。本文介绍它的语法，[下一篇文章](https://www.ruanyifeng.com/blog/2015/07/flex-examples.html)给出常见布局的 Flex 写法。网友 [JailBreak](http://vgee.cn/) 为本文的所有示例制作了 [Demo](http://static.vgee.cn/static/index.html)，也可以参考。

以下内容主要参考了下面两篇文章：[A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) 和 [A Visual Guide to CSS3 Flexbox Properties](https://scotch.io/tutorials/a-visual-guide-to-css3-flexbox-properties)。

#### 一、Flex 布局是什么？

Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。

任何一个容器都可以指定为 Flex 布局。

> ```css
> .box {
>   display: flex;
> }
> ```

行内元素也可以使用 Flex 布局。

> ```css
> .box {
>   display: inline-flex;
> }
> ```

Webkit 内核的浏览器，必须加上`-webkit`前缀。

> ```css
> .box {
>   display: -webkit-flex; /* Safari */
>   display: flex;
> }
> ```

注意，设为 Flex 布局以后，子元素的`float`、`clear`和`vertical-align`属性将失效。

#### 二、基本概念

采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)

容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。

项目默认沿主轴排列。单个项目占据的主轴空间叫做`main size`，占据的交叉轴空间叫做`cross size`。

#### 三、容器的属性

以下 6 个属性设置在容器上。

> - flex-direction
> - flex-wrap
> - flex-flow
> - justify-content
> - align-items
> - align-content

##### 3.1 flex-direction 属性

`flex-direction`属性决定主轴的方向（即项目的排列方向）。

> ```css
> .box {
>   flex-direction: row | row-reverse | column | column-reverse;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071005.png)

它可能有 4 个值。

> - `row`（默认值）：主轴为水平方向，起点在左端。
> - `row-reverse`：主轴为水平方向，起点在右端。
> - `column`：主轴为垂直方向，起点在上沿。
> - `column-reverse`：主轴为垂直方向，起点在下沿。

##### 3.2 flex-wrap 属性

默认情况下，项目都排在一条线（又称"轴线"）上。`flex-wrap`属性定义，如果一条轴线排不下，如何换行。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071006.png)

> ```css
> .box {
>   flex-wrap: nowrap | wrap | wrap-reverse;
> }
> ```

它可能取三个值。

（1）`nowrap`（默认）：不换行。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071007.png)

（2）`wrap`：换行，第一行在上方。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071008.jpg)

（3）`wrap-reverse`：换行，第一行在下方。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071009.jpg)

##### 3.3 flex-flow

`flex-flow`属性是`flex-direction`属性和`flex-wrap`属性的简写形式，默认值为`row nowrap`。

> ```css
> .box {
>   flex-flow: <flex-direction> || <flex-wrap>;
> }
> ```

##### 3.4 justify-content 属性

`justify-content`属性定义了项目在主轴上的对齐方式。

> ```css
> .box {
>   justify-content: flex-start | flex-end | center | space-between |
>     space-around;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071010.png)

它可能取 5 个值，具体对齐方式与轴的方向有关。下面假设主轴为从左到右。

> - `flex-start`（默认值）：左对齐
> - `flex-end`：右对齐
> - `center`： 居中
> - `space-between`：两端对齐，项目之间的间隔都相等。
> - `space-around`：每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。

##### 3.5 align-items 属性

`align-items`属性定义项目在交叉轴上如何对齐。

> ```css
> .box {
>   align-items: flex-start | flex-end | center | baseline | stretch;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071011.png)

它可能取 5 个值。具体的对齐方式与交叉轴的方向有关，下面假设交叉轴从上到下。

> - `flex-start`：交叉轴的起点对齐。
> - `flex-end`：交叉轴的终点对齐。
> - `center`：交叉轴的中点对齐。
> - `baseline`: 项目的第一行文字的基线对齐。
> - `stretch`（默认值）：如果项目未设置高度或设为 auto，将占满整个容器的高度。

##### 3.6 align-content 属性

`align-content`属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

> ```css
> .box {
>   align-content: flex-start | flex-end | center | space-between | space-around
>     | stretch;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071012.png)

该属性可能取 6 个值。

> - `flex-start`：与交叉轴的起点对齐。
> - `flex-end`：与交叉轴的终点对齐。
> - `center`：与交叉轴的中点对齐。
> - `space-between`：与交叉轴两端对齐，轴线之间的间隔平均分布。
> - `space-around`：每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。
> - `stretch`（默认值）：轴线占满整个交叉轴。

#### 四、项目的属性

以下 6 个属性设置在项目上。

> - `order`
> - `flex-grow`
> - `flex-shrink`
> - `flex-basis`
> - `flex`
> - `align-self`

##### 4.1 order 属性

`order`属性定义项目的排列顺序。数值越小，排列越靠前，默认为 0。

> ```css
> .item {
>   order: <integer>;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071013.png)

##### 4.2 flex-grow 属性

`flex-grow`属性定义项目的放大比例，默认为`0`，即如果存在剩余空间，也不放大。

> ```css
> .item {
>   flex-grow: <number>; /* default 0 */
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071014.png)

如果所有项目的`flex-grow`属性都为 1，则它们将等分剩余空间（如果有的话）。如果一个项目的`flex-grow`属性为 2，其他项目都为 1，则前者占据的剩余空间将比其他项多一倍。

##### 4.3 flex-shrink 属性

`flex-shrink`属性定义了项目的缩小比例，默认为 1，即如果空间不足，该项目将缩小。

> ```css
> .item {
>   flex-shrink: <number>; /* default 1 */
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071015.jpg)

如果所有项目的`flex-shrink`属性都为 1，当空间不足时，都将等比例缩小。如果一个项目的`flex-shrink`属性为 0，其他项目都为 1，则空间不足时，前者不缩小。

负值对该属性无效。

##### 4.4 flex-basis 属性

`flex-basis`属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为`auto`，即项目的本来大小。

> ```css
> .item {
>   flex-basis: <length> | auto; /* default auto */
> }
> ```

它可以设为跟`width`或`height`属性一样的值（比如 350px），则项目将占据固定空间。

##### 4.5 flex 属性

`flex`属性是`flex-grow`, `flex-shrink` 和 `flex-basis`的简写，默认值为`0 1 auto`。后两个属性可选。

> ```css
> .item {
>   flex: none | [ < "flex-grow" > < "flex-shrink" >? || < "flex-basis" > ];
> }
> ```

该属性有两个快捷值：`auto` (`1 1 auto`) 和 none (`0 0 auto`)。

建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。

##### 4.6 align-self 属性

`align-self`属性允许单个项目有与其他项目不一样的对齐方式，可覆盖`align-items`属性。默认值为`auto`，表示继承父元素的`align-items`属性，如果没有父元素，则等同于`stretch`。

> ```css
> .item {
>   align-self: auto | flex-start | flex-end | center | baseline | stretch;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071016.png)

该属性可能取 6 个值，除了 auto，其他都与 align-items 属性完全一致。

{{< card title="Flex 布局实例篇" description="你会看到，不管是什么布局，Flex往往都可以几行命令搞定。" url="https://www.ruanyifeng.com/blog/2015/07/flex-examples.html" >}}

[上一篇文章](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)介绍了 Flex 布局的语法，今天介绍常见布局的 Flex 写法。

你会看到，不管是什么布局，Flex 往往都可以几行命令搞定。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071327.png)

我只列出代码，详细的语法解释请查阅[《Flex 布局教程：语法篇》](https://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)。我的主要参考资料是[Landon Schropp](https://davidwalsh.name/flexbox-dice)的文章和[Solved by Flexbox](https://philipwalton.github.io/solved-by-flexbox/)。

#### 一、骰子的布局

骰子的一面，最多可以放置 9 个点。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071328.png)

下面，就来看看 Flex 如何实现，从 1 个点到 9 个点的布局。你可以到[codepen](https://codepen.io/LandonSchropp/pen/KpzzGo)查看 Demo。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071329.png)

如果不加说明，本节的 HTML 模板一律如下。

> ```markup
> <div class="box">
>   <span class="item"></span>
> </div>
> ```

上面代码中，div 元素（代表骰子的一个面）是 Flex 容器，span 元素（代表一个点）是 Flex 项目。如果有多个项目，就要添加多个 span 元素，以此类推。

##### 1.1 单项目

首先，只有左上角 1 个点的情况。Flex 布局默认就是首行左对齐，所以一行代码就够了。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071301.png)

> ```css
> .box {
>   display: flex;
> }
> ```

设置项目的对齐方式，就能实现居中对齐和右对齐。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071302.png)

> ```css
> .box {
>   display: flex;
>   justify-content: center;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071303.png)

> ```css
> .box {
>   display: flex;
>   justify-content: flex-end;
> }
> ```

设置交叉轴对齐方式，可以垂直移动主轴。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071304.png)

> ```css
> .box {
>   display: flex;
>   align-items: center;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071305.png)

> ```css
> .box {
>   display: flex;
>   justify-content: center;
>   align-items: center;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071306.png)

> ```css
> .box {
>   display: flex;
>   justify-content: center;
>   align-items: flex-end;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071307.png)

> ```css
> .box {
>   display: flex;
>   justify-content: flex-end;
>   align-items: flex-end;
> }
> ```

##### 1.2 双项目

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071308.png)

> ```css
> .box {
>   display: flex;
>   justify-content: space-between;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071309.png)

> ```css
> .box {
>   display: flex;
>   flex-direction: column;
>   justify-content: space-between;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071310.png)

> ```css
> .box {
>   display: flex;
>   flex-direction: column;
>   justify-content: space-between;
>   align-items: center;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071311.png)

> ```css
> .box {
>   display: flex;
>   flex-direction: column;
>   justify-content: space-between;
>   align-items: flex-end;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071312.png)

> ```css
> .box {
>   display: flex;
> }
>
> .item:nth-child(2) {
>   align-self: center;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071313.png)

> ```css
> .box {
>   display: flex;
>   justify-content: space-between;
> }
>
> .item:nth-child(2) {
>   align-self: flex-end;
> }
> ```

##### 1.3 三项目

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071314.png)

> ```css
> .box {
>   display: flex;
> }
>
> .item:nth-child(2) {
>   align-self: center;
> }
>
> .item:nth-child(3) {
>   align-self: flex-end;
> }
> ```

##### 1.4 四项目

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071315.png)

> ```css
> .box {
>   display: flex;
>   flex-wrap: wrap;
>   justify-content: flex-end;
>   align-content: space-between;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071316.png)

HTML 代码如下。

> ```markup
> <div class="box">
>   <div class="column">
>     <span class="item"></span>
>     <span class="item"></span>
>   </div>
>   <div class="column">
>     <span class="item"></span>
>     <span class="item"></span>
>   </div>
> </div>
> ```

CSS 代码如下。

> ```css
> .box {
>   display: flex;
>   flex-wrap: wrap;
>   align-content: space-between;
> }
>
> .column {
>   flex-basis: 100%;
>   display: flex;
>   justify-content: space-between;
> }
> ```

##### 1.5 六项目

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071317.png)

> ```css
> .box {
>   display: flex;
>   flex-wrap: wrap;
>   align-content: space-between;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071318.png)

> ```css
> .box {
>   display: flex;
>   flex-direction: column;
>   flex-wrap: wrap;
>   align-content: space-between;
> }
> ```

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071319.png)

HTML 代码如下。

> ```markup
> <div class="box">
>   <div class="row">
>     <span class="item"></span>
>     <span class="item"></span>
>     <span class="item"></span>
>   </div>
>   <div class="row">
>     <span class="item"></span>
>   </div>
>   <div class="row">
>      <span class="item"></span>
>      <span class="item"></span>
>   </div>
> </div>
> ```

CSS 代码如下。

> ```css
> .box {
>   display: flex;
>   flex-wrap: wrap;
> }
>
> .row {
>   flex-basis: 100%;
>   display: flex;
> }
>
> .row:nth-child(2) {
>   justify-content: center;
> }
>
> .row:nth-child(3) {
>   justify-content: space-between;
> }
> ```

##### 1.6 九项目

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071320.png)

> ```css
> .box {
>   display: flex;
>   flex-wrap: wrap;
> }
> ```

#### 二、网格布局

##### 2.1 基本网格布局

最简单的网格布局，就是平均分布。在容器里面平均分配空间，跟上面的骰子布局很像，但是需要设置项目的自动缩放。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071321.png)

HTML 代码如下。

> ```markup
> <div class="Grid">
>   <div class="Grid-cell">...</div>
>   <div class="Grid-cell">...</div>
>   <div class="Grid-cell">...</div>
> </div>
> ```

CSS 代码如下。

> ```css
> .Grid {
>   display: flex;
> }
>
> .Grid-cell {
>   flex: 1;
> }
> ```

##### 2.2 百分比布局

某个网格的宽度为固定的百分比，其余网格平均分配剩余的空间。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071322.png)

HTML 代码如下。

> ```markup
> <div class="Grid">
>   <div class="Grid-cell u-1of4">...</div>
>   <div class="Grid-cell">...</div>
>   <div class="Grid-cell u-1of3">...</div>
> </div>
> ```

> ```css
> .Grid {
>   display: flex;
> }
>
> .Grid-cell {
>   flex: 1;
> }
>
> .Grid-cell.u-full {
>   flex: 0 0 100%;
> }
>
> .Grid-cell.u-1of2 {
>   flex: 0 0 50%;
> }
>
> .Grid-cell.u-1of3 {
>   flex: 0 0 33.3333%;
> }
>
> .Grid-cell.u-1of4 {
>   flex: 0 0 25%;
> }
> ```

#### 三、圣杯布局

[圣杯布局](<https://en.wikipedia.org/wiki/Holy_Grail_(web_design)>)（Holy Grail Layout）指的是一种最常见的网站布局。页面从上到下，分成三个部分：头部（header），躯干（body），尾部（footer）。其中躯干又水平分成三栏，从左到右为：导航、主栏、副栏。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071323.png)

HTML 代码如下。

> ```markup
> <body class="HolyGrail">
>   <header>...</header>
>   <div class="HolyGrail-body">
>     <main class="HolyGrail-content">...</main>
>     <nav class="HolyGrail-nav">...</nav>
>     <aside class="HolyGrail-ads">...</aside>
>   </div>
>   <footer>...</footer>
> </body>
> ```

CSS 代码如下。

> ```css
> .HolyGrail {
>   display: flex;
>   min-height: 100vh;
>   flex-direction: column;
> }
>
> header,
> footer {
>   flex: 1;
> }
>
> .HolyGrail-body {
>   display: flex;
>   flex: 1;
> }
>
> .HolyGrail-content {
>   flex: 1;
> }
>
> .HolyGrail-nav,
> .HolyGrail-ads {
>   /* 两个边栏的宽度设为12em */
>   flex: 0 0 12em;
> }
>
> .HolyGrail-nav {
>   /* 导航放到最左边 */
>   order: -1;
> }
> ```

如果是小屏幕，躯干的三栏自动变为垂直叠加。

> ```css
> @media (max-width: 768px) {
>   .HolyGrail-body {
>     flex-direction: column;
>     flex: 1;
>   }
>   .HolyGrail-nav,
>   .HolyGrail-ads,
>   .HolyGrail-content {
>     flex: auto;
>   }
> }
> ```

#### 四、输入框的布局

我们常常需要在输入框的前方添加提示，后方添加按钮。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071324.png)

HTML 代码如下。

> ```markup
> <div class="InputAddOn">
>   <span class="InputAddOn-item">...</span>
>   <input class="InputAddOn-field">
>   <button class="InputAddOn-item">...</button>
> </div>
> ```

CSS 代码如下。

> ```css
> .InputAddOn {
>   display: flex;
> }
>
> .InputAddOn-field {
>   flex: 1;
> }
> ```

#### 五、悬挂式布局

有时，主栏的左侧或右侧，需要添加一个图片栏。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071325.png)

HTML 代码如下。

> ```markup
> <div class="Media">
>   <img class="Media-figure" src="" alt="">
>   <p class="Media-body">...</p>
> </div>
> ```

CSS 代码如下。

> ```css
> .Media {
>   display: flex;
>   align-items: flex-start;
> }
>
> .Media-figure {
>   margin-right: 1em;
> }
>
> .Media-body {
>   flex: 1;
> }
> ```

#### 六、固定的底栏

有时，页面内容太少，无法占满一屏的高度，底栏就会抬高到页面的中间。这时可以采用 Flex 布局，让底栏总是出现在页面的底部。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071326.png)

HTML 代码如下。

> ```markup
> <body class="Site">
>   <header>...</header>
>   <main class="Site-content">...</main>
>   <footer>...</footer>
> </body>
> ```

CSS 代码如下。

> ```css
> .Site {
>   display: flex;
>   min-height: 100vh;
>   flex-direction: column;
> }
>
> .Site-content {
>   flex: 1;
> }
> ```

#### 七，流式布局

每行的项目数固定，会自动分行。

![img](https://www.ruanyifeng.com/blogimg/asset/2015/bg2015071330.png)

CSS 的写法。

> ```css
> .parent {
>   width: 200px;
>   height: 150px;
>   background-color: black;
>   display: flex;
>   flex-flow: row wrap;
>   align-content: flex-start;
> }
>
> .child {
>   box-sizing: border-box;
>   background-color: white;
>   flex: 0 0 25%;
>   height: 50px;
>   border: 1px solid red;
> }
> ```

### 几种颜色的表示方式

- 英语表示
- 十进制表示 : rgb();
- 十六进制表示 : #000000;
- 带透明度十进制 : rgba();

## 应用场景

### sup 标签导致行距变大的问题

#### 问题描述

使用 `<sup>` 标签时，行距变大。

#### 产生原因

`<sup>` 标签可定义上标文本，HTML 默认的上标样式实现是会影响行高的。

#### 解决方式

```css
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
  top: -0.5em;
}
```
