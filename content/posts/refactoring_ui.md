---
title: "《Refactoring UI》读书笔记"
date: 2022-12-28T11:05:02+08:00
categories: ["Development"]
tags: ["Frontend Framework"]
---

如果你从事网站设计工作，请帮自己一个忙，买这本书。

{{< card "https://www.refactoringui.com/" >}}

## 从头开始

### 从一个功能开始，而不是布局

当你开始设计一个新的应用创意时，你首先设计什么？如果它是页面顶部的导航栏，那你就错了。

在进行新设计时发现自己感到沮丧和卡住的最简单方法是从尝试“设计应用程序”开始。当大多数人想到“设计应用程序”时，他们想到的是布局。

_它应该有一个顶部导航，还是一个侧边栏？_

_导航项应该在左边还是右边？_

_页面内容应该放在一个容器中，还是应该是全角的？徽标应该放在哪里？_

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7f9mg4ze11g0.webp)

问题是，“应用程序”实际上是功能的集合。在设计一些功能之前，您甚至没有决定导航应该如何工作所需的信息。难怪令人沮丧！

不要从布局开始，而是从一个实际的功能开始。

例如，假设您正在构建航班预订服务。您可以从“搜索航班”等功能开始。

您的界面将需要：

- 出发城市字段
- 目的地城市的字段
- 出发日期字段
- 返回日期字段
- 一个执行搜索的按钮

从那开始。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.21i1fdwsxw9s.webp)

见鬼，你甚至可能不需要其他东西——它适用于谷歌。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.39iwzh3ox8g0.webp)

### 细节稍后出现

在设计新功能的最初阶段，重要的是你不要在字体、阴影、图标等方面做出低级决定。

这些东西最终都会很重要，但现在并不重要。

如果您在浏览器或您最喜欢的设计工具等高保真环境中工作时无法忽略细节，basecamp 的 jason fried 喜欢使用的一个技巧是使用厚锐利的纸在纸上进行设计。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.522v3c9h5o40.webp)

使用 sharpie 不可能专注于小细节，因此它可能是快速探索一系列不同布局想法的好方法。

#### 保持颜色

即使您准备好以更高的保真度完善一个想法，也要抵制立即引入颜色的诱惑。

通过灰度设计，你不得不使用间距、对比度和大小来完成所有繁重的工作。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3oly11ca7480.webp)

这有点更具挑战性，但你最终会得到一个更清晰的界面和一个强大的层次结构，以后很容易用颜色来增强。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6uab0th7tao0.webp)

#### 不要过度投资

低保真设计的全部意义在于能够快速移动，这样你就可以尽快开始构建真实的东西。

草图和线框是一次性的——用户不能用静态模型做任何事情。用它们来探索您的想法，并在您做出决定后将它们抛在脑后。

### 不要设计太多

在继续实施之前，您无需设计应用程序中的每个功能；事实上，如果你不这样做会更好。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1q76pjynxtpc.webp)

弄清楚产品中的每个功能应该如何交互以及每个边缘情况应该如何看起来真的很难，尤其是在抽象的时候。

_如果用户有 2000 个联系人，这个屏幕应该如何显示？_

_这种形式的错误信息应该放在哪里？_

_当同时安排两个活动时，这个日历应该如何显示？_

如果您试图仅使用设计工具和您的想象力来解决这些问题，您就会感到沮丧。

#### 循环工作

与其预先设计所有内容，不如缩短工作周期。首先设计您要构建的下一个功能的简单版本。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6efwjuvc9nc0.webp)

一旦您对基本设计感到满意，就将其变为现实。

在此过程中，您可能会遇到一些意想不到的复杂性，但这就是重点——在您可以实际使用的界面中修复设计问题比提前想象每个边缘情况要容易得多。

迭代工作设计，直到没有更多问题需要解决，

然后跳回设计模式并开始处理下一个功能。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.58kiobrmyfg0.webp)

不要在抽象中不知所措。尽早构建真实的东西，这样您的想象力就不必承担所有繁重的工作。

#### 做一个悲观主义者

不要在你的设计中暗示你还没有准备好构建的功能。

例如，假设您正在为项目管理工具开发评论系统。您知道有一天，您希望用户能够将文件附加到他们的评论中，因此您在设计中包含了一个附件部分。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.305vgo6tnbq0.webp)

您深入实施后才发现支持附件的工作比您预期的要多得多。你现在没有时间完成它，所以当你处理其他优先事项时，整个评论系统都处于次要地位。

问题是，一个没有附件的评论系统仍然比没有评论系统要好，但是因为你从第一天起就计划包含它，所以你没有什么可以发布的。

当您设计一项新功能时，预计它很难构建。设计您可以交付的最小有用版本可以大大降低这种风险。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.539eekv6chc0.webp)

如果某项功能的一部分是“可有可无”，请稍后再进行设计。首先构建简单的版本，你总会有一些东西可以依靠。

### 选择个性

每个设计都有某种个性。银行网站可能会尝试以安全和专业的方式进行交流，而时尚的新创业公司可能会采用让人感觉有趣和好玩的设计。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1fwv2shhkts0.webp)

从表面上看，为设计赋予特定的个性可能听起来抽象而随意，但其中很多是由一些坚实、具体的因素决定的。

#### 字体选择

排版在决定设计的感觉方面起着重要作用。

如果你想要优雅或经典的外观，你可能想在你的设计中加入衬线字体：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.55myr3r5ab40.webp)

如果想要俏皮的外观，您可以使用圆形的无衬线字体：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6051akhs8380.webp)

如果你想要更朴素的外观，或者想依靠其他元素来提供个性，中性无衬线字体效果很好：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2yi3tsooj9o0.webp)

#### 颜色

有很多关于颜色心理学的科学，但在实践中，你真的只需要注意不同颜色对你的感觉。

蓝色是安全和熟悉的——没有人抱怨蓝色：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1uhyzg9luexs.webp)

黄金可能会说“昂贵”和“复杂”：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.623xhatxs2o0.webp)

粉红色更有趣一点，而且不那么严肃：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6sws1bdmyp80.webp)

虽然尝试仅使用心理学来选择颜色并不是很实用——其中很多只是关于你看起来好看的颜色——当你试图理解为什么你认为一种颜色是合适的时候，思考一下会很有帮助.

#### 圆角

就像听起来的细节一样小，如果你在你的设计中转角以及转角的多少会对整体感觉产生很大的影响。

一个小的圆角是非常中性的，并没有真正传达出太多的个性：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4aucxfst7eq0.webp)

大圆角开始感觉更有趣：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6sg1fq5rvcc0.webp)

…虽然完全没有圆角感觉更严肃或正式：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3qxxnt8sr320.webp)

无论您选择什么，保持一致很重要。在同一个界面中混合方角和圆角几乎总是比坚持使用其中一种更糟糕。

#### 语言

虽然本质上不是一种视觉设计技术，但您在界面中使用的文字对整体个性有着巨大的影响。

使用不那么个人化的语气可能会让人感觉更正式或更专业：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6x28wb3v80g0.webp)

……使用更友好、更随意的语言会让网站感觉更友好：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6y8s7jpk4x80.webp)

文字在用户界面中无处不在，选择正确的文字与选择正确的颜色或字体一样重要（如果不是更重要的话）。

#### 决定你真正想要什么

很多时候你可能只是对你想要的个性有一种直觉。但如果您不这样做，简化决定的一个好方法是查看想要访问的人使用的其他站点。

如果它们大多是非常“严肃的业务”，那么也许您的网站也应该如此。如果他们更幽默一点，也许这是一个更好的方向。

尽量不要从直接竞争对手那里借鉴太多，你不想看起来像其他东西的二流版本。

#### 限制你的选择

拥有数百万种颜色和数千种字体可供选择在理论上听起来不错，但在实践中这通常是一个令人瘫痪的诅咒。

不仅是字体和颜色——你很容易浪费时间在几乎所有次要的设计决定上苦苦思索。

_此文本应该是 12px 还是 13px？_

_这个盒子阴影应该有 10% 的不透明度还是 15% 的不透明度？_

_这个头像应该是 24px 还是 25px 高？_

_我应该为这个按钮使用中等字体粗细还是半粗体？_

_这个标题的底边距应该是 18 像素还是 20 像素？_

当你在不受限制的情况下进行设计时，决策是一种折磨，因为总是会有不止一个正确的选择。

例如，这些按钮都有不同的背景颜色，但仅靠观察几乎无法分辨它们之间的区别。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.19pc2rttq1u.webp)

如果这些都不是真正糟糕的选择，您应该如何做出自信的决定？

#### 提前定义规范

与其在需要做出决定时从无限的池中手动挑选值，不如从较小的选项集开始。

每次需要选择新的蓝色阴影时，不要伸手去拿颜色选择器——从提前挑选的一组 8-10 种颜色中选择。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2205ni8sq0o0.webp)

同样，不要一次调整一个像素的字体大小，直到它看起来完美为止。提前定义一个限制性的字体比例，并使用它来做出任何未来的字体大小决定。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.vxdx9wbu0cg.webp)

当你构建这样的规范时，你只需要做一次艰难的选择初始值的工作，而不是每次你设计一个新的用户界面时。前期的工作要多一些，但这是值得的——它会为你省去大量的决策疲劳。

#### 淘汰法设计

当您使用一组受约束的值进行设计时，决策制定会容易得多，因为“正确”的选择要少得多。

例如，假设您正在尝试为图标选择大小。你已经预先定义了一个尺寸比例，你唯一的中小型尺寸选项是 12px、16px、24px 和 32px。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5r0npe02gtc0.webp)

要选择最佳选项，首先要猜测哪个看起来最好，也许是 16px。然后尝试比较两侧的值（12px 和 24px）。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.ooumxpgtry8.webp)

很有可能，其中两个选项看起来显然是错误的选择。如果是外面的选项，你就完了——中间的选项是唯一好的选择。

如果其中一个外部选项看起来最好，则使用该选项作为“中间”值进行另一次比较，并确保没有更好的选择。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6ovcib1vsgo0.webp)

这种方法适用于您定义系统的任何地方。当您被限制在一组看起来都明显不同的选项时，选择最好的一个是小菜一碟。

#### 规范化一切

您拥有的规范越多，您的工作速度就越快，您对自己的决定进行二次猜测的次数就越少。

你会想要这样的规范：

- Font size
- Font weight
- Line height
- Color
- Margin
- Padding
- Width
- Height
- Box shadows
- Border radius
- Border width
- Opacity

......以及任何其他你遇到的感觉就像你在为一个低层次的设计决策而努力的地方。

您不必提前定义所有这些东西，只需确保您以规范为中心的思维方式进行设计即可。在做出新决定时寻找引入新系统的机会，并尽量避免必须两次做出相同的小决定。

使用系统进行设计将是贯穿本书的一个反复出现的主题，在后面的章节中，我们将更详细地讨论构建许多这样的系统。

## 层次就是一切

### 并非所有元素都相等

当您将视觉设计视为“为事物设计样式以使其看起来不错”时，很容易理解为什么如果没有先天的艺术天赋就很难实现。但事实证明，使某物“看起来不错”的最大因素之一与表面造型完全无关。

视觉层次是指界面中的元素相对于彼此的重要性，它是让某些东西感觉“经过设计”的最有效工具。

当界面中的所有内容都在争夺注意力时，会让人感觉嘈杂和混乱，就像一堵内容的大墙，不清楚真正重要的是什么：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3qxqkldg7d00.webp)

当你故意不强调次要和第三级信息，并努力突出最重要的元素时，结果会立即更令人愉悦，即使配色方案、字体选择和布局没有改变：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.67q9uii7t1k0.webp)

那么您实际上是如何做到这一点的呢？在接下来的章节中，我们将介绍一些可用于将层次结构引入设计的具体策略。

### 尺寸不是一切

过分依赖字体大小来控制层次结构是一个错误——它通常会导致主要内容太大，而次要内容太小。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5tgl4jd9wqc0.webp)

与其将所有繁重的工作都留给字体大小，不如尝试使用字体粗细或颜色来完成同样的工作。

例如，使主要元素更粗可以让您使用更多

合理的字体大小，并且通常在传达其重要性方面做得更好：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2vgm477men40.webp)

类似地，使用更柔和的颜色来支持文本而不是很小的字体大小可以清楚地表明文本是次要的，同时牺牲更少的可读性：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1d38xxxs4hsw.webp)

尝试坚持两种或三种颜色：

- 主要内容的深色（如文章的标题）
- 灰色表示次要内容（如文章发表日期）
- 浅灰色用于第三级内容（可能是页脚中的版权声明）

同样，两个字体粗细通常足以用于 ui 工作：

- 大多数文本的正常字体粗细（400 或 500，具体取决于字体）
- 为您想要强调的文本提供较重的字体粗细（600 或 700）

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7c7jgvw1qyg0.webp)

远离 400 以下的字体重量用于 ui 工作——它们可以用于大标题，但在较小的尺寸下太难阅读。如果你正在考虑

使用较轻的字重来淡化某些文本，请改用较浅的颜色或较小的字体大小。

### 不要在彩色背景上使用灰色文本

将文本设为浅灰色是在白色背景上弱化它的好方法，但在彩色背景上看起来就不那么好了。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1tvwyyh51dmo.webp)

那是因为我们实际看到的白色灰色效果是降低了对比度。

使文本更接近背景颜色实际上有助于创建层次结构，而不是使其变成浅灰色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6y0pjkwvr1k0.webp)

您可能认为实现此目的的最简单方法是使用白色文本并降低不透明度：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.57zqqr5hufk0.webp)

虽然这确实会降低对比度，但它通常会导致文本看起来暗淡、褪色，有时甚至无法显示。

更糟糕的是，在图像或图案之上使用这种方法意味着背景将通过文本显示出来：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5bq4qq02c8w.webp)

更好的方法是根据背景颜色手动选择一种新颜色。

选择具有相同色调的颜色，并调整饱和度和亮度，直到它看起来适合您：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.16936khl6hog.webp)

以这种方式手工挑选颜色可以轻松降低对比度，而不会使文本看起来褪色。

### 通过去强调来强调

有时你会遇到这样一种情况，界面的主要元素不够突出，但你也无法添加任何东西来赋予它所需的重点。

例如，尽管试图通过给它一个不同的颜色来使这个活动的导航项目“流行”，但与非活动项目相比它仍然没有真正脱颖而出：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4lbo8gs049i0.webp)

当你遇到这样的情况时，与其试图进一步强调你想要引起注意的元素，不如想办法淡化与之竞争的元素。

在此示例中，您可以通过为非活动项目提供更柔和的颜色来做到这一点，以便它们更多地位于背景中：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4r79syhkrte0.webp)

您也可以将这种想法应用于更大的界面部分。

例如，如果侧边栏感觉它在与您的主要内容区域竞争，请不要给它一个背景颜色——让内容直接位于页面背景上：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4t9iieo3rug0.webp)

### 标签是最后的手段

放下可访问性干草叉——这与表单无关。

当向用户呈现数据（尤其是来自数据库的数据）时，很容易陷入使用天真的标签：值格式来显示它的陷阱。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.v3gc16fygcw.webp)

这种方法的问题在于，它很难以任何类型的层次结构呈现数据；每一条数据都被同等重视。

#### 你可能根本不需要标签

在很多情况下，你可以通过查看格式来判断一段数据是什么。

例如，janedoe@example.com 是电子邮件地址，_(555) 765-4321_ 是电话号码，_$19.99_ 是价格。

当格式不够时，上下文通常是。

当您在员工目录中看到某人姓名下方列出的短语“客户支持”时，

您无需标签即可将其与该人工作的部门联系起来。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.21eaq8bp7jds.webp)

当你能够在没有标签的情况下呈现数据时，强调重要或识别信息会容易得多，使界面更易于使用，同时让人感觉更“设计”。

#### 组合标签和值

即使在没有标签的情况下一段数据并不完全清楚，您通常可以通过向值添加澄清文本来避免添加标签。

例如，如果您需要在电子商务界面中显示库存，而不是“in stock: 12”，请尝试“12 left in stock”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3zz9d3phj100.webp)

如果你正在构建一个房地产应用程序，“卧室：3”之类的东西可以简单地变成“3 间卧室”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.25x24hhpcfhc.webp)

当您能够将标签和值组合成一个单元时，在不牺牲清晰度的情况下为每条数据赋予有意义的样式会容易得多。

#### 标签是次要的

有时你真的需要一个标签；例如，当您显示多条相似数据并且它们需要易于扫描时，就像在仪表板上一样。

在这些情况下，添加标签，但将其视为支持内容。数据本身很重要，标签只是为了清楚起见。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6huhphwzkjc0.webp)

通过缩小标签、降低对比度、使用较轻的字体粗细或三者的某种组合来弱化标签。

#### 何时强调标签

如果你正在设计一个你知道用户会寻找标签的界面，那么强调标签而不是数据可能是有意义的。

这通常出现在信息密集的页面上，例如产品的技术规格。

如果用户试图找出智能手机的尺寸，他们可能会在页面上扫描“深度”之类的词，而不是“7.6 毫米”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.63zh5bbufhc0.webp)

在这些场景中不要过分强调数据；这仍然是重要的信息。简单地为标签使用较深的颜色，为值使用稍浅的颜色通常就足够了。

### 将视觉层次结构与文档层次结构分开

在为网络构建时使用语义标记很重要，这意味着如果您决定向界面的一部分添加标题，您将经常使用标题标签，如 `h1`、`h2` 或 `h3`。

默认情况下，Web 浏览器为标题元素指定逐渐变小的字体大小，因此 `h1` 相当大，而 `h6` 非常小。这对于文章或文档等文档样式内容很有帮助，但它可能会在应用程序用户界面中鼓励做出一些错误的决定。

使用 `h1` 标签向页面添加诸如管理帐户之类的标题在语义上是完全合理的，但是因为我们被训练相信 `h1` 元素应该很大，所以很容易陷入使这些标题比实际需要更大的陷阱成为。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2u74goifzl40.webp)

很多时候，章节标题更像是标签而不是标题——它们是支持性的内容，它们不应该抢走所有的注意力。

通常该部分的内容应该是重点，而不是标题。这意味着很多时候，标题实际上应该很小：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.541ydah7edc0.webp)

在极端情况下，出于可访问性原因，您甚至可能在标记中包含部分标题，但在视觉上完全隐藏它们，因为内容不言而喻。

不要让你正在使用的元素影响你如何选择它的样式 - 出于语义目的选择元素并为它们设置样式，但是你需要创建最佳的视觉层次结构。

### 平衡重量和对比度

与普通文本相比，粗体文本给人以强调的原因是粗体文本覆盖了更多的表面积——在相同的空间量下，用于文本的像素多于用于背景的像素。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6maargzhj180.webp)

那么为什么这很有趣呢？事实证明，表面区域和层次结构之间的关系也对 UI 中的其他元素有影响。

#### 使用对比度来补偿重量

理解这种关系变得重要的地方之一是在使用图标时。

就像粗体文本一样，图标（尤其是实心图标）通常非常“重”并且覆盖了很多表面积。因此，当您将图标放在某些文本旁边时，该图标往往会让人感到被强调。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6llvocpp99c0.webp)

与文本不同，没有办法改变图标的 “重量”，因此为了创造平衡，需要以其他方式弱化它。

一个简单而有效的方法是通过给它一个柔和的颜色来降低图标的对比度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5tpg5dntfn40.webp)

这适用于您需要平衡具有不同权重的元素的任何地方。降低对比度就像一种平衡，即使重量没有改变，也会让较重的元素感觉更轻。

#### 使用重量来补偿对比度

就像降低对比度有助于弱化重元素一样，增加权重是强调低对比度元素的好方法。

当像 1px 细边框这样的东西使用柔和的颜色太微妙时，这很有用，但是使颜色变暗会使设计感觉粗糙和嘈杂。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2m8771bgmay0.webp)

通过增加宽度使边框更重一点有助于强调它而不会失去更柔和的外观：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4hrkkpacyqa0.webp)

### 语义是次要的

当用户可以在一个页面上执行多个操作时，很容易陷入纯粹基于语义来设计这些操作的陷阱。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6wzl6utmzb40.webp)

语义是按钮设计的重要组成部分，但这并不意味着您可以忘记层次结构。

页面上的每个动作都位于重要性金字塔中的某个位置。大多数页面只有一个真正的主要动作，一些不太重要的次要动作，以及一些很少使用的三级动作。

在设计这些动作时，重要的是要传达它们在层次结构中的位置。

- **主要行动应该是显而易见的。** 纯色、高对比度的背景颜色在这里效果很好。
- **次要动作应该清晰但不突出。** 轮廓样式或较低对比度的背景颜色是不错的选择。
- **三级动作应该是可发现的但不引人注目。** 将这些操作设置为链接样式通常是最好的方法。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4t4vwrnffok0.webp)

当您采用层次结构优先的方法来设计页面上的操作时，结果是一个不那么繁忙的用户界面，可以更清晰地传达信息：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6r97hnr27d80.webp)

#### 破坏性行为

具有破坏性或高严重性并不自动意味着按钮应该是大的、红色的和粗体的。

如果破坏性操作不是页面上的主要操作，则最好对其进行二级或三级按钮处理。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2g63obskrzpc.webp)

将此与破坏性操作实际上是主要操作的确认步骤相结合，并在此处应用大红色粗体样式。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.19gony184d1c.webp)

## 布局和间距

### 从太多的空白开始

清理设计的最简单方法之一就是简单地给每个元素多一点呼吸空间。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7hvy9w8bflk0.webp)

听起来很简单，对吧？那么为什么我们通常不这样做呢？

#### 应删除而不是添加空格

在为网络设计时，空白几乎总是添加到设计中

如果某些东西看起来有点太局促，您可以添加一些边距或填充，直到看起来更好。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4n330vxp3440.webp)

这种方法的问题在于，元素只被给予了最少的呼吸空间，以免看起来很糟糕。为了使某些东西看起来真的很棒，您通常需要更多的空白空间。

更好的方法是先给某物留出太多空间，然后将其移除，直到您对结果满意为止。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3gapo82u7dm0.webp)

您可能会认为这样最终会留下太多空白，但实际上，当专注于单个元素时看起来“有点太多”，但在完整的用户界面。

#### 密集的用户界面有它们的位置

虽然有很多呼吸空间的界面几乎总是感觉更干净、更简单，但在某些情况下，设计更紧凑是有意义的。

例如，如果您正在设计某种需要同时显示大量信息的仪表板，那么将这些信息打包在一起以使其全部显示在一个屏幕上可能值得让设计感觉更加忙碌。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.38q5xjminf20.webp)

重要的是让这成为一个深思熟虑的决定，而不仅仅是默认。当你需要删除空格时比你需要添加它时要明显得多。

### 建立间距和尺寸规范

当你试图决定 ui 中元素的完美尺寸时，你不应该在 120px 和 125px 之间挑剔。

痛苦地一次一个像素地尝试任意值，最好的情况下会大大降低你的速度，最坏的情况下会创建丑陋、不一致的设计。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.55dpjtpwiz40.webp)

相反，将自己限制在一组预先定义的约束值中。

#### 线性刻度不起作用

创建间距和大小调整系统并不像“确保所有内容都是 4px 的倍数”那样简单——像这样天真的方法不会让在 120px 和 125px 之间做出选择变得更容易。

对于一个真正有用的规范，它需要考虑相邻值之间的相对差异。

在尺度的小端（比如图标的大小，或按钮内的填充），几个像素可以产生很大的不同。从 12px 跳到 16px 是增加了 33%！

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7jr3rgz8eak0.webp)

但在大端（卡片的宽度，或着陆页英雄的垂直间距），几个像素基本上是不可察觉的。即使将卡片的宽度从 500px 增加到 520px 也只有 4% 的差异，这比从 12px 增加到 16px 的差异小八倍。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6le76tnsp340.webp)

如果您希望您的系统更容易做出规模调整决策，请确保您的规模中没有两个值接近 25%。

#### 定义规范

就像您不想在调整元素大小时或微调元素之间的空间时费力处理任意值一样，您也不想从任意值构建间距和大小比例。

一个简单的方法是从一个合理的基值开始，然后使用该值的因数和倍数建立一个比例。

16px 是一个很好的开始数字，因为它很好地划分，而且恰好是每个主要网络浏览器的默认字体大小。

规模较小端的值应该开始时非常紧凑，随着规模的进一步扩大，它们之间的距离会逐渐变大。

这是一个使用这种方法构建的相当实用的规模的例子：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.20ja5aawjxq8.webp)

#### 使用规范

一旦你定义了你的间距和大小规范，你会发现你能够更快地设计，特别是如果你在浏览器中设计（当你输入数字时坚持一个规范更容易比你用鼠标拖动时。）

需要在元素下添加一些空间？从您的秤中获取一个值并尝试一下。还不够？下一个值可能是完美的。

虽然工作流程的改进可能是最大的好处，但您也会开始注意到您的设计中以前没有的微妙的一致性，并且看起来会更干净一些。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3s4rlvns3iw0.webp)

间距和大小调整规范将帮助您以更少的精力和更短的时间创建更好的设计。设计建议没有比这更有价值的了。

### 你不必填满整个屏幕

还记得 960px 是桌面尺寸设计的实际布局宽度吗？现在你很难找到分辨率这么低的手机。

因此，当我们大多数人在高分辨率显示器上打开我们选择的设计工具时，我们给自己至少 1200-1400 像素的空间来填充也就不足为奇了。但仅仅因为您有空间，并不意味着您需要使用它。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.okbkwmk8940.webp)

如果你只需要 600px，就使用 600px。将事物展开或使事物变得不必要地宽只会使界面更难理解，而边缘周围的一点额外空间不会伤害任何人。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.560jeegdk9c.webp)

这也适用于界面的各个部分。你不需要因为其他东西（比如你的导航）是全角的就把所有的东西都变成全角的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4zvi27dtxj40.webp)

只给每个元素它需要的空间——不要为了让它与其他东西相匹配而让事情变得更糟。

#### 缩小画布

如果您在大画布上设计小界面时遇到困难，请缩小画布！很多时候，当约束真实存在时，设计一些小东西会更容易。

如果你正在构建响应式 Web 应用程序，请尝试从 ~400px 画布开始并首先设计移动布局。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5bxtr1mzi1o0.webp)

一旦你有了一个你满意的移动设计，把它带到一个更大的屏幕上，并调整任何在小屏幕上感觉妥协的东西。很可能您不必像您想象的那样做出太多改变。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4sew3we6pbe0.webp)

#### 专栏思考

如果你正在设计的东西在较窄的宽度下效果最好，但在其他较宽的 UI 环境中感觉不平衡，看看你是否可以将它分成几列，而不是仅仅让它变宽。

例如，采用这种窄格式布局：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.52lroc3a1940.webp)

如果您想更好地利用可用空间而不会使表单更难使用，您可以将支持文本分成一个单独的列：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.677d9iomtlk0.webp)

这使设计感觉更加平衡和一致，而不会影响表单本身的最佳宽度。

#### 不要强迫它

就像你不应该担心填满整个屏幕一样，你也不应该不必要地把所有东西都塞进一个小区域。

如果你需要很大的空间，那就去吧！如果不需要，就不要觉得有义务填写它。

### 网格被高估了

使用像 12 列网格这样的系统是简化布局决策的好方法，并且可以为您的设计带来令人满意的秩序感。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6exfibl3ntc0.webp)

但是即使网格很有用，将所有布局决策外包给网格也弊大于利。

#### 并非所有元素都应该是流动的

从根本上说，网格系统只是为元素提供流动的、基于百分比的宽度，您可以从一组受限的百分比中进行选择。

例如，在 12 列网格中，每列的宽度为 8.33%。只要元素的宽度是 8.33% 的倍数（包括任何间距），该元素就“在网格上”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3l8589so1ug0.webp)

将网格系统视为一种宗教的问题在于，在很多情况下，元素具有固定宽度而不是相对宽度更有意义。

例如，考虑一个传统的侧边栏布局。使用 12 列的网格系统，您可以为侧边栏设置三列 (25%) 的宽度，将主要内容区域设置为九列 (75%) 的宽度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6a50qcmulc80.webp)

乍一看这似乎很好，但请想一想当您调整屏幕大小时会发生什么。

如果你把屏幕变宽，侧边栏也会变宽，占用了本可以被主要内容区域更好利用的空间。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1u05e5r08mhs.webp)

同样，如果您使屏幕变窄，侧边栏可能会缩小到其最小合理宽度以下，从而导致尴尬的文本换行或截断。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3no2nf5ucia0.webp)

在这种情况下，为侧边栏提供针对其内容优化的固定宽度更有意义。然后主要内容区域可以弯曲以填充剩余空间，使用其自己的内部网格来布置其子项。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6gpfked2szw0.webp)

这也适用于组件——除非你真的想让它缩放，否则不要使用百分比来调整大小。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.16w86rl3fqbg.webp)

#### 除非需要，否则不要收缩元素

假设您正在设计登录卡。使用全屏宽度看起来很难看，因此您将其宽度设置为 6 列 (50%)，每侧有 3 列偏移。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.302ixyclz5c0.webp)

在中等尺寸的屏幕上，您会发现卡片有点窄，即使您有足够的空间将其变大，因此在该屏幕尺寸下，您将其切换为 8 列的宽度，每侧有两个空列。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2t6eae62pga0.webp)

这种方法的愚蠢之处在于，因为列宽是可变的，所以屏幕尺寸有一个范围，其中登录卡在中等屏幕上比在大屏幕上更宽：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2r7wa3ksfxi0.webp)

如果你知道 500px 是卡片的最佳尺寸，那么如果你有足够的空间，为什么要让它变得更小呢？

不要像这样基于网格调整元素大小，而是给它们一个最大宽度，这样它们就不会变得太大，并且只有在屏幕小于最大宽度时才强制它们缩小。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.44jaua1u7x20.webp)

不要成为网格的奴隶——为您的组件提供它们需要的空间，并且在实际需要之前不要做出任何妥协。

### 相对大小不缩放

人们很容易相信界面的每一部分都应该相对于彼此调整大小，如果元素 a 需要在较小的屏幕上缩小 25%，那么元素 b 也应该缩小 25%。

例如，假设您正在设计一个大屏幕尺寸的文章。如果你的正文是 18px 而你的标题是 45px，很容易通过将你的标题大小定义为 2.5em 来编码这种关系；当前字体大小的 2.5 倍。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.673q3z149940.webp)

使用像 em 这样的相对单位本质上没有错，但不要误以为以这种方式定义的关系可以保持不变 2.5em 可能是桌面上完美的标题大小，但不能保证它在桌面上也是正确的大小较小的屏幕。

假设您在小屏幕上将正文大小减小到 14px 以控制行长。将标题保持在 2.5em 意味着呈现的字体大小为 35px——对于小屏幕来说太大了！

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2bkz7g5e6n9c.webp)

对于小屏幕，更好的标题大小可能介于 20 像素和 24 像素之间：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4ir7rabw9xu0.webp)

这只是 14px 正文大小的 1.5-1.7 倍——与桌面屏幕上的关系完全不同。这意味着根本没有任何真正的关系，并且尝试定义相对于正文大小的标题大小并没有真正的好处。

作为一般规则，大屏幕上的大元素需要比已经相当小的元素收缩得更快——在小屏幕尺寸下，小元素和大元素之间的差异应该不那么极端。

#### 元素内的关系

事物应该独立缩放的想法不仅仅适用于不同屏幕尺寸的元素；它也适用于单个组件的属性。

假设你设计了一个按钮。它的字体大小为 16px，水平填充为 16px，垂直填充为 12px：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6n9g80cfxu00.webp)

很像前面的例子，很容易认为填充应该根据当前字体大小来定义。这样如果你想要一个更大或更小的按钮，你只需要改变字体大小，填充就会自动更新，对吧？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.30hla6naq0y0.webp)

这是可行的——按钮会按比例放大或缩小并保持相同的比例。但这是我们真正想要的吗？

将其与这些按钮进行比较，其中填充在较大尺寸时变得更宽大，而在较小尺寸时不成比例地更紧：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6tocjxmiwp00.webp)

这里的大按钮实际上感觉是一个更大的按钮，而小按钮实际上感觉更小的按钮，而不是像我们简单地调整缩放。

放弃一切都需要按比例缩放的想法——让自己自由地独立微调事物，这使得针对多种环境进行设计变得容易得多。

### 避免歧义间距

当元素组明确分开时——通常是用边框或背景色——很明显哪些元素属于哪个组。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3gqyjrm58vc0.webp)

但是当没有可见的分隔符时，它并不总是那么明显。

假设您正在设计一个带有堆叠标签和输入的表单。如果标签下方的边距与输入下方的边距相同，则表单组中的元素不会明显“连接”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4nxwim33opi0.webp)

充其量，用户必须更加努力地解释用户界面，而最坏的情况是，这意味着不小心将错误的数据放在错误的字段中。

解决方法是增加每个表单组之间的空间，以便清楚哪个标签属于哪个输入：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.46u7hcnggc00.webp)

当章节标题上方没有足够的空间时，文章设计中也会出现同样的问题：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.56crgr54te80.webp)

...在项目符号列表中，当项目符号之间的间距与单个项目符号的行高匹配时：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6x2n2quw2qw0.webp)

您不仅要担心垂直间距；水平放置的组件也很容易犯这个错误：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3pkeob5d5z00.webp)

每当你依靠间距来连接一组元素时，请始终确保组周围的空间大于其中的空间——难以理解的界面总是看起来更糟。

## 设计文字

### 建立类型量表

大多数界面使用太多的字体大小。除非一个团队有一个严格的设计系统，否则经常会发现从 10px 到 24px 的每个像素值都被用在了 ui 的某个地方。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6wbux03wjbs0.webp)

在没有规范的情况下选择字体大小不是一个好主意，原因有二：

1. 它会导致你的设计中出现恼人的不一致。
2. 它减慢了您的工作流程。

那么如何定义类型规范呢？

#### 选择一个规模

就像间距和大小一样，线性刻度是行不通的。字体大小之间较小的跳跃在比例底部很有用，但你不想浪费时间在 46px 和 48px 之间决定一个大标题。

##### 模块化秤

一种方法是使用比例来计算字体比例，例如 4:5（“大三度”）、2:3（“完美五度”），或者也许是“黄金比例”，1:1.618。这通常被称为“模块化秤”。

你从一个合理的基值开始（16px 很常见，因为它是大多数浏览器的默认字体大小），应用你的比率以获得下一个值，然后将你的比率应用于该值以获得下一个值，依此类推:

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2amik6chubdw.webp)

这种方法的数学纯度很诱人，但在实践中，由于几个原因，它并不完美。

1.  **你最终得到的是分数值。**

    使用 16px 的基础和 4:5 的比例，你的比例最终会得到很多尺寸，这些尺寸不会恰好落在像素上，比如 31.25px、39.063px、48.828px 等。浏览器处理子像素舍入的方式都有点不同，所以如果可以避免，最好避免小数尺寸。

    如果您确实想使用这种方法，请确保在定义比例时自己对值进行四舍五入，以避免跨浏览器出现像素差一的问题。

2.  **您通常需要更多尺寸。**

    如果您为文章等长篇内容定义类型比例，这种方法会很有效，但对于界面设计，使用模块化比例获得的跳跃通常有点太局限了。

    使用（四舍五入的）3:4 字体比例，您可以得到 12px、16px、21px 和 28px 等大小。虽然从表面上看这似乎没有太多限制，但实际上您会希望大小介于 12px 和 16px 之间，而另一个介于 16px 和 21px 之间。

    您可以使用更严格的比例，例如 8:9，但此时您只是想选择一个恰好与您已知的尺寸相匹配的比例。

##### 手工制作的秤

对于界面设计，更实用的方法是简单地手动选择值。您不必担心这种方式的亚像素舍入误差，并且您可以完全控制存在哪些尺寸，而不是将该工作外包给某些数学公式。

这是一个适用于大多数项目的比例示例，并且与“建立间距和尺寸规范”中推荐的间距和尺寸比例很好地对齐：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6n7a8lqoln00.webp)

它的限制刚好足以加快您的决策速度，但又不会限制到让您觉得自己缺少有用的尺寸。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5omsq1b1pkg0.webp)

#### 避免 em 单位

当你建立字体比例时，不要使用 em 单位来定义你的尺寸。

因为 em 单位是相对于当前字体大小的，所以计算出的嵌套元素的字体大小通常不是您比例中的实际值。

例如，假设您定义了一个基于 em 的类型标度，如下所示：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.661f7xp9mm40.webp)

如果你给一个元素一个 1.25em 的字体大小（默认为 20px），在该元素内部 1em 现在等于 20px。这意味着，如果您给其中一个嵌套元素指定 .875em 的字体大小，则实际计算出的字体大小为 17.5px，而不是您的字体比例中的值！

坚持使用 px 或 rem 单位——这是保证你真正坚持使用系统的唯一方法。

### 使用好的字体

有成千上万种不同的字体可供选择，区分好的字体和坏的字体可能是一项艰巨的任务。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2b63yfq5rvy8.webp)

开发一个好的字体的所有细节可能需要数年时间。你可能没有多少年头了，所以这里有一些技巧可以让你立即开始挑选高质量的字体。

#### 谨慎行事

对于 ui 设计，你最安全的选择是相当中性的无衬线字体——想想像 helvetica 这样的字体。

如果您真的不相信自己的品味，一个不错的选择是依赖系统字体堆栈：

`-apple-system, Segoe UI, Roboto, Noto Sans, Ubuntu, Cantarell, Helvetica Neue;`

它可能不是最雄心勃勃的选择，但至少您的用户已经习惯了看到它。

#### 忽略字重小于 5 的字体

这并不总是正确的，但作为一般规则，与重量较轻的字体相比，具有许多不同重量的字体在制作时往往更加谨慎和注重细节。

许多字体目录（如谷歌字体）将允许您按“样式数量”进行过滤，这是可用权重以及这些权重的斜体变化的组合。

限制您必须选择的选项数量的一个好方法是将其增加到 10+（考虑到斜体）：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1fnlviga2dwg.webp)

特别是在谷歌字体上，它削减了 85% 的可用选项，只剩下不到 50 种无衬线字体可供选择。

#### 优化易读性

当有人设计字体系列时，他们通常是为特定目的而设计的。用于标题的字体通常具有更紧凑的字母间距和更短的小写字母（更短的 x 高度），而用于较小尺寸的字体具有更宽的字母间距和更高的小写字母。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.pxgdyzbbe2o.webp)

请记住这一点，并避免在主 ui 文本中使用具有短 x 高度的压缩字体。

#### 相信群众的智慧

如果一种字体很流行，它可能是一种很好的字体。大多数字体目录会让您按受欢迎程度排序，因此这是限制您的选择的好方法。

当你试图挑选出中性 ui 字体以外的东西时，这尤其有用。例如，选择具有某种个性的漂亮衬线可能很困难。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3asi6lqspqg0.webp)

利用成千上万其他人的集体决策权可以使事情变得容易得多。

#### 从关心的人那里偷东西

检查一些你最喜欢的网站，看看他们使用的是什么字体。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4zdaah48l8w0.webp)

有很多很棒的设计团队，里面的人对排版有着非常强烈的看法，他们经常会选择你可能从未使用上面概述的一些更安全的方法找到的很棒的字体。

#### 培养你的直觉

一旦你开始密切关注设计良好的网站上的排版，不久你就会很自如地将字体标记为很棒或糟糕。

你很快就会成为一个类型势利的人，但上面列出的建议将帮助你在此期间度过难关。

### 控制你的行长

在设置段落样式时，很容易犯这样的错误，即让文本适合您的布局，而不是试图创造最佳的阅读体验。

通常这意味着行太长，使文本更难阅读。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.hlfoa7zh760.webp)

为获得最佳阅读体验，请让您的段落足够宽，以适应每行 45 到 75 个字符。在 Web 上执行此操作的最简单方法是使用 em 单位，它与当前字体大小相关。 20-35em 的宽度将使您进入正确的范围。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2h9onaaszp40.webp)
![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4v04xyc3n020.webp)

每行超过 75 个字符有时也可以，但请注意，您正在进入危险的领域——如果您想安全起见，请坚持使用 45-75 个字符。

#### 处理更广泛的内容

如果您将段落文本与图像或其他大型组件混合在一起，即使整个内容区域需要更宽以容纳其他元素，您仍应限制段落宽度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3888sn631k80.webp)
![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.40jchers8sc0.webp)

在同一内容区域中使用不同的宽度乍一看似乎有悖常理，但结果几乎总是看起来更加精美。

### 基线，而不是中心

在很多情况下，使用多种字体大小在一行上创建层次结构是有意义的。

例如，也许您正在设计一张卡片，它在左上角有一个大标题，在右上角有一个较小的操作列表。

当你像这样混合字体大小时，你的直觉可能是将文本垂直居中以保持平衡：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.xvyydwrohh.webp)

当不同的字体大小之间有足够的空间时，它通常看起来不会太糟糕以引起您的注意，但是当文本靠得很近时，笨拙的对齐方式会变得更加明显：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.20z7v7if0zo.webp)

更好的方法是根据基线对齐混合字体大小，这是字母停留的假想线：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7l4qal0ktlc0.webp)

当您根据基线对齐混合字体大小时，您正在利用您的眼睛已经感知到的对齐参考。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.31ykc0izz8c0.webp)

结果是比将两段文本居中并偏移它们的基线时得到的更简单、更清晰的外观。

### 行高成正比

您可能听说过这样的建议：从可读性的角度来看，大约 1.5 的行高是一个很好的起点。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4a9vmozvkd00.webp)

虽然这不一定是不正确的，但为您的文本选择正确的行高比在所有情况下都使用相同的值要复杂一些。

#### 占行长度

我们在文本行之间添加空格的原因是为了让读者在文本换行时更容易找到下一行。你有没有不小心把同一行文字读了两遍，或者不小心跳过了一行？行高可能太短了。

当文本行间隔得太紧时，很容易读完页面右边缘的一行文本，然后将眼睛一直跳回左边缘，结果不确定下一行是哪一行。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3j0ah38b5580.webp)

当文本行很长时，这个问题会被放大。你的眼睛必须水平跳得越远才能阅读下一行，就越容易失去你的位置。

这意味着您的行高和段落宽度应该成比例——窄内容可以使用较短的行高，例如 1.5，但宽内容可能需要高达 2 的行高。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1b2s1gm8ct9c.webp)

#### 占字体大小

行长不是选择正确行高的唯一因素——字体大小也有很大影响。

当文本很小时，额外的行间距很重要，因为当文本换行时，它使您的眼睛更容易找到下一行。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6zcgq45n05c0.webp)

但是随着文字变大，您的眼睛就不需要那么多帮助了。这意味着对于大标题文本，您可能不需要任何额外的行距，行高为 1 就非常合适。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.c28qkiqu4ow.webp)

行高和字体大小成反比——小文本使用较高的行高，大文本使用较短的行高。

### 不是每个链接都需要颜色

当您将链接包含在其他非链接文本块中时，确保链接突出并且看起来可点击非常重要。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7bacwj9j9140.webp)

但是当你设计一个几乎所有内容都是链接的界面时，使用旨在使链接在段落文本中“弹出”的处理方式可能真的很霸道。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5s7ak8jl5xg0.webp)

相反，以更微妙的方式强调大多数链接，例如仅使用较重的字体粗细或较深的颜色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3n93usswpp20.webp)

默认情况下，某些链接甚至可能根本不需要强调。如果你的界面中有真正辅助的链接，而不是用户通过应用程序的主要路径的一部分，请考虑添加下划线或仅在悬停时更改颜色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6viilf0ak200.webp)

任何想要尝试的用户仍然可以发现它们，但不会与页面上更重要的操作争夺注意力。

### 与可读性保持一致

一般来说，文本应该对齐以匹配它所用语言的方向。对于英语（和大多数其他语言），这意味着绝大多数文本应该左对齐。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.w8wnkhbdv6o.webp)

其他对齐选项确实有它们的位置，你只需要有效地使用它们。

#### 不要将长格式文本居中

居中对齐对于标题或简短的独立文本块来说看起来很棒。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1nek0ss7klpc.webp)

但如果内容超过两三行，它几乎总是左对齐看起来更好。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.judf639psj4.webp)

如果你有几个文本块想要居中，但其中一个有点太长，最简单的解决方法是重写内容并使其更短：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1maof0gvhx1c.webp)

它不仅会解决对齐问题，还会使您的设计感觉更加一致。

#### 右对齐数字

如果您正在设计一个包含数字的表格，请将它们右对齐。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.mtw8ku3pctc.webp)

当数字列表中的小数点始终位于同一位置时，一目了然地比较它们会容易得多。

#### 连字符对齐文本

对齐的文本在打印时看起来很棒，并且在您想要更正式的外观时也可以在网络上很好地工作，但是如果不特别小心，它会在单词之间造成很多尴尬的差距：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3f9zhxqhptc0.webp)

为避免这种情况，无论何时对齐文本，您还应该启用连字符：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.49upqurhgli0.webp)

对齐文本在您试图模仿印刷外观的情况下效果最好，例如在线杂志或报纸。即便如此，左对齐文本也能很好地工作，所以这真的只是一个偏好问题。

### 有效地使用字母间距

在设置文本样式时，需要付出很多努力才能使粗细、颜色和行高恰到好处，但很容易忘记字母间距也可以调整。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6oeid3weszc0.webp)

作为一般规则，您应该相信字体设计师并且不要管字母间距。也就是说，在一些常见的情况下，调整它可以改进您的设计。

#### 紧缩的头条新闻

当有人设计字体系列时，他们会在设计时牢记目的。

像 open sans 这样的字体被设计成即使在小尺寸时也非常清晰，所以内置的字母间距比像 oswald 这样专为标题设计的字体要宽得多。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.80pny97cs78.webp)

如果您想为标题或标题使用具有更宽字母间距的系列，通常可以减少字母间距以模仿特制标题系列的简洁外观：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1wei3k4qvtsw.webp)

避免尝试以相反的方式工作——即使你增加字母间距，标题字体在小尺寸下也很少能很好地工作。

#### 提高全部大写的易读性

大多数字体系列中的字母间距都针对普通的“句子大小写”文本进行了优化——大写字母后跟大部分小写字母。

小写字母在视觉上有很多种。像 n、v 和 e 这样的字母完全适合字体的 x 高度，其他像 y、g 和 p 这样的字母有在基线下方伸出的下降部分，而像 b、f 和 t 这样的字母有在基线上方延伸的上升部分。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2n94gjjcmaw0.webp)

另一方面，全部大写的文本并不是那么多样化。由于每个字母的高度相同，使用默认的字母间距通常会导致文本更难阅读，因为字母之间的区别特征较少。

出于这个原因，增加全大写文本的字母间距以提高可读性通常是有意义的：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.33xy8sjqx1w0.webp)

## 使用颜色

### 为 HSL 设置十六进制

Hex 和 RGB 是在网络上表示颜色的最常见格式，但它们并不是最有用的。

使用十六进制或 RGB，在视觉上有很多共同点的颜色在代码中看起来完全不同。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5b3p2l1o5ug0.webp)

HSL 通过使用人眼直观感知的属性来表示颜色来解决此问题：色调、饱和度和亮度。

色调是颜色在色轮上的位置——它是一种颜色的属性，可以让我们将两种颜色识别为“蓝色”，即使它们不相同。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7g19zko0os8.webp)

色调以度为单位，其中 0° 为红色，120° 为绿色，240° 为蓝色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4d7fjx0dzk80.webp)

饱和度是颜色看起来有多鲜艳或鲜艳。 0% 饱和度是灰色（没有颜色），100% 饱和度是充满活力和强烈的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.8e7afkfbj4s.webp)

没有饱和度，色调是无关紧要的——当饱和度为 0% 时旋转色调实际上根本不会改变颜色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.76ellugx4cw0.webp)

亮度就像它听起来的那样——它衡量一种颜色与黑色或白色的接近程度。 0% 亮度是纯黑色，100% 亮度是纯白色，50% 亮度是给定色调的纯色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5qfhldn2c300.webp)

#### HSL 与 HSB

不要将 HSL 与 HSB 混淆——HSL 中的亮度与 HSB 中的亮度不同。

在 HSB 中，0%亮度总是黑色，但 100%亮度只有在饱和度为 0%时才是白色。当饱和度为 100% 时，HSB 中的 100% 亮度与 HSL 中的 100% 饱和度和 50% 亮度相同。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6local4ozi00.webp)

HSB 在设计软件中比 HSL 更常见，但浏览器只理解 HSL，所以如果你正在为 web 设计，HSL 应该是你的首选武器。

### 你需要比你想象的更多的颜色

您是否曾经使用过其中一种调色板生成器，您可以在其中选择一种起始颜色，调整一些选项，然后获得您应该用来构建网站的五种完美颜色？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.s5pblalrmls.webp)

这种选择完美配色方案的计算方法非常诱人，但除非您希望您的网站看起来像这样，否则它不是很有用：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.680ihvww2j40.webp)

#### 你真正需要的

你不能用五个十六进制代码构建任何东西。要构建真实的东西，您需要一组更全面的颜色以供选择。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6s7gix706og.webp)

您可以将好的调色板分为三类。

##### 灰色

文本、背景、面板、表单控件——几乎界面中的所有内容都是灰色的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6v1hczzaq800.webp)

你需要的灰色也比你想象的要多——三四种色调可能听起来很多，但用不了多久你就会希望有比色调 #2 深一点但比色调 #3 浅一点的东西。

实际上，您需要从 8-10 种色调中进行选择（更多信息请参见“预先定义您的色调”）。不会多到让您浪费时间在#77 和#78 色号之间做出选择，但足以确保您不必做出太多妥协。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2lyqwjepxj80.webp)

真正的黑色往往看起来很不自然，所以从真正的深灰色开始，然后逐步增加到白色。

##### 原色

大多数网站需要一种，也许两种颜色用于主要操作、活动导航元素等。这些颜色决定了网站的整体外观——让你认为 facebook 是“蓝色”的颜色。

就像灰色一样，您需要有多种 (5-10) 种浅色和深色可供选择。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3rweb31wv480.webp)

超浅色可以用作警报等内容的有色背景，而深色则非常适合文本。

##### 强调色

在原色之上，每个网站都需要一些强调色来向用户传达不同的信息。

例如，您可能想要使用吸引眼球的颜色（如黄色、粉红色或蓝绿色）来突出显示新功能：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.774w1jjc8os0.webp)

您可能还需要颜色来强调不同的语义状态，例如红色用于确认破坏性操作：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1dv43dzrffgg.webp)

…黄色表示警告消息：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2s75a8vhn5m0.webp)

…或绿色以突出积极趋势：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6hu72o3xaxw0.webp)

你也会想要这些颜色的多种色调，即使它们在整个用户界面中应该非常谨慎地使用。

如果您正在构建需要使用颜色来区分或分类相似元素（例如图形上的线条、日历中的事件或项目中的标签）的东西，您可能需要更多强调色。

总而言之，复杂的用户界面需要多达十种不同的颜色，每种颜色有 5-10 种色调，这种情况并不少见。

### 预先定义你的色调

当你需要在你的调色板中创建更亮或更暗的颜色变化时，不要聪明地使用 css 预处理器函数，如“变亮”或“变暗”来动态创建阴影。这就是你如何最终得到 35 种略有不同但看起来都一样的蓝调。

相反，预先定义一组固定的阴影，您可以在工作时从中选择。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6ykw7hwxzao0.webp)

那么你怎么把这样的调色板放在一起呢？

#### 首先选择底色

首先为您要创建的比例选择一种基色——浅色和深色所基于的中间颜色。

没有真正科学的方法来做到这一点，但对于原色和强调色，一个好的经验法则是选择一个适合按钮背景的阴影。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7kr54hromn40.webp)

重要的是要注意这里没有真正的规则，比如“从 50% 的亮度开始”或任何东西——每种颜色的表现都有点不同，所以你必须依靠你的眼睛来判断这个。

#### 找到边缘

接下来，选择最深的阴影和最浅的阴影。这也没有真正的科学依据，但它有助于思考它们将在哪里使用并根据该上下文选择它们。

最深的颜色阴影通常保留给文本，而最浅的阴影可能用于为元素的背景着色。

一个简单的警报组件是结合了这两种用例的一个很好的例子，因此它是选择这些颜色的好地方。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1h52ne0l3jwg.webp)

从与您的基色相匹配的颜色开始，然后调整饱和度和亮度，直到您满意为止。

#### 填补空白

一旦你有了基础、最深和最浅的色调，你只需要填补它们之间的空白。

对于大多数项目，每种颜色至少需要 5 种色调，如果您不想感到过于拘束，则可能接近 10 种。

9 是一个很大的数字，因为它很容易划分，并且可以更直接地填补空白。让我们将最深的阴影称为 900，将我们的基础阴影称为 500，将我们的最浅的阴影称为 100。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6lhjpji8tf40.webp)

首先选择色调 700 和 300，它们正好位于间隙中间。您希望这些色调感觉像是两侧色调之间的完美折衷。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.45szl0mj56e0.webp)

这会在刻度上再创建四个孔（800、600、400 和 200），您可以使用相同的方法填充这些孔。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3i4z9bedjrq0.webp)

您应该最终得到一组非常平衡的颜色，这些颜色提供的选项刚好可以满足您的设计理念而不会感到局限。

#### 灰色呢？

对于灰色，底色并不那么重要，但其他过程是相同的。从边缘开始，填补空白，直到你得到你需要的东西。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5olf3i721io0.webp)

通过为项目中最深的文本选择一种颜色来选择最深的灰色，通过选择适合微妙的灰白色背景的颜色来选择最浅的灰色。

#### 这不是一门科学

尽管它很诱人，但您不能仅依靠数学来制作完美的调色板。

像上面描述的那样的系统方法非常适合您入门，但如果需要，请不要害怕做一些小的调整。

一旦你真正开始在你的设计中使用你的颜色，你几乎不可避免地会想要调整一个阴影的饱和度，或者使几个阴影更亮或更暗。相信你的眼睛，而不是数字。

如果可以避免，请尽量避免过于频繁地添加新色调。如果你不努力限制你的调色板，你可能根本没有颜色系统。

### 不要让亮度扼杀你的饱和度

在 HSL 色彩空间中，当颜色接近 0% 或 100% 亮度时，饱和度的影响会减弱——同样的饱和度值在 50% 亮度下看起来比在 90% 亮度下看起来更鲜艳。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.53bgudjgcww0.webp)

这意味着，如果您不希望给定颜色的较浅和较深的阴影看起来褪色，则需要随着亮度远离 50% 而增加饱和度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.lcbx3c5gc1o.webp)

这是微妙的，但像这样的小细节加起来，尤其是当一种颜色被应用到用户界面的大部分时。

但是如果你的底色已经很饱和了怎么办？如果饱和度已经是 100%，如何增加饱和度？

#### 使用感知亮度对您有利

你觉得这两种颜色哪个更浅？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4d9awht138s0.webp)

黄色的，对吧？事实证明，就 HSL 而言，这两种颜色实际上具有完全相同的“亮度”：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.41tfel3bp4q0.webp)

那么为什么我们看到黄色更浅呢？事实证明，由于人眼感知颜色的方式，每种色调都具有固有的感知亮度。

您可以通过将其 rgb 组件代入此公式来计算颜色的感知亮度：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5nla6vgyq7c0.webp)

以 100% 饱和度和 50% 亮度的不同色调作为样本，我们可以很好地了解色轮周围不同颜色的感知亮度：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4n83sypc7j00.webp)

正如预期的那样，黄色比蓝色具有更高的感知亮度。但这里有趣的是，感知到的亮度并不仅仅从最暗的色调线性变化到最亮的色调——相反，存在三个独立的局部最小值（红色、绿色和蓝色）和三个局部最大值（黄色、青色和洋红色） ).

#### 通过旋转色调改变亮度

从表面上看，理解颜色当然是一件有趣的事情。但是当您意识到如何在您的设计中使用这些知识时，事情就会变得非常有趣。

通常当你想改变一种颜色的亮度时，你可以调整亮度组件：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.8tk9hoa43xw.webp)

虽然这确实可以使颜色变亮或变暗，但您通常会失去一些颜色的强度——颜色看起来也更接近白色或黑色，而不仅仅是更亮或更暗。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1yppdgjjgxs0.webp)

由于不同的色调具有不同的感知亮度，另一种改变颜色亮度的方法是旋转其色调。

要使颜色变浅，请将色调旋转到最接近的明亮色调 - 60°、180° 或 300°。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4hfr7kwf9yg0.webp)

要使颜色更深，请将色调旋转到最接近的深色调 — 0°、120° 或 240°。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1wtkfsfglkn4.webp)

这在尝试为黄色等浅色创建调色板时非常有用。通过在降低亮度的同时逐渐将色调转向更多橙色，较暗的色调会感觉温暖和丰富，而不是暗淡和棕色：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.42ggv692sj60.webp)

您当然也可以将这些方法结合起来，通过调整色调获得一些亮度，通过调整亮度获得一些亮度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.387gfroe6i20.webp)

虽然这是在不影响颜色强度的情况下改变颜色亮度的好方法，但它在小剂量时效果最好。不要将色调旋转超过 20-30°，否则它看起来像是完全不同的颜色，而不仅仅是更亮或更暗。

### 灰色不一定是灰色

根据定义，真正的灰色具有 0% 的饱和度——它根本没有任何实际颜色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6qyo7gjg05k0.webp)

但实际上，很多我们认为是灰色的颜色实际上饱和度很高：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.72cocsgj2o00.webp)

这种饱和度使一些灰色感觉凉爽而其他灰色感觉温暖。

#### 色温

如果您以前购买过灯泡，您必须在发出黄光的“暖白”灯泡和发出蓝光的“冷白”灯泡之间做出决定。

用户界面中的饱和灰色以类似的方式工作。

如果你想让你的灰色感觉凉爽，用一点蓝色来饱和它们：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4jdyl1ok8bk0.webp)

给你的灰色一个温暖的感觉，用一点黄色或橙色饱和它们：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.sjahojjsuvk.webp)

为了保持一致的温度，不要忘记增加浅色和深色的饱和度。如果不这样做，与接近 50% 亮度的灰色相比，这些色调看起来会有点褪色。

你想让你的灰色饱和多少完全取决于你——如果你只想稍微倾斜温度，就加一点，或者如果你想让界面在一个方向或另一个方向上强烈倾斜，就把它调高。

### 可访问并不一定意味着丑陋

为确保您的设计可访问，网络内容可访问性指南 (wcag) 建议普通文本（小于 18 像素）的对比度至少为 4.5:1，较大文本的对比度至少为 3:1 .

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.g6j290eo3rc.webp)

对于典型的浅色背景上的深色文本情况，满足此建议非常容易，但是当您开始使用颜色时，它会变得更加棘手。

#### 翻转对比度

当在彩色背景上使用白色文本时，您会惊讶于颜色通常需要多深才能满足 4.5:1 的对比度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6qrvmewzd780.webp)

当这些元素不应该成为页面的焦点时，这可能会产生层次结构问题——深色背景会真正吸引用户的注意力。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.44w6ob9t4q2.webp)

你可以通过翻转对比度来解决这个问题。不要在深色背景上使用浅色文本，而是在浅色背景上使用深色文本：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4yuh938d5rs0.webp)

颜色仍然存在以帮助支持文本，但它不那么直接，也不会干扰页面上的其他操作。

#### 旋转色调

比彩色背景上的白色文本更难的是彩色背景上的彩色文本。如果您曾经尝试为深色面板中的一些辅助文本选择颜色，就会遇到这种情况。

如果你从取背景颜色开始，简单地调整亮度和饱和度，你会发现很难达到推荐的对比度而不非常接近纯白色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1nqynksktjuo.webp)

您不希望主要文本和次要文本看起来一样，那么您还能做什么？

好吧，因为有些颜色比其他颜色更亮，一种增加对比度而又不接近白色的方法是将色调旋转到更亮的颜色，如青色、品红色或黄色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.63zo8j7dpes0.webp)

这可以使文本更易于访问，同时仍保持其色彩丰富。

### 不要只依赖颜色

颜色可以是增强信息并使其更易于理解的绝佳方式，但请注意不要依赖它，否则有色盲的用户将很难理解您的用户界面。

以这些指标卡为例。通过这种设计，红绿色盲的人无法轻易判断指标是变好还是变差：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6tz9hs48hc8.webp)

解决此问题的一个简单方法是也以其他方式传达该信息，例如通过添加图标来指示更改是积极的还是消极的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2luexq7721o0.webp)

像图表这样的东西怎么样，其中每条趋势线都有不同的颜色？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.510d432f3ss0.webp)

在这种情况下，尝试依靠对比度而不是使用完全不同的颜色。对于色盲的人来说，分辨明暗之间的区别要比他们分辨两种不同颜色之间的区别容易得多。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6rhksgd3b1k0.webp)

始终使用颜色来支持您的设计已经表达的内容；切勿将其用作唯一的交流方式。

## 创造深度

### 模拟光源

你有没有注意到界面中的一些元素感觉它们从页面上凸起，而另一些元素感觉它们嵌入到背景中？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1dubqii1o3hc.webp)

创建这种效果乍一看可能很复杂，但实际上只需要您了解一个基本规则。

#### 光来自上方

看看这扇门上的镶板：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5jyx03ftuw40.webp)

即使您只是看平面图像，门上的面板仍然很明显是凸起的。这是为什么？

注意到面板的顶部边缘更亮了吗？那是因为它朝向天空倾斜并接收到更多的光。同样，底部边缘较暗，因为它与天空成一定角度，接收到的光线较少。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.ebvapy35l0g.webp)

这些边缘可能以这种方式定向的唯一方法是面板本身被抬起，这就是我们的大脑感知它的方式。

现在看看这个柜子上的镶板：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4e8ujgwu5ue0.webp)

在这种情况下，很明显面板是内嵌的，因为顶部有一个阴影，表明上方的边缘挡住了光线，而底部边缘较亮，表明它向上倾斜。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3nssso4bzos0.webp)

要在您的设计中创造同样的深度感，您需要做的就是模仿光线影响现实世界事物的方式。

#### 在用户界面中模拟光

如果你想让一个元素出现凸起或凹陷，首先要弄清楚你希望该元素具有什么样的轮廓，然后模仿光源如何与该形状相互作用。

##### 凸起的元素

例如，假设你有一个按钮，你希望它看起来从页面上凸起，顶部和底部的边缘完全平坦：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.38lfsao7aa60.webp)

因为顶部和底部边缘都是平的，所以不可能同时看到它们。人们通常会略微向下看屏幕，因此为了获得最自然的外观，请露出一点顶部边缘并隐藏底部边缘。

由于顶部边缘朝上，使其比按钮的表面稍微亮一些，通常使用顶部边框或带有轻微垂直偏移的内嵌框阴影：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6x2xpko44g80.webp)

手动选择较浅的颜色而不是使用半透明的白色以获得最佳效果 - 简单地覆盖白色可以吸收底层颜色的饱和度。

接下来，您需要考虑一个事实，即凸起的元素会阻挡部分光线到达元素下方的区域。

通过添加一个带有轻微垂直偏移的小暗框阴影来做到这一点（您只希望阴影出现在元素下方）：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2tq6rvf8xei0.webp)

不要被模糊半径冲昏头脑，几个像素就足够了。这些类型的阴影应该有非常锐利的边缘——看看墙上插座或窗框底部投射的阴影，看看真实世界的例子。

##### 内嵌元素

假设您正在设计一个“很好”的组件，感觉它应该嵌入到页面中。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2gw70szngik0.webp)

稍微向下看，只能看到下唇。因为它面向天空，所以使用底部边框或具有负垂直偏移的插入阴影为该边缘提供稍微亮一点的颜色：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1xwybj286wcg.webp)

井上方的区域应该阻挡一些光线到达井的顶部，所以添加一个小的深色嵌入框阴影，垂直偏移略微正，以确保它不会穿透底部：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.fv7f6az7eqg.webp)

这种相同的处理方式适用于任何可能需要嵌入显示的元素，例如文本输入和复选框：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4qo2l4uwnug0.webp)

#### 不要得意忘形

一旦您了解了如何在界面中模拟光线，您可能会忍不住花几个小时进行修补，调整和调整以了解您可以多接近地模仿现实世界。

虽然这可能是一个有趣的练习，但在实践中它可能会导致界面繁忙且不清楚。从现实世界中借用一些视觉线索是增加一点深度的好方法，但没有必要尝试让事情看起来像照片一样逼真。

### 使用阴影来传达高度

阴影不仅仅是一种华而不实的效果——经过深思熟虑，它们可以让您将元素放置在虚拟的 z 轴上，以创造一种有意义的深度感。

具有小模糊半径的小阴影使元素感觉仅略微从背景中凸起，而具有较高模糊半径的较大阴影使元素感觉更接近用户：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1cwujc2bagn4.webp)

与用户感觉越接近的东西，就越能吸引他们的注意力。

你可以为按钮之类的东西使用较小的阴影，你希望用户注意到它但不希望它占据页面：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.30aeipa1m0y0.webp)

中等阴影对于下拉菜单之类的东西很有用；需要位于 ui 其余部分之上的元素：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4d5uu60yjkg0.webp)

大阴影非常适合模态对话框，您真的想在其中吸引用户的注意力：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4tpuxk589r00.webp)

#### 建立高程规范

就像颜色、排版、间距和大小一样，定义一组固定的阴影将加快您的工作流程并有助于保持设计的一致性。

你不需要大量不同的阴影——五个选项通常就足够了。

首先定义最小的阴影和最大的阴影，然后用线性增加的阴影填充中间：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1k2bxs7ydrr4.webp)

#### 将阴影与交互相结合

阴影不仅对在 z 轴上静态定位元素有用；当用户与元素交互时，它们也是向用户提供视觉提示的好方法。

例如，假设您有一个项目列表，用户可以在其中单击并拖动每个项目来对它们进行排序。当用户点击一个项目时给它添加一个阴影，让人感觉它在列表中的其他项目之上向前弹出，并让用户清楚他们可以拖动它：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3zeacb7wpes0.webp)

类似地，您可以通过切换到更小的阴影，或者完全移除阴影，让用户点击按钮时感觉它被压入了页面：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7ddz8ik5kvw0.webp)

像这样以有意义的方式使用阴影是破解选择元素应该具有哪种阴影的过程的好方法。不要考虑阴影本身，考虑您希望元素在 z 轴上的位置并相应地为其分配阴影。

### 阴影可以有两部分

曾经在网站上检查过一个非常漂亮的阴影，并注意到他们实际上使用了两个阴影？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4106mlxfmyk0.webp)

有一种解决这种疯狂的方法，它实际上非常简单而且很有意义。

当你看到有人将两个影子组合在一起时，他们不仅仅是随机试验直到看起来不错，他们正在使用每个影子来完成特定的工作。

第一个阴影更大更柔和，具有相当大的垂直偏移和大的模糊半径。它模拟直接光源在物体后面投射的阴影。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3v2wsraoae00.webp)

第二个阴影更紧更暗，垂直偏移更小，模糊半径更小。它模拟物体下方的阴影区域，即使是环境光也难以到达。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.23921dbv52tc.webp)

像这样使用两个阴影比使用一个阴影可以给你更多的控制——你可以保持较大的阴影漂亮和微妙，同时仍然使阴影更接近元素的边缘漂亮和定义。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1e4uhx9ceie.webp)

#### 考虑海拔

当一个物体离表面越来越远时，由于缺乏环境光而产生的小而暗的阴影会慢慢消失（继续，用你桌上的东西试试）。

因此，如果您打算在自己的项目中使用这种双阴影技术，请确保使代表更高海拔的阴影更加微妙。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4n2016mx0jc0.webp)

它应该在你的最低海拔处非常明显，而在你的最高海拔处几乎（或完全）看不见。

### 即使是平面设计也可以有深度

当大多数人谈论“平面设计”时，他们指的是没有阴影、渐变或任何其他试图模仿光与现实世界中事物相互作用的效果的设计。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1jdbl0bvepfk.webp)

但最有效的平面设计仍然传达深度，他们只是以不同的方式做到这一点。

#### 用颜色创造深度

一般来说（尤其是相同颜色的阴影），较浅的物体感觉离我们更近，而较暗的物体感觉更远。

使元素比背景颜色更亮，让它感觉像是从页面上凸起，或者比背景颜色更暗，如果你想让它感觉像一口井：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3cf6try4lr80.webp)

这同样适用于非扁平化设计——颜色只是工具带中用于传达距离的另一种工具。

#### 使用实体阴影

在平面设计中传达深度的另一种方法是使用短的、垂直偏移的阴影，完全没有模糊半径。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3rb872oth7a0.webp)

这是让卡片或按钮稍微脱离页面而不牺牲平面美感的好方法。

### 重叠元素以创建图层

创造深度的最有效方法之一是重叠不同的元素，让人感觉设计有多个层次。

例如，不是将卡片完全包含在另一个元素中，而是对其进行偏移，使其跨越两个不同背景之间的过渡：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5mrg58orzr00.webp)

你也可以让一个元素比它的父元素高，所以它在两边重叠：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1vfud2ggnhj4.webp)

重叠元素也可以为较小的组件增加深度，例如这个旋转木马上的控件：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2bwee4sn4iv4.webp)

#### 重叠图像

这种技术也适用于图像，但如果不特别考虑，重叠图像很容易发生冲突。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.42v50ysx3dy0.webp)

避免这种情况的一个简单技巧是给图像一个“隐形边框”——一个与背景颜色相匹配的边框——所以图像之间总是有一点差距：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3t259g5wodu0.webp)

你仍然会创建层的外观，但没有丑陋的冲突。

## 处理图像

### 使用好照片

糟糕的照片会毁了一个设计，即使它的其他一切看起来都很棒。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7i50dyedvko0.webp)

如果您的设计需要摄影，而您又不是天才摄影师，那么您有两种选择：

1.  **聘请专业摄影师。**

    如果您的项目需要非常具体的照片，请委托专业人士。拍出好照片不仅仅需要使用昂贵的相机，还需要光线、构图、色彩——需要多年才能培养的技能。

2.  **使用高质量图片库。**

    如果您的需求更通用，那里有大量优质资源，您可以在其中购买优质的库存照片。甚至还有像 unsplash 这样的免费提供精美照片的网站。

无论你做什么，都不要使用占位符图像进行设计，并期望能够用智能手机拍摄一些照片并在以后交换它们。它永远行不通。

### 文字需要一致的对比

曾经尝试在大英雄图片上打上标题，却发现无论您尝试用什么颜色显示文本，它仍然难以阅读？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7d6zk929poc0.webp)

那是因为问题不在于文字，而在于图像。

#### 背景图片的问题

照片可以非常动态，有很多非常亮的区域，也有很多非常暗的区域。白色文本在黑暗区域可能看起来不错，但在明亮区域会丢失。深色文本在明亮区域看起来很棒，但在黑暗区域会丢失。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.16ad9ho1rz28.webp)

要解决这个问题，需要降低图像中的动态，使文字和背景的对比度更加一致。

#### 添加叠加层

增加整体文本对比度的一种方法是向背景图像添加半透明覆盖层。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2qkyd4cuvhs0.webp)

黑色覆盖层将淡化浅色区域并帮助浅色文本脱颖而出，而白色覆盖层将照亮深色区域并帮助深色文本脱颖而出。

#### 降低图像对比度

使用叠加层时做出的妥协之一是使整个图像变亮或变暗，而不仅仅是问题区域。

如果你想要更多的控制，另一个解决方案是降低图像本身的对比度：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4nw4pn8al6y0.webp)

降低对比度会改变图像整体的明暗程度，因此请务必调整亮度以进行补偿。

#### 给图像上色

帮助文本在图像中脱颖而出的另一种方法是使用单一颜色为图像着色。

一些照片编辑软件将此作为一流的功能，但如果您的软件没有，您可以通过三个步骤创建此效果：

1. **降低图像对比度**，平衡一下。
2. **对图像进行去饱和处理**，以去除任何现有颜色。
3. **添加实体填充**，使用“乘法”混合模式。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.7kj604wnrxk0.webp)

这也是使背景图像与您现有的品牌颜色更好地搭配的好方法。

#### 添加文字阴影

如果你想在背景图像中保留更多的动态，文本阴影可能是一种很好的方法，可以只在你最需要的地方增加对比度。

你想让它看起来更像是一种微妙的发光而不是实际的阴影，所以使用大的模糊半径并且不要添加任何类型的偏移。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.46rcoohrjrq0.webp)

降低整体图像对比度仍然是个好主意，但是将其与文本阴影结合使用意味着您可以减少一点。

### 一切都有预期的大小

每个人都知道将位图图像缩放到大于其原始大小是个坏主意——他们会立即感到“模糊”并失去清晰度。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5tylt1rm6tc0.webp)

但这并不是缩放比例出错的唯一方法，即使您认为自己在安全地进行操作。

#### 不要放大图标

如果你正在设计一些可以使用一些大图标的东西（比如登陆页面的“功能”部分），你可能会本能地抓住你最喜欢的 svg 图标集并增加尺寸直到它们满足你的需要。

毕竟它们是矢量图像，所以如果你增加尺寸，质量不会受到影响，对吧？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4gz7p7k0zgo0.webp)

虽然当你增加尺寸时矢量图不会降低质量，但当你将它们放大到预期尺寸的 3 倍或 4 倍时，以 16-24 像素绘制的图标永远不会看起来很专业。他们缺乏细节，并且总是感觉不成比例地“矮胖”。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5n8ogvl8tqc0.webp)

如果你只有小图标，请尝试将它们包围在另一个形状中并为该形状提供背景颜色：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.qkeay7flpxc.webp)

这使您可以使实际图标更接近其预期大小，同时仍然填充更大的空间。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.49doifqjd4o0.webp)

#### 不要缩小屏幕截图

假设您想在同一功能页面上包含您的应用程序的屏幕截图。

如果你截取全尺寸屏幕截图并将其缩小 70% 以使其适合，你最终会得到一张试图将太多细节塞进太小空间的图像。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6uspvrmjpoc0.webp)

您应用程序中的 16px 字体在您的屏幕截图中变成了 4px 字体，访问者的眼球会在距离屏幕两英寸的地方眯起眼睛，努力弄清所有文字的含义。

如果您想在设计中包含详细的屏幕截图，请以较小的屏幕尺寸截取屏幕截图（例如您的平板电脑布局）并为其节省大量空间，这样您就不必将其缩小太多：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3kvji9x0nky0.webp)

或者考虑只截取部分屏幕截图，这样您就可以在更小的空间中显示它而无需缩小它：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.r6y1holm70g.webp)

如果你真的需要在一个狭小的空间中放置整个应用程序的屏幕截图，请尝试绘制一个简化版本的用户界面，删除细节并将小文本替换为简单的线条：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1j1eoa05bqv4.webp)

它仍然会传达总体设计，而不会诱使访问者尝试弄清所有细节。

#### 也不要缩小图标

就像绘制用于 16px 的图标在放大时看起来很粗壮一样，用于更大尺寸的图标在缩小时看起来不规则和模糊。

最极端的例子是网站图标，您在浏览器选项卡中的页面标题旁边看到的那些小图标。

如果你试图将一个 128px 的标志缩小到 favicon 大小，它就会变成糊状，因为浏览器会尽力在一个 16px 的小方块中呈现所有细节：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4lh6ql8ap6y0.webp)

更好的方法是以目标尺寸重新绘制徽标的超级简化版本，这样您就可以控制妥协而不是将其留给浏览器：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6muz5fo5zrk0.webp)

### 当心用户上传的内容

当您依赖于用户上传的图像时，您无法微调对比度、仔细调整颜色或裁剪完美的框架。

虽然在某种程度上你总是受用户的摆布，但你可以做一些事情来确保他们的内容不会完全破坏你的设计。

#### 控制形状和大小

以用户上传的图像固有的纵横比显示确实会影响布局，尤其是当屏幕上同时显示大量图像时。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3mwloeuy0u20.webp)

与其让用户破坏你的页面结构，不如将他们的图像放在固定容器中，裁剪掉任何不合适的东西。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3nyhv80aetm.webp)

现在用 css 很容易做到这一点，只需将图像设为背景图像，并将 background-size 属性设置为 cover。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5qeb22ej0zs0.webp)

#### 防止背景渗出

当用户提供的图像的背景颜色与您的用户界面中的背景颜色相似时，图像和背景可能会融合在一起，导致图像变形。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.qsgyx0811wg.webp)

与其尝试使用边框解决此问题，不如尝试使用微妙的内部框阴影：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.40s7i92e4740.webp)

边框通常会与图像中的颜色发生冲突，而大多数人甚至都不会意识到阴影的存在。

如果你不喜欢使用方框阴影时出现的轻微“嵌入”效果，半透明的内边框也很不错。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5s3uhwrkvf80.webp)

## 收尾工作

### 增加默认值

你不必总是在设计中添加新元素来增加光彩——有很多方法可以通过“增压”已有的元素来使页面活跃起来。

例如，如果您的设计包含项目符号列表，请尝试用图标替换项目符号：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5a41w008cvs0.webp)

在很多情况下，复选标记和箭头是很好的通用选择，但您也可以使用更具体的内容，例如用于安全相关功能列表的挂锁图标：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1dekl0ndqygw.webp)

同样，如果您正在制作推荐书，请尝试通过增加尺寸和更改颜色将引语“提升”为视觉元素：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3al7vifuaqi0.webp)

链接是特殊样式的另一个很好的候选者。您可以做一些像更改颜色和字体粗细这样简单的事情，或者像一个与文本部分重叠的厚而多彩的自定义下划线这样花哨的事情：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.69tw6hsyi980.webp)

如果您正在处理表单，使用自定义复选框和单选按钮是为设计添加一些颜色的简单方法：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5ui0439umtc0.webp)

只需为所选状态使用您的品牌颜色之一而不是浏览器默认值通常就足以让一些东西从无聊变成感觉精致和精心设计。

### 添加带有重音边框的颜色

如果您不是平面设计师，您如何将其他设计从精美的摄影或彩色插图中获得的那种视觉天赋添加到您的用户界面中？

一个简单的技巧可以产生很大的不同，那就是在你的界面部分添加彩色边框，否则会让人觉得有点乏味。

例如，在卡片的顶部：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.49600womo4a0.webp)

…或突出显示活动的导航项：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2kzhwe44xrm0.webp)

…或在警告消息的旁边：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2cgl21smhxes.webp)

……或者作为标题下方的简短强调：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.19r0uxdmtgow.webp)

…甚至在整个布局的顶部：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5pws3loxgt00.webp)

向您的用户界面添加彩色矩形不需要任何图形设计人才，而且它可以大大有助于让某些东西感觉更“设计”。

### 装饰你的背景

即使你在层次结构、间距和排版方面做得很好，有时设计仍然会让人觉得有点平淡。

在不彻底改变设计的情况下打破一些单调的好方法是为您的一些背景添加一些刺激。

#### 更改背景颜色

给背景增添一些趣味的一种方法是简单地改变颜色。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6j1sutl517w.webp)

这对于强调单个面板以及在整个页面部分之间添加一些区别非常有用。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6abprsbptb40.webp)

为了看起来更有活力，你甚至可以使用轻微的渐变：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.g9gvqok2vv.webp)

为获得最佳效果，请使用相距不超过 30° 的两种色调。

#### 使用重复模式

另一种方法是添加一个微妙的可重复模式，就像英雄模式中的这个：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.vqapegwvjgw.webp)

你不必在整个背景上重复它，设计为沿单个边缘重复的图案也可以看起来很棒。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.4krzalgsac60.webp)

保持背景和图案之间的对比度非常低，以确保可读性。

#### 添加简单的形状或插图

除了装饰整个背景，您还可以尝试在特定位置包含一两个单独的图形。

简单的几何形状很适合这个：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6awvvsouiy40.webp)

......就像可重复模式的小块一样：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.15a19n2jfpy8.webp)

你甚至可以做一些更复杂的事情，比如简化的世界地图：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.20cl3umad3vk.webp)

就像完整的背景图案一样，最好保持低对比度，以免干扰内容。

### 不要忽视空状态

假设您正在为您正在开发的应用程序设计一项新功能。

您花费了大量时间制作完美逼真的示例数据，挑选用户名和头像，并制作出精美而令人兴奋的屏幕。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5j8j0sfqy4g0.webp)

您将其全部编码并将其部署到生产环境中。但是当兴奋的用户点击导航中的新项目时，他们会看到：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.wa6qhnq46xs.webp)

如果你正在设计依赖于用户生成内容的东西，空状态应该是一个优先事项，而不是事后的想法。

尝试结合图像或插图来吸引用户的注意力，并强调号召性用语以鼓励他们采取下一步行动：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.71q12n1p6u80.webp)

如果您正在处理具有大量支持 ui（例如选项卡或过滤器）的东西，请考虑完全隐藏这些东西。在用户创建一些内容之前，呈现一堆什么都不做的操作是没有意义的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5yflec2qbho0.webp)

空状态是用户与新产品或功能的第一次交互。将它们作为变得有趣和令人兴奋的机会——不要满足于平淡乏味。

### 使用更少的边框

当您需要在两个元素之间创建分隔时，请尽量避免立即伸手去拿边界。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.28t8f6ebdgro.webp)

虽然边框是区分两个元素的好方法，但它们并不是唯一的方法，而且使用太多边框会使您的设计显得忙碌和混乱。

#### 使用盒子阴影

框阴影可以像边框一样很好地勾勒出元素轮廓，但可以更微妙，并且可以在不分散注意力的情况下实现相同的目标。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.yyl01kjzf4g.webp)

当您应用框阴影的元素与背景的颜色不同时，此方法最有效。

#### 使用两种不同的背景颜色

给相邻元素略微不同的背景颜色通常是您在它们之间创建区分所需要的。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.2hzrzrhvraq0.webp)

如果除边框外您已经在使用不同的背景颜色，请尝试删除边框；你可能不需要它。

#### 添加额外的间距

有什么比简单地增加分离更好的方法来创建元素之间的分离？

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5os7ojtl3aw0.webp)

将事物进一步分开是在不引入任何新用户界面的情况下区分元素组的好方法。

### 创造性思考

大多数人对某些组件的外观有很多先入为主的观念。但是仅仅因为我们已经习惯于相信只有一种方法来设计特定的组件，并不意味着它是真的。

例如，画一个下拉菜单。您可能正在想象一个带有一点阴影的白色框和一个堆叠在其中的链接列表：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.63e6ywm3t9k.webp)

但是谁说下拉菜单必须是无聊的链接列表？它只是屏幕上的一个浮动框，您可以用它做任何您想做的事情。

将它分成几个部分，使用多个列，添加支持文本或彩色图标——用它做一些有趣的事情！

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1raroih55a9s.webp)

并且不要只停留在下拉菜单上；表格之类的东西怎么样？

当您想象一个表时，您可能会想到每个列都包含一个特定的数据：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.425my58a5eo0.webp)

但是，表不必以这种方式工作——如果列不需要可排序，则没有理由不能将它与相关列组合并引入一些有趣的层次结构：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.zzwfzj97jjk.webp)

表格内容也不一定是纯文本。如果有意义，添加图像，或引入一些颜色来丰富现有数据：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.33aws7e3a7c0.webp)

单选按钮怎么样？没有什么比一堆旁边有小圆圈的标签更无聊的了。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.3oq9zuk4fnc0.webp)

如果一组单选按钮是您正在设计的用户界面的重要组成部分，请尝试使用可选卡片之类的东西：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5r56rf397no0.webp)

不要让你现有的信念阻碍你的设计——约束是强大的，但有时一点自由正是你将界面提升到一个新水平所需要的。

## 升级

希望读完这本书后，您对自己能够在不依赖设计师的情况下做出令人惊叹的东西的能力更有信心。但是，尽管我们已尽最大努力将我们可能想到的每一个好主意都塞进去，但总会有更多东西需要学习。

您可以通过以下两种最佳方式继续磨练自己的技能，并将新工具添加到您的工具箱中。

### 寻找你不会做出的决定

每当你偶然发现一个你真正喜欢的设计时，问问自己：

_“设计师在这里做了什么我从未想过要做的事吗？”_

也许这是他们在日期选择器上反转背景颜色的方式：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.5a4jm1ou26k0.webp)

…或者他们将按钮放置在文本输入内而不是外部的方式：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.6cj6cj594500.webp)

……或者像为标题使用两种不同字体颜色这样简单的事情：

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1ozny803mxnk.webp)

注意这些非直觉的决定是发现新想法的好方法，您可以将这些想法应用到您自己的设计中。

### 重建你最喜欢的界面

注意使设计看起来真正精致的小细节的绝对最佳方法是从头开始重新创建该设计，而无需查看开发人员工具。

当您试图找出为什么您的版本看起来与原始版本不同时，您会发现诸如“降低标题的行高”、“为大写文本添加字母间距”或“组合多个阴影”之类的技巧你自己。

![image](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/Book/image.1oic2z5xir0g.webp)

通过持续仔细地研究激发您灵感的作品，您将在未来几年中掌握设计技巧。
