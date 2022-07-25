---
title: "JavaScript 知识总结"
date: 2019-07-18T22:04:47+08:00
categories: ["Development"]
tags: ["Language"]
---

## 简介

> 定义：JavaScript 一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言。  
> 产生原因：网页没有复杂交互行为。

{{< card "https://www.liaoxuefeng.com/wiki/1022910821149312" >}}

## 语法

### 变量类型

- number
- string
- boolean
- object
- function
- null
- undefined

### 关键字

- 流程控制
  - return
  - continue
  - break
  - do
  - while
  - for
  - if
  - else
  - switch
  - case
- 定义
  - var ：定义变量
  - let : 不可重复声明、块级作用域(ES6+)
  - const : 不可重复声明、块级作用域(ES6+)
  - function
  - new
- 异常处理
  - try ：测试代码块的错误
  - catch：处理错误
  - finally
  - throw ：创建自定义错误
- 类型判断
  - typeof
  - instanceof
- 其他

  - this
  - in : 与 for 一起使用用于遍历对象的属性名或判断某个对象是否具有某个属性
  - delete : 删除对象的某个属性，只能删除自身定义的公有属性，即"this.属性名"定义的属性，而不能删除私有属性或通过 proptotype 定义的公有属性（已实践）。此外可删除直接在对象上添加的属性，如`var a = new Object();a.name = "name"; delete a.name;`
  - with : 引用一个对象，使访问属性与方法更加方便（只能访问与修改属性，不能增加属性与方法）

### 运算符

- 数学运算符 : +,-,\*,/,%
- 比较运算符 : >,<,\==,!=,>=,<=,=\==,!==
- 逻辑运算符 : &&,||,!
- 位操作符 : ^,~,&,|,<<,>>,>>>

### 函数的定义

- 正常方式`function mysum(num1,num2){return num1+num2;}`
- 直接量/匿名方式`var mysum = function(num1,num2){return num1+num2;}`
- 构造器方式`new Function("num1","num2","return num1+num2;")`
- 箭头函数(ES6)

## 常用对象

### 内建对象

- Math
- Date
  - getTime() : 获取毫秒值
- String
  - length : 字符串的长度
  - indexOf() : 检索字符串。
  - substr() : 从起始索引号提取字符串中指定数目的字符。
  - split() : 把字符串分割为字符串数组。
- Array
  - length : 设置或返回数组中元素的数目。
  - join() : 把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。
  - push() : 向数组的末尾添加一个或更多元素，并返回新的长度。
  - splice() : 删除元素，并返回删除元素
- RegExp
  - 修饰符
    - i : 执行对大小写不敏感的匹配。
    - g : 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。
  - 中括号
    - [abc] : 查找方括号之间的任何字符。
    - [^abc] : 查找任何不在方括号之间的字符。
    - [0-9] : 查找任何从 0 至 9 的数字。
    - [a-z] : 查找任何从小写 a 到小写 z 的字符。
    - [A-Z] : 查找任何从大写 A 到大写 Z 的字符。
    - [A-z] : 查找任何从大写 A 到小写 z 的字符。
  - 元字符
    - . : 查找单个字符，除了换行和行结束符。
    - \w : 查找任意一个字母、数字或下划线字符。
    - \W : 查找非\w 字符。
    - \d : 查找数字。
    - \D : 查找非数字字符。
    - \s : 查找空白字符。
    - \S : 查找非空白字符。
    - \b : 匹配单词边界。
    - \B : 匹配非单词边界。
  - 量词
    - n+ : 匹配任何包含至少一个 n 的字符串。
    - n\* : 匹配任何包含零个或多个 n 的字符串。
    - n? : 匹配任何包含零个或一个 n 的字符串。
    - n{X} : 匹配包含 X 个 n 的序列的字符串。
    - n{X,Y} : 匹配包含 X 至 Y 个 n 的序列的字符串。
    - n{X,} : 匹配包含至少 X 个 n 的序列的字符串。
    - n\$ : 匹配任何结尾为 n 的字符串。
    - ^n : 匹配任何开头为 n 的字符串。
    - ?=n : 匹配任何其后紧接指定字符串 n 的字符串。
    - ?!n : 匹配任何其后没有紧接指定字符串 n 的字符串。

### HTML DOM 对象

- document
  - document.getElementById() : 返回对拥有指定 id 的第一个对象的引用。
- element
  - id : 设置或者返回元素的 id。
  - className : 设置或返回元素的 class 属性
  - style : 设置或返回元素的样式属性
  - title : 设置或返回元素的 title 属性
  - getAttribute() : 返回指定元素的属性值
  - setAttribute() : 设置或者改变指定属性并指定值
  - innerHTML : 设置或者返回元素的内容
  - outerHTML : 设置或返回元素的全部内容包括标签部分
  - clientHeight : 在页面上返回内容的可视高度（不包括边框，边距或滚动条）
  - clientWidth : 在页面上返回内容的可视宽度（不包括边框，边距或滚动条）
  - scrollHeight : 返回整个元素的高度（包括带滚动条的隐蔽的地方）
  - scrollTop : 返回滚动的高度

### HTML BOM 对象

- window
  - alert() : 显示带有一段消息和一个确认按钮的警告框。
  - setInterval(函数,毫秒数) : 每隔一段时间执行函数
  - clearInterval(定时器对象) : 结束定时器
  - setTimeout(函数,毫秒数) : 一段时间后执行函数
  - clearTimeout(超时器对象) : 结束超时器
- location
  - href : 返回完整的 URL(直接使用 location 就相当于调用这个属性)
- history
  - back() : 加载 history 列表中的前一个 URL
  - forward() : 加载 history 列表中的下一个 URL
  - go() : 加载 history 列表中的某个具体页面
- screen
  - availHeight : 返回屏幕的高度（不包括 Windows 任务栏）
  - availWidth : 返回屏幕的宽度（不包括 Windows 任务栏）
  - height : 返回屏幕的总高度
  - width : 返回屏幕的总宽度
- navigator
  - userAgent : 返回由客户机发送服务器的 user-agent 头部的值

### AJAX 对象

- ActiveXObject
- XMLHttpRequest

## 常用全局方法

- parseInt() : 字符串转换整型
- eval() : 执行字符串表达式，如果是变量需要加上括号：eval("("+var+")")
- encodeURI(string)：对 URI 字符串进行 UTF-8 的编码

## 扩展

### ES5 数组新增方法

{{< card title="ES5中新增的Array方法详细说明"
url="https://www.zhangxinxu.com/wordpress/2013/04/es5%E6%96%B0%E5%A2%9E%E6%95%B0%E7%BB%84%E6%96%B9%E6%B3%95/"
description="ES5中新增的不少东西，了解之对我们写JavaScript会有不少帮助，比如数组这块，我们可能就不需要去有板有眼地for循环了">}}

#### 一、前言-索引

ES5 中新增的不少东西，了解之对我们写 JavaScript 会有不少帮助，比如数组这块，我们可能就不需要去有板有眼地`for`循环了。

ES5 中新增了写数组方法，如下：

1. [forEach](#foreach) (js v1.6)
2. [map](#map) (js v1.6)
3. [filter](#filter) (js v1.6)
4. [some](#some) (js v1.6)
5. [every](#every) (js v1.6)
6. [indexOf](#indexof) (js v1.6)
7. [lastIndexOf](#lastindexof) (js v1.6)
8. [reduce](#reduce) (js v1.8)
9. [reduceRight](#reduceright) (js v1.8)

**浏览器支持**

- Opera 11+
- Firefox 3.6+
- Safari 5+
- Chrome 8+
- Internet Explorer 9+

对于让人失望很多次的 IE6-IE8 浏览器，Array 原型扩展可以实现以上全部功能，例如`forEach`方法:

```javascript
// 对于古董浏览器，如IE6-IE8

if (typeof Array.prototype.forEach != "function") {
  Array.prototype.forEach = function () {
    /* 实现 */
  };
}
```

#### 二、一个一个来

##### forEach

`forEach` 是 Array 新方法中最基本的一个，就是遍历，循环。例如下面这个例子：

```js
[1, 2, 3, 4].forEach(alert);
```

等同于下面这个传统的`for`循环：

```js
var array = [1, 2, 3, 4];

for (var k = 0, length = array.length; k < length; k++) {
  alert(array[k]);
}
```

Array 在 ES5 新增的方法中，参数都是`function`类型，默认有传参，这些参数分别是？见下面：

```js
[1, 2, 3, 4].forEach(console.log);

// 结果：

// 1, 0, [1, 2, 3, 4]
// 2, 1, [1, 2, 3, 4]
// 3, 2, [1, 2, 3, 4]
// 4, 3, [1, 2, 3, 4]
```

![用来判断参数个数以及内容的测试输出截图 张鑫旭-鑫空间-鑫生活](https://image.zhangxinxu.com/image/blog/201304/2013-04-24_230237.png)

显而易见，`forEach`方法中的`function`回调支持 3 个参数，第 1 个是遍历的数组内容；第 2 个是对应的数组索引，第 3 个是数组本身。

因此，我们有：

```js
[].forEach(function (value, index, array) {
  // ...
});
```

对比 jQuery 中的`$.each`方法：

```javascript
$.each([], function (index, value, array) {
  // ...
});
```

会发现，第 1 个和第 2 个参数正好是相反的，大家要注意了，不要记错了。后面类似的方法，例如`$.map`也是如此。

现在，我们就可以使用`forEach`卖弄一个稍显完整的例子了，数组求和：

```js
var sum = 0;

[1, 2, 3, 4].forEach(function (item, index, array) {
  console.log(array[index] == item); // true
  sum += item;
});

alert(sum); // 10
```

再下面，更进一步，`forEach`除了接受一个必须的回调函数参数，还可以接受一个可选的上下文参数（改变回调函数里面的`this`指向）（第 2 个参数）。

```js
array.forEach(callback, [thisObject]);
```

例子更能说明一切：

```javascript
var database = {
  users: ["张含韵", "江一燕", "李小璐"],
  sendEmail: function (user) {
    if (this.isValidUser(user)) {
      console.log("你好，" + user);
    } else {
      console.log("抱歉，" + user + "，你不是本家人");
    }
  },
  isValidUser: function (user) {
    return /^张/.test(user);
  },
};

// 给每个人法邮件
database.users.forEach(
  // database.users中人遍历
  database.sendEmail, // 发送邮件
  database // 使用database代替上面标红的this
);

// 结果：
// 你好，张含韵
// 抱歉，江一燕，你不是本家人
// 抱歉，李小璐，你不是本家
```

如果这第 2 个可选参数不指定，则使用全局对象代替（在浏览器是为`window`），[严格模式](http://dmitrysoshnikov.com/ecmascript/es5-chapter-2-strict-mode/)下甚至是`undefined`.

另外，forEach 不会遍历纯粹“占着官位吃空饷”的元素的，例如下面这个例子：

```js
var array = [1, 2, 3];

delete array[1]; // 移除 2
alert(array); // "1,,3"

alert(array.length); // but the length is still 3

array.forEach(alert); // 弹出的仅仅是1和3
```

综上全部规则，我们就可以对 IE6-IE8 进行仿真扩展了，如下代码：

```javascript
// 对于古董浏览器，如IE6-IE8

if (typeof Array.prototype.forEach != "function") {
  Array.prototype.forEach = function (fn, context) {
    for (var k = 0, length = this.length; k < length; k++) {
      if (
        typeof fn === "function" &&
        Object.prototype.hasOwnProperty.call(this, k)
      ) {
        fn.call(context, this[k], k, this);
      }
    }
  };
}
```

现在拿上面“张含韵”的例子测下我们扩展的`forEach`方法，您可能狠狠地点击这里：[兼容处理的 forEach 方法 demo](http://www.zhangxinxu.com/study/201304/array-foreach.html)

例如 IE7 浏览器下：
![IE7下forEach方法测试结果截图 张鑫旭-鑫空间-鑫生活](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_102546.png)

##### map

这里的 `map` 不是“地图”的意思，而是指“映射”。

```
[].map();
```

基本用法跟 `forEach` 方法类似：

```js
array.map(callback, [thisObject]);
```

`callback`的参数也类似：

```js
[].map(function (value, index, array) {
  // ...
});
```

`map`方法的作用不难理解，“映射”嘛，也就是原数组被“映射”成对应新数组。下面这个例子是数值项求平方：

```js
var data = [1, 2, 3, 4];

var arrayOfSquares = data.map(function (item) {
  return item * item;
});

alert(arrayOfSquares); // 1, 4, 9, 16
```

`callback`需要有`return`值，如果没有，就像下面这样：

```javascript
var data = [1, 2, 3, 4];
var arrayOfSquares = data.map(function () {});

arrayOfSquares.forEach(console.log);
```

结果如下图，可以看到，数组所有项都被映射成了`undefined`：
![全部项都成了undefined ](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_105958.png)

在实际使用的时候，我们可以利用`map`方法方便获得对象数组中的特定属性值们。例如下面这个例子（之后的兼容 demo 也是该例子）：

```js
var users = [
  { name: "张含韵", email: "zhang@email.com" },
  { name: "江一燕", email: "jiang@email.com" },
  { name: "李小璐", email: "li@email.com" },
];

var emails = users.map(function (user) {
  return user.email;
});

console.log(emails.join(", ")); // zhang@email.com, jiang@email.com, li@email.com
```

`Array.prototype`扩展可以让 IE6-IE8 浏览器也支持`map`方法：

```javascript
if (typeof Array.prototype.map != "function") {
  Array.prototype.map = function (fn, context) {
    var arr = [];
    if (typeof fn === "function") {
      for (var k = 0, length = this.length; k < length; k++) {
        arr.push(fn.call(context, this[k], k, this));
      }
    }
    return arr;
  };
}
```

您可以狠狠地点击这里：[兼容 map 方法测试 demo](http://www.zhangxinxu.com/study/201304/array-map.html)

结果显示如下图，IE6 浏览器：
![map映射方法测试，IE6下截图](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_112441.png)

##### filter

`filter` 为“过滤”、“筛选”之意。指数组过滤后，返回过滤后的新数组。用法跟 `map` 极为相似：

```js
array.filter(callback, [thisObject]);
```

`filter`的`callback`函数需要返回布尔值`true`或`false`. 如果为`true`则表示，恭喜你，通过啦!如果为`false`, 只能高歌“我只能无情地将你抛弃……”)。

可能会疑问，一定要是`Boolean`值吗？我们可以简单测试下嘛，如下：

```javascript
var data = [0, 1, 2, 3];
var arrayFilter = data.filter(function (item) {
  return item;
});
console.log(arrayFilter); // [1, 2, 3]
```

有此可见，返回值只要是弱等于`== true/false`就可以了，而非非得返回 `=== true/false`.

因此，我们在为低版本浏览器扩展时候，无需关心是否返回值是否是纯粹布尔值（见下黑色代码部分）：

```javascript
if (typeof Array.prototype.filter != "function") {
  Array.prototype.filter = function (fn, context) {
    var arr = [];
    if (typeof fn === "function") {
      for (var k = 0, length = this.length; k < length; k++) {
        fn.call(context, this[k], k, this) && arr.push(this[k]);
      }
    }
    return arr;
  };
}
```

接着上面`map`筛选邮件的例子，您可以狠狠地点击这里：[兼容处理后 filter 方法测试 demo](http://www.zhangxinxu.com/study/201304/array-filter.html)

主要测试代码为：

```javascript
var emailsZhang = users
  // 获得邮件
  .map(function (user) {
    return user.email;
  })
  // 筛选出zhang开头的邮件
  .filter(function (email) {
    return /^zhang/.test(email);
  });

console.log(emailsZhang.join(", ")); // zhang@email.com
```

![filter demo页面的结果截图 张鑫旭-鑫空间-鑫生活](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_140442.png)

> 实际上，存在一些语法糖可以实现`map+filter`的效果，被称之为“数组简约式(Array comprehensions)”。目前，仅 FireFox 浏览器可以实现，展示下又不会怀孕：
>
> ```javascript
> var zhangEmails = [user.email for each (user in users) if (/^zhang/.test(user.email)) ];
>
> console.log(zhangEmails); // [zhang@email.com]
> ```
>
> ![数组简约式(Array comprehensions)实现的map+filter效果](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_141315.png)

##### some

`some` 意指“某些”，指是否“某些项”合乎条件。与下面的 `every` 算是好基友，`every` 表示是否“每一项”都要靠谱。用法如下：

```js
array.some(callback, [thisObject]);
```

例如下面的简单使用：

```javascript
var scores = [5, 8, 3, 10];
var current = 7;

function higherThanCurrent(score) {
  return score > current;
}

if (scores.some(higherThanCurrent)) {
  alert("朕准了！");
}
```

结果弹出了“朕准了”文字。 `some`要求至少有 1 个值让`callback`返回`true`就可以了。显然，`8 > 7`，因此`scores.some(higherThanCurrent)`值为`true`.

我们自然可以使用`forEach`进行判断，不过，相比`some`, 不足在于，`some`只有有`true`即返回不再执行了。

IE6-IE8 扩展如下：

```javascript
if (typeof Array.prototype.some != "function") {
  Array.prototype.some = function (fn, context) {
    var passed = false;
    if (typeof fn === "function") {
      for (var k = 0, length = this.length; k < length; k++) {
        if (passed === true) break;
        passed = !!fn.call(context, this[k], k, this);
      }
    }
    return passed;
  };
}
```

于是，我们就有了“朕准了”的 demo，您可以狠狠地点击这里：[兼容处理后的 some 方法 demo](http://www.zhangxinxu.com/study/201304/array-some.html)

![IE7浏览器下some扩展demo结果](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_160829.png)

##### every

跟 `some` 的基友关系已经是公开的秘密了，同样是返回 Boolean 值，不过，`every` 需要每一个妃子都要让朕满意，否则——“来人，给我拖出去砍了！”

IE6-IE8 扩展（与`some`相比就是`true`和`false`调换一下）：

```javascript
if (typeof Array.prototype.every != "function") {
  Array.prototype.every = function (fn, context) {
    var passed = true;
    if (typeof fn === "function") {
      for (var k = 0, length = this.length; k < length; k++) {
        if (passed === false) break;
        passed = !!fn.call(context, this[k], k, this);
      }
    }
    return passed;
  };
}
```

还是那个朕的例子，您可以狠狠地点击这里：[是否 every 妃子让朕满意 demo](http://www.zhangxinxu.com/study/201304/array-every.html)

```cpp
if (scores.every(higherThanCurrent)) {
  console.log("朕准了！");
} else {
  console.log("来人，拖出去斩了！");
}
```

结果是：
![every方法结果](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_163305.png)

##### indexOf

`indexOf` 方法在字符串中自古就有，

```
string.indexOf(searchString, position)
```

。数组这里的 `indexOf` 方法与之类似。

```js
array.indexOf(searchElement[, fromIndex])
```

返回整数索引值，如果没有匹配（严格匹配），返回`-1`. `fromIndex`可选，表示从这个位置开始搜索，若缺省或格式不合要求，使用默认值`0`，我在 FireFox 下测试，发现使用字符串数值也是可以的，例如`"3"`和`3`都可以。

```js
var data = [2, 5, 7, 3, 5];

console.log(data.indexOf(5, "x")); // 1 ("x"被忽略)
console.log(data.indexOf(5, "3")); // 4 (从3号位开始搜索)

console.log(data.indexOf(4)); // -1 (未找到)
console.log(data.indexOf("5")); // -1 (未找到，因为5 !== "5")
```

兼容处理如下：

```javascript
if (typeof Array.prototype.indexOf != "function") {
  Array.prototype.indexOf = function (searchElement, fromIndex) {
    var index = -1;
    fromIndex = fromIndex * 1 || 0;

    for (var k = 0, length = this.length; k < length; k++) {
      if (k >= fromIndex && this[k] === searchElement) {
        index = k;
        break;
      }
    }
    return index;
  };
}
```

一个路子下来的，显然，轮到 demo 了，您可以狠狠地点击这里：[兼容处理后 indexOf 方法测试 demo](http://www.zhangxinxu.com/study/201304/array-indexof.html)

下图为 ietester IE6 下的截图：
![IE6下indexOf扩展后测试结果截图](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_171244.png)

##### lastIndexOf

`lastIndexOf` 方法与 `indexOf` 方法类似：

```js
array.lastIndexOf(searchElement[, fromIndex])
```

只是`lastIndexOf`是从字符串的末尾开始查找，而不是从开头。还有一个不同就是`fromIndex`的默认值是`array.length - 1`而不是`0`.

IE6 等浏览器如下折腾：

```javascript
if (typeof Array.prototype.lastIndexOf != "function") {
  Array.prototype.lastIndexOf = function (searchElement, fromIndex) {
    var index = -1,
      length = this.length;
    fromIndex = fromIndex * 1 || length - 1;

    for (var k = length - 1; k > -1; k -= 1) {
      if (k <= fromIndex && this[k] === searchElement) {
        index = k;
        break;
      }
    }
    return index;
  };
}
```

于是，则有：

```js
var data = [2, 5, 7, 3, 5];

console.log(data.lastIndexOf(5)); // 4
console.log(data.lastIndexOf(5, 3)); // 1 (从后往前，索引值小于3的开始搜索)

console.log(data.lastIndexOf(4)); // -1 (未找到)
```

懒得截图了，结果查看可狠狠地点击这里：[lastIndexOf 测试 demo](http://www.zhangxinxu.com/study/201304/array-lastindexof.html)

##### reduce

`reduce` 是 JavaScript 1.8 中才引入的，中文意思为“减少”、“约简”。不过，从功能来看，我个人是无法与“减少”这种含义联系起来的，反而更接近于“迭代”、“递归(recursion)”，擦，因为单词这么接近，不会是 ECMA-262 5th 制定者笔误写错了吧~~

此方法相比上面的方法都复杂，用法如下：

```js
array.reduce(callback[, initialValue])
```

`callback`函数接受 4 个参数：之前值、当前值、索引值以及数组本身。`initialValue`参数可选，表示初始值。若指定，则当作最初使用的`previous`值；如果缺省，则使用数组的第一个元素作为`previous`初始值，同时`current`往后排一位，相比有`initialValue`值少一次迭代。

```javascript
var sum = [1, 2, 3, 4].reduce(function (previous, current, index, array) {
  return previous + current;
});

console.log(sum); // 10
```

说明：

1.  因为`initialValue`不存在，因此一开始的`previous`值等于数组的第一个元素。
2.  从而`current`值在第一次调用的时候就是`2`.
3.  最后两个参数为索引值`index`以及数组本身`array`.

以下为循环执行过程：

```javascript
// 初始设置
previous = initialValue = 1, current = 2

// 第一次迭代
previous = (1 + 2) =  3, current = 3

// 第二次迭代
previous = (3 + 3) =  6, current = 4

// 第三次迭代
previous = (6 + 4) =  10, current = undefined (退出)
```

有了`reduce`，我们可以轻松实现二维数组的扁平化：

```js
var matrix = [
  [1, 2],
  [3, 4],
  [5, 6],
];

// 二维数组扁平化
var flatten = matrix.reduce(function (previous, current) {
  return previous.concat(current);
});

console.log(flatten); // [1, 2, 3, 4, 5, 6]
```

兼容处理 IE6-IE8：

```javascript
if (typeof Array.prototype.reduce != "function") {
  Array.prototype.reduce = function (callback, initialValue) {
    var previous = initialValue,
      k = 0,
      length = this.length;
    if (typeof initialValue === "undefined") {
      previous = this[0];
      k = 1;
    }

    if (typeof callback === "function") {
      for (k; k < length; k++) {
        this.hasOwnProperty(k) &&
          (previous = callback(previous, this[k], k, this));
      }
    }
    return previous;
  };
}
```

然后，测试整合，demo 演示，您可以狠狠地点击这里：[兼容 IE6 的 reduce 方法测试 demo](http://www.zhangxinxu.com/study/201304/array-reduce.html)

IE6 浏览器下结果如下图：
![reduce方法测试页面结构示意](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_191415.png)

##### reduceRight

`reduceRight` 跟 `reduce` 相比，用法类似：

```js
array.reduceRight(callback[, initialValue])
```

实现上差异在于`reduceRight`是从数组的末尾开始实现。看下面这个例子：

```js
var data = [1, 2, 3, 4];
var specialDiff = data.reduceRight(function (previous, current, index) {
  if (index == 0) {
    return previous + current;
  }
  return previous - current;
});

console.log(specialDiff); // 0
```

结果`0`是如何得到的呢？
我们一步一步查看循环执行：

```javascript
// 初始设置
index = 3, previous = initialValue = 4, current = 3

// 第一次迭代
index = 2, previous = (4- 3) = 1, current = 2

// 第二次迭代
index = 1, previous = (1 - 2) = -1, current = 1

// 第三次迭代
index = 0, previous = (-1 + 1) = 0, current = undefined (退出)
```

为使低版本浏览器支持此方法，您可以添加如下代码：

```javascript
if (typeof Array.prototype.reduceRight != "function") {
  Array.prototype.reduceRight = function (callback, initialValue) {
    var length = this.length,
      k = length - 1,
      previous = initialValue;
    if (typeof initialValue === "undefined") {
      previous = this[length - 1];
      k--;
    }
    if (typeof callback === "function") {
      for (k; k > -1; k -= 1) {
        this.hasOwnProperty(k) &&
          (previous = callback(previous, this[k], k, this));
      }
    }
    return previous;
  };
}
```

您可以狠狠地点击这里：[reduceRight 简单使用 demo](http://www.zhangxinxu.com/study/201304/array-reduceright.html)

对比 FireFox 浏览器和 IE7 浏览器下的结果：
![FireFox浏览器下reduceRight测试结果](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_205011.png) ![对比IE7下reduceRight测试结果截图 张鑫旭-鑫空间-鑫生活](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_205035.png)

#### 三、更进一步的应用

我们还可以将上面这些数组方法应用在其他对象上。

例如，我们使用 forEach 遍历 DOM 元素。

```javascript
var eleDivs = document.getElementsByTagName("div");
Array.prototype.forEach.call(eleDivs, function (div) {
  console.log("该div类名是：" + (div.className || "空"));
});
```

可以输出页面所有`div`的类名，您可以狠狠地点击这里：[Array 新方法 forEach 遍历 DOM demo](http://www.zhangxinxu.com/study/201304/array-foreach-dom-loop.html)

结果如下，IE6 下，demo 结果：
![forEach方法遍历DOM的使用演示 张鑫旭-鑫空间-鑫生活](https://image.zhangxinxu.com/image/blog/201304/2013-04-25_213419.png)

等很多其他类数组应用。

#### 四、最后一点点了

本文为低版本 IE 扩展的 Array 方法我都合并到一个 JS 中了，您可以轻轻的右键这里或下载或查看：[es5-array.js](http://www.zhangxinxu.com/study/201304/es5-array.js)

以上所有未 IE 扩展的方法都是自己根据理解写的，虽然多番测试，难免还会有细节遗漏的，欢迎指出来。

### ES6

{{< card "https://es6.ruanyifeng.com/" >}}

#### let 和 const

##### let 命令

###### 基本用法

ES6 新增了`let`命令，用来声明变量。它的用法类似于`var`，但是所声明的变量，只在`let`命令所在的代码块内有效。

```javascript
{
  let a = 10;
  var b = 1;
}

a; // ReferenceError: a is not defined.
b; // 1
```

上面代码在代码块之中，分别用`let`和`var`声明了两个变量。然后在代码块之外调用这两个变量，结果`let`声明的变量报错，`var`声明的变量返回了正确的值。这表明，`let`声明的变量只在它所在的代码块有效。

`for`循环的计数器，就很合适使用`let`命令。

```javascript
for (let i = 0; i < 10; i++) {
  // ...
}

console.log(i);
// ReferenceError: i is not defined
```

上面代码中，计数器`i`只在`for`循环体内有效，在循环体外引用就会报错。

下面的代码如果使用`var`，最后输出的是`10`。

```javascript
var a = [];
for (var i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 10
```

上面代码中，变量`i`是`var`命令声明的，在全局范围内都有效，所以全局只有一个变量`i`。每一次循环，变量`i`的值都会发生改变，而循环内被赋给数组`a`的函数内部的`console.log(i)`，里面的`i`指向的就是全局的`i`。也就是说，所有数组`a`的成员里面的`i`，指向的都是同一个`i`，导致运行时输出的是最后一轮的`i`的值，也就是 10。

如果使用`let`，声明的变量仅在块级作用域内有效，最后输出的是 6。

```javascript
var a = [];
for (let i = 0; i < 10; i++) {
  a[i] = function () {
    console.log(i);
  };
}
a[6](); // 6
```

上面代码中，变量`i`是`let`声明的，当前的`i`只在本轮循环有效，所以每一次循环的`i`其实都是一个新的变量，所以最后输出的是`6`。你可能会问，如果每一轮循环的变量`i`都是重新声明的，那它怎么知道上一轮循环的值，从而计算出本轮循环的值？这是因为 JavaScript 引擎内部会记住上一轮循环的值，初始化本轮的变量`i`时，就在上一轮循环的基础上进行计算。

另外，`for`循环还有一个特别之处，就是设置循环变量的那部分是一个父作用域，而循环体内部是一个单独的子作用域。

```javascript
for (let i = 0; i < 3; i++) {
  let i = "abc";
  console.log(i);
}
// abc
// abc
// abc
```

上面代码正确运行，输出了 3 次`abc`。这表明函数内部的变量`i`与循环变量`i`不在同一个作用域，有各自单独的作用域（同一个作用域不可使用 `let` 重复声明同一个变量）。

###### 不存在变量提升

`var`命令会发生“变量提升”现象，即变量可以在声明之前使用，值为`undefined`。这种现象多多少少是有些奇怪的，按照一般的逻辑，变量应该在声明语句之后才可以使用。

为了纠正这种现象，`let`命令改变了语法行为，它所声明的变量一定要在声明后使用，否则报错。

```javascript
// var 的情况
console.log(foo); // 输出undefined
var foo = 2;

// let 的情况
console.log(bar); // 报错ReferenceError
let bar = 2;
```

上面代码中，变量`foo`用`var`命令声明，会发生变量提升，即脚本开始运行时，变量`foo`已经存在了，但是没有值，所以会输出`undefined`。变量`bar`用`let`命令声明，不会发生变量提升。这表示在声明它之前，变量`bar`是不存在的，这时如果用到它，就会抛出一个错误。

###### 暂时性死区

只要块级作用域内存在`let`命令，它所声明的变量就“绑定”（binding）这个区域，不再受外部的影响。

```javascript
var tmp = 123;

if (true) {
  tmp = "abc"; // ReferenceError
  let tmp;
}
```

上面代码中，存在全局变量`tmp`，但是块级作用域内`let`又声明了一个局部变量`tmp`，导致后者绑定这个块级作用域，所以在`let`声明变量前，对`tmp`赋值会报错。

ES6 明确规定，如果区块中存在`let`和`const`命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。

总之，在代码块内，使用`let`命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”（temporal dead zone，简称 TDZ）。

```javascript
if (true) {
  // TDZ开始
  tmp = "abc"; // ReferenceError
  console.log(tmp); // ReferenceError

  let tmp; // TDZ结束
  console.log(tmp); // undefined

  tmp = 123;
  console.log(tmp); // 123
}
```

上面代码中，在`let`命令声明变量`tmp`之前，都属于变量`tmp`的“死区”。

“暂时性死区”也意味着`typeof`不再是一个百分之百安全的操作。

```javascript
typeof x; // ReferenceError
let x;
```

上面代码中，变量`x`使用`let`命令声明，所以在声明之前，都属于`x`的“死区”，只要用到该变量就会报错。因此，`typeof`运行时就会抛出一个`ReferenceError`。

作为比较，如果一个变量根本没有被声明，使用`typeof`反而不会报错。

```javascript
typeof undeclared_variable; // "undefined"
```

上面代码中，`undeclared_variable`是一个不存在的变量名，结果返回“undefined”。所以，在没有`let`之前，`typeof`运算符是百分之百安全的，永远不会报错。现在这一点不成立了。这样的设计是为了让大家养成良好的编程习惯，变量一定要在声明之后使用，否则就报错。

有些“死区”比较隐蔽，不太容易发现。

```javascript
function bar(x = y, y = 2) {
  return [x, y];
}

bar(); // 报错
```

上面代码中，调用`bar`函数之所以报错（某些实现可能不报错），是因为参数`x`默认值等于另一个参数`y`，而此时`y`还没有声明，属于“死区”。如果`y`的默认值是`x`，就不会报错，因为此时`x`已经声明了。

```javascript
function bar(x = 2, y = x) {
  return [x, y];
}
bar(); // [2, 2]
```

另外，下面的代码也会报错，与`var`的行为不同。

```javascript
// 不报错
var x = x;

// 报错
let x = x;
// ReferenceError: x is not defined
```

上面代码报错，也是因为暂时性死区。使用`let`声明变量时，只要变量在还没有声明完成前使用，就会报错。上面这行就属于这个情况，在变量`x`的声明语句还没有执行完成前，就去取`x`的值，导致报错”x 未定义“。

ES6 规定暂时性死区和`let`、`const`语句不出现变量提升，主要是为了减少运行时错误，防止在变量声明前就使用这个变量，从而导致意料之外的行为。这样的错误在 ES5 是很常见的，现在有了这种规定，避免此类错误就很容易了。

总之，暂时性死区的本质就是，只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量。

###### 不允许重复声明

`let`不允许在相同作用域内，重复声明同一个变量。

```javascript
// 报错
function func() {
  let a = 10;
  var a = 1;
}

// 报错
function func() {
  let a = 10;
  let a = 1;
}
```

因此，不能在函数内部重新声明参数。

```javascript
function func(arg) {
  let arg;
}
func(); // 报错

function func(arg) {
  {
    let arg;
  }
}
func(); // 不报错
```

##### 块级作用域

###### 为什么需要块级作用域？

ES5 只有全局作用域和函数作用域，没有块级作用域，这带来很多不合理的场景。

第一种场景，内层变量可能会覆盖外层变量。

```javascript
var tmp = new Date();

function f() {
  console.log(tmp);
  if (false) {
    var tmp = "hello world";
  }
}

f(); // undefined
```

上面代码的原意是，`if`代码块的外部使用外层的`tmp`变量，内部使用内层的`tmp`变量。但是，函数`f`执行后，输出结果为`undefined`，原因在于变量提升，导致内层的`tmp`变量覆盖了外层的`tmp`变量。

第二种场景，用来计数的循环变量泄露为全局变量。

```javascript
var s = "hello";

for (var i = 0; i < s.length; i++) {
  console.log(s[i]);
}

console.log(i); // 5
```

上面代码中，变量`i`只用来控制循环，但是循环结束后，它并没有消失，泄露成了全局变量。

###### ES6 的块级作用域

`let`实际上为 JavaScript 新增了块级作用域。

```javascript
function f1() {
  let n = 5;
  if (true) {
    let n = 10;
  }
  console.log(n); // 5
}
```

上面的函数有两个代码块，都声明了变量`n`，运行后输出 5。这表示外层代码块不受内层代码块的影响。如果两次都使用`var`定义变量`n`，最后输出的值才是 10。

ES6 允许块级作用域的任意嵌套。

```javascript
{
  {
    {
      {
        {
          let insane = "Hello World";
        }
        console.log(insane); // 报错
      }
    }
  }
}
```

上面代码使用了一个五层的块级作用域，每一层都是一个单独的作用域。第四层作用域无法读取第五层作用域的内部变量。

内层作用域可以定义外层作用域的同名变量。

```javascript
{
  {
    {
      {
        let insane = "Hello World";
        {
          let insane = "Hello World";
        }
      }
    }
  }
}
```

块级作用域的出现，实际上使得获得广泛应用的匿名立即执行函数表达式（匿名 IIFE）不再必要了。

```javascript
// IIFE 写法
(function () {
  var tmp = ...;
  ...
}());

// 块级作用域写法
{
  let tmp = ...;
  ...
}
```

###### 块级作用域与函数声明

函数能不能在块级作用域之中声明？这是一个相当令人混淆的问题。

ES5 规定，函数只能在顶层作用域和函数作用域之中声明，不能在块级作用域声明。

```javascript
// 情况一
if (true) {
  function f() {}
}

// 情况二
try {
  function f() {}
} catch (e) {
  // ...
}
```

上面两种函数声明，根据 ES5 的规定都是非法的。

但是，浏览器没有遵守这个规定，为了兼容以前的旧代码，还是支持在块级作用域之中声明函数，因此上面两种情况实际都能运行，不会报错。

ES6 引入了块级作用域，明确允许在块级作用域之中声明函数。ES6 规定，块级作用域之中，函数声明语句的行为类似于`let`，在块级作用域之外不可引用。

```javascript
function f() {
  console.log("I am outside!");
}

(function () {
  if (false) {
    // 重复声明一次函数f
    function f() {
      console.log("I am inside!");
    }
  }

  f();
})();
```

上面代码在 ES5 中运行，会得到“I am inside!”，因为在`if`内声明的函数`f`会被提升到函数头部，实际运行的代码如下。

```javascript
// ES5 环境
function f() {
  console.log("I am outside!");
}

(function () {
  function f() {
    console.log("I am inside!");
  }
  if (false) {
  }
  f();
})();
```

ES6 就完全不一样了，理论上会得到“I am outside!”。因为块级作用域内声明的函数类似于`let`，对作用域之外没有影响。但是，如果你真的在 ES6 浏览器中运行一下上面的代码，是会报错的，这是为什么呢？

```javascript
// 浏览器的 ES6 环境
function f() {
  console.log("I am outside!");
}

(function () {
  if (false) {
    // 重复声明一次函数f
    function f() {
      console.log("I am inside!");
    }
  }

  f();
})();
// Uncaught TypeError: f is not a function
```

上面的代码在 ES6 浏览器中，都会报错。

原来，如果改变了块级作用域内声明的函数的处理规则，显然会对老代码产生很大影响。为了减轻因此产生的不兼容问题，ES6 在[附录 B](https://www.ecma-international.org/ecma-262/6.0/index.html#sec-block-level-function-declarations-web-legacy-compatibility-semantics)里面规定，浏览器的实现可以不遵守上面的规定，有自己的[行为方式](https://stackoverflow.com/questions/31419897/what-are-the-precise-semantics-of-block-level-functions-in-es6)。

- 允许在块级作用域内声明函数。
- 函数声明类似于`var`，即会提升到全局作用域或函数作用域的头部。
- 同时，函数声明还会提升到所在的块级作用域的头部。

注意，上面三条规则只对 ES6 的浏览器实现有效，其他环境的实现不用遵守，还是将块级作用域的函数声明当作`let`处理。

根据这三条规则，浏览器的 ES6 环境中，块级作用域内声明的函数，行为类似于`var`声明的变量。上面的例子实际运行的代码如下。

```javascript
// 浏览器的 ES6 环境
function f() {
  console.log("I am outside!");
}
(function () {
  var f = undefined;
  if (false) {
    function f() {
      console.log("I am inside!");
    }
  }

  f();
})();
// Uncaught TypeError: f is not a function
```

考虑到环境导致的行为差异太大，应该避免在块级作用域内声明函数。如果确实需要，也应该写成函数表达式，而不是函数声明语句。

```javascript
// 块级作用域内部的函数声明语句，建议不要使用
{
  let a = "secret";
  function f() {
    return a;
  }
}

// 块级作用域内部，优先使用函数表达式
{
  let a = "secret";
  let f = function () {
    return a;
  };
}
```

另外，还有一个需要注意的地方。ES6 的块级作用域必须有大括号，如果没有大括号，JavaScript 引擎就认为不存在块级作用域。

```javascript
// 第一种写法，报错
if (true) let x = 1;

// 第二种写法，不报错
if (true) {
  let x = 1;
}
```

上面代码中，第一种写法没有大括号，所以不存在块级作用域，而`let`只能出现在当前作用域的顶层，所以报错。第二种写法有大括号，所以块级作用域成立。

函数声明也是如此，严格模式下，函数只能声明在当前作用域的顶层。

```javascript
// 不报错
'use strict';
if (true) {
  function f() {}
}

// 报错
'use strict';
if (true)
  function f() {}
```

##### const 命令

###### 基本用法

`const`声明一个只读的常量。一旦声明，常量的值就不能改变。

```javascript
const PI = 3.1415;
PI; // 3.1415

PI = 3;
// TypeError: Assignment to constant variable.
```

上面代码表明改变常量的值会报错。

`const`声明的变量不得改变值，这意味着，`const`一旦声明变量，就必须立即初始化，不能留到以后赋值。

```javascript
const foo;
// SyntaxError: Missing initializer in const declaration
```

上面代码表示，对于`const`来说，只声明不赋值，就会报错。

`const`的作用域与`let`命令相同：只在声明所在的块级作用域内有效。

```javascript
if (true) {
  const MAX = 5;
}

MAX; // Uncaught ReferenceError: MAX is not defined
```

`const`命令声明的常量也是不提升，同样存在暂时性死区，只能在声明的位置后面使用。

```javascript
if (true) {
  console.log(MAX); // ReferenceError
  const MAX = 5;
}
```

上面代码在常量`MAX`声明之前就调用，结果报错。

`const`声明的常量，也与`let`一样不可重复声明。

```javascript
var message = "Hello!";
let age = 25;

// 以下两行都会报错
const message = "Goodbye!";
const age = 30;
```

###### 本质

`const`实际上保证的，并不是变量的值不得改动，而是变量指向的那个内存地址所保存的数据不得改动。对于简单类型的数据（数值、字符串、布尔值），值就保存在变量指向的那个内存地址，因此等同于常量。但对于复合类型的数据（主要是对象和数组），变量指向的内存地址，保存的只是一个指向实际数据的指针，`const`只能保证这个指针是固定的（即总是指向另一个固定的地址），至于它指向的数据结构是不是可变的，就完全不能控制了。因此，将一个对象声明为常量必须非常小心。

```javascript
const foo = {};

// 为 foo 添加一个属性，可以成功
foo.prop = 123;
foo.prop; // 123

// 将 foo 指向另一个对象，就会报错
foo = {}; // TypeError: "foo" is read-only
```

上面代码中，常量`foo`储存的是一个地址，这个地址指向一个对象。不可变的只是这个地址，即不能把`foo`指向另一个地址，但对象本身是可变的，所以依然可以为其添加新属性。

下面是另一个例子。

```javascript
const a = [];
a.push("Hello"); // 可执行
a.length = 0; // 可执行
a = ["Dave"]; // 报错
```

上面代码中，常量`a`是一个数组，这个数组本身是可写的，但是如果将另一个数组赋值给`a`，就会报错。

如果真的想将对象冻结，应该使用`Object.freeze`方法。

```javascript
const foo = Object.freeze({});

// 常规模式时，下面一行不起作用；
// 严格模式时，该行会报错
foo.prop = 123;
```

上面代码中，常量`foo`指向一个冻结的对象，所以添加新属性不起作用，严格模式时还会报错。

除了将对象本身冻结，对象的属性也应该冻结。下面是一个将对象彻底冻结的函数。

```javascript
var constantize = (obj) => {
  Object.freeze(obj);
  Object.keys(obj).forEach((key, i) => {
    if (typeof obj[key] === "object") {
      constantize(obj[key]);
    }
  });
};
```

###### ES6 声明变量的六种方法

ES5 只有两种声明变量的方法：`var`命令和`function`命令。ES6 除了添加`let`和`const`命令，后面章节还会提到，另外两种声明变量的方法：`import`命令和`class`命令。所以，ES6 一共有 6 种声明变量的方法。

##### 顶层对象的属性

顶层对象，在浏览器环境指的是`window`对象，在 Node 指的是`global`对象。ES5 之中，顶层对象的属性与全局变量是等价的。

```javascript
window.a = 1;
a; // 1

a = 2;
window.a; // 2
```

上面代码中，顶层对象的属性赋值与全局变量的赋值，是同一件事。

顶层对象的属性与全局变量挂钩，被认为是 JavaScript 语言最大的设计败笔之一。这样的设计带来了几个很大的问题，首先是没法在编译时就报出变量未声明的错误，只有运行时才能知道（因为全局变量可能是顶层对象的属性创造的，而属性的创造是动态的）；其次，程序员很容易不知不觉地就创建了全局变量（比如打字出错）；最后，顶层对象的属性是到处可以读写的，这非常不利于模块化编程。另一方面，`window`对象有实体含义，指的是浏览器的窗口对象，顶层对象是一个有实体含义的对象，也是不合适的。

ES6 为了改变这一点，一方面规定，为了保持兼容性，`var`命令和`function`命令声明的全局变量，依旧是顶层对象的属性；另一方面规定，`let`命令、`const`命令、`class`命令声明的全局变量，不属于顶层对象的属性。也就是说，从 ES6 开始，全局变量将逐步与顶层对象的属性脱钩。

```javascript
var a = 1;
// 如果在 Node 的 REPL 环境，可以写成 global.a
// 或者采用通用方法，写成 this.a
window.a; // 1

let b = 1;
window.b; // undefined
```

上面代码中，全局变量`a`由`var`命令声明，所以它是顶层对象的属性；全局变量`b`由`let`命令声明，所以它不是顶层对象的属性，返回`undefined`。

##### globalThis 对象

JavaScript 语言存在一个顶层对象，它提供全局环境（即全局作用域），所有代码都是在这个环境中运行。但是，顶层对象在各种实现里面是不统一的。

- 浏览器里面，顶层对象是`window`，但 Node 和 Web Worker 没有`window`。
- 浏览器和 Web Worker 里面，`self`也指向顶层对象，但是 Node 没有`self`。
- Node 里面，顶层对象是`global`，但其他环境都不支持。

同一段代码为了能够在各种环境，都能取到顶层对象，现在一般是使用`this`关键字，但是有局限性。

- 全局环境中，`this`会返回顶层对象。但是，Node.js 模块中`this`返回的是当前模块，ES6 模块中`this`返回的是`undefined`。
- 函数里面的`this`，如果函数不是作为对象的方法运行，而是单纯作为函数运行，`this`会指向顶层对象。但是，严格模式下，这时`this`会返回`undefined`。
- 不管是严格模式，还是普通模式，`new Function('return this')()`，总是会返回全局对象。但是，如果浏览器用了 CSP（Content Security Policy，内容安全策略），那么`eval`、`new Function`这些方法都可能无法使用。

综上所述，很难找到一种方法，可以在所有情况下，都取到顶层对象。下面是两种勉强可以使用的方法。

```javascript
// 方法一
typeof window !== "undefined"
  ? window
  : typeof process === "object" &&
    typeof require === "function" &&
    typeof global === "object"
  ? global
  : this;

// 方法二
var getGlobal = function () {
  if (typeof self !== "undefined") {
    return self;
  }
  if (typeof window !== "undefined") {
    return window;
  }
  if (typeof global !== "undefined") {
    return global;
  }
  throw new Error("unable to locate global object");
};
```

[ES2020](https://github.com/tc39/proposal-global) 在语言标准的层面，引入`globalThis`作为顶层对象。也就是说，任何环境下，`globalThis`都是存在的，都可以从它拿到顶层对象，指向全局环境下的`this`。

垫片库[`global-this`](https://github.com/ungap/global-this)模拟了这个提案，可以在所有环境拿到`globalThis`。

#### 解构赋值

##### 数组的解构赋值

###### 基本用法

ES6 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring）。

以前，为变量赋值，只能直接指定值。

```javascript
let a = 1;
let b = 2;
let c = 3;
```

ES6 允许写成下面这样。

```javascript
let [a, b, c] = [1, 2, 3];
```

上面代码表示，可以从数组中提取值，按照对应位置，对变量赋值。

本质上，这种写法属于“模式匹配”，只要等号两边的模式相同，左边的变量就会被赋予对应的值。下面是一些使用嵌套数组进行解构的例子。

```javascript
let [foo, [[bar], baz]] = [1, [[2], 3]];
foo; // 1
bar; // 2
baz; // 3

let [, , third] = ["foo", "bar", "baz"];
third; // "baz"

let [x, , y] = [1, 2, 3];
x; // 1
y; // 3

let [head, ...tail] = [1, 2, 3, 4];
head; // 1
tail; // [2, 3, 4]

let [x, y, ...z] = ["a"];
x; // "a"
y; // undefined
z; // []
```

如果解构不成功，变量的值就等于`undefined`。

```javascript
let [foo] = [];
let [bar, foo] = [1];
```

以上两种情况都属于解构不成功，`foo`的值都会等于`undefined`。

另一种情况是不完全解构，即等号左边的模式，只匹配一部分的等号右边的数组。这种情况下，解构依然可以成功。

```javascript
let [x, y] = [1, 2, 3];
x; // 1
y; // 2

let [a, [b], d] = [1, [2, 3], 4];
a; // 1
b; // 2
d; // 4
```

上面两个例子，都属于不完全解构，但是可以成功。

如果等号的右边不是数组（或者严格地说，不是可遍历的结构，参见《Iterator》一章），那么将会报错。

```javascript
// 报错
let [foo] = 1;
let [foo] = false;
let [foo] = NaN;
let [foo] = undefined;
let [foo] = null;
let [foo] = {};
```

上面的语句都会报错，因为等号右边的值，要么转为对象以后不具备 Iterator 接口（前五个表达式），要么本身就不具备 Iterator 接口（最后一个表达式）。

对于 Set 结构，也可以使用数组的解构赋值。

```javascript
let [x, y, z] = new Set(["a", "b", "c"]);
x; // "a"
```

事实上，只要某种数据结构具有 Iterator 接口，都可以采用数组形式的解构赋值。

```javascript
function* fibs() {
  let a = 0;
  let b = 1;
  while (true) {
    yield a;
    [a, b] = [b, a + b];
  }
}

let [first, second, third, fourth, fifth, sixth] = fibs();
sixth; // 5
```

上面代码中，`fibs`是一个 Generator 函数（参见《Generator 函数》一章），原生具有 Iterator 接口。解构赋值会依次从这个接口获取值。

###### 默认值

解构赋值允许指定默认值。

```javascript
let [foo = true] = [];
foo; // true

let [x, y = "b"] = ["a"]; // x='a', y='b'
let [x, y = "b"] = ["a", undefined]; // x='a', y='b'
```

注意，ES6 内部使用严格相等运算符（`===`），判断一个位置是否有值。所以，只有当一个数组成员严格等于`undefined`，默认值才会生效。

```javascript
let [x = 1] = [undefined];
x; // 1

let [x = 1] = [null];
x; // null
```

上面代码中，如果一个数组成员是`null`，默认值就不会生效，因为`null`不严格等于`undefined`。

如果默认值是一个表达式，那么这个表达式是惰性求值的，即只有在用到的时候，才会求值。

```javascript
function f() {
  console.log("aaa");
}

let [x = f()] = [1];
```

上面代码中，因为`x`能取到值，所以函数`f`根本不会执行。上面的代码其实等价于下面的代码。

```javascript
let x;
if ([1][0] === undefined) {
  x = f();
} else {
  x = [1][0];
}
```

默认值可以引用解构赋值的其他变量，但该变量必须已经声明。

```javascript
let [x = 1, y = x] = []; // x=1; y=1
let [x = 1, y = x] = [2]; // x=2; y=2
let [x = 1, y = x] = [1, 2]; // x=1; y=2
let [x = y, y = 1] = []; // ReferenceError: y is not defined
```

上面最后一个表达式之所以会报错，是因为`x`用`y`做默认值时，`y`还没有声明。

##### 对象的解构赋值

###### 简介

解构不仅可以用于数组，还可以用于对象。

```javascript
let { foo, bar } = { foo: "aaa", bar: "bbb" };
foo; // "aaa"
bar; // "bbb"
```

对象的解构与数组有一个重要的不同。数组的元素是按次序排列的，变量的取值由它的位置决定；而对象的属性没有次序，变量必须与属性同名，才能取到正确的值。

```javascript
let { bar, foo } = { foo: "aaa", bar: "bbb" };
foo; // "aaa"
bar; // "bbb"

let { baz } = { foo: "aaa", bar: "bbb" };
baz; // undefined
```

上面代码的第一个例子，等号左边的两个变量的次序，与等号右边两个同名属性的次序不一致，但是对取值完全没有影响。第二个例子的变量没有对应的同名属性，导致取不到值，最后等于`undefined`。

如果解构失败，变量的值等于`undefined`。

```javascript
let { foo } = { bar: "baz" };
foo; // undefined
```

上面代码中，等号右边的对象没有`foo`属性，所以变量`foo`取不到值，所以等于`undefined`。

对象的解构赋值，可以很方便地将现有对象的方法，赋值到某个变量。

```javascript
// 例一
let { log, sin, cos } = Math;

// 例二
const { log } = console;
log("hello"); // hello
```

上面代码的例一将`Math`对象的对数、正弦、余弦三个方法，赋值到对应的变量上，使用起来就会方便很多。例二将`console.log`赋值到`log`变量。

如果变量名与属性名不一致，必须写成下面这样。

```javascript
let { foo: baz } = { foo: "aaa", bar: "bbb" };
baz; // "aaa"

let obj = { first: "hello", last: "world" };
let { first: f, last: l } = obj;
f; // 'hello'
l; // 'world'
```

这实际上说明，对象的解构赋值是下面形式的简写（参见《对象的扩展》一章）。

```javascript
let { foo: foo, bar: bar } = { foo: "aaa", bar: "bbb" };
```

也就是说，对象的解构赋值的内部机制，是先找到同名属性，然后再赋给对应的变量。真正被赋值的是后者，而不是前者。

```javascript
let { foo: baz } = { foo: "aaa", bar: "bbb" };
baz; // "aaa"
foo; // error: foo is not defined
```

上面代码中，`foo`是匹配的模式，`baz`才是变量。真正被赋值的是变量`baz`，而不是模式`foo`。

与数组一样，解构也可以用于嵌套结构的对象。

```javascript
let obj = {
  p: ["Hello", { y: "World" }],
};

let {
  p: [x, { y }],
} = obj;
x; // "Hello"
y; // "World"
```

注意，这时`p`是模式，不是变量，因此不会被赋值。如果`p`也要作为变量赋值，可以写成下面这样。

```javascript
let obj = {
  p: ["Hello", { y: "World" }],
};

let {
  p,
  p: [x, { y }],
} = obj;
x; // "Hello"
y; // "World"
p; // ["Hello", {y: "World"}]
```

下面是另一个例子。

```javascript
const node = {
  loc: {
    start: {
      line: 1,
      column: 5,
    },
  },
};

let {
  loc,
  loc: { start },
  loc: {
    start: { line },
  },
} = node;
line; // 1
loc; // Object {start: Object}
start; // Object {line: 1, column: 5}
```

上面代码有三次解构赋值，分别是对`loc`、`start`、`line`三个属性的解构赋值。注意，最后一次对`line`属性的解构赋值之中，只有`line`是变量，`loc`和`start`都是模式，不是变量。

下面是嵌套赋值的例子。

```javascript
let obj = {};
let arr = [];

({ foo: obj.prop, bar: arr[0] } = { foo: 123, bar: true });

obj; // {prop:123}
arr; // [true]
```

如果解构模式是嵌套的对象，而且子对象所在的父属性不存在，那么将会报错。

```javascript
// 报错
let {
  foo: { bar },
} = { baz: "baz" };
```

上面代码中，等号左边对象的`foo`属性，对应一个子对象。该子对象的`bar`属性，解构时会报错。原因很简单，因为`foo`这时等于`undefined`，再取子属性就会报错。

注意，对象的解构赋值可以取到继承的属性。

```javascript
const obj1 = {};
const obj2 = { foo: "bar" };
Object.setPrototypeOf(obj1, obj2);

const { foo } = obj1;
foo; // "bar"
```

上面代码中，对象`obj1`的原型对象是`obj2`。`foo`属性不是`obj1`自身的属性，而是继承自`obj2`的属性，解构赋值可以取到这个属性。

###### 默认值

对象的解构也可以指定默认值。

```javascript
var { x = 3 } = {};
x; // 3

var { x, y = 5 } = { x: 1 };
x; // 1
y; // 5

var { x: y = 3 } = {};
y; // 3

var { x: y = 3 } = { x: 5 };
y; // 5

var { message: msg = "Something went wrong" } = {};
msg; // "Something went wrong"
```

默认值生效的条件是，对象的属性值严格等于`undefined`。

```javascript
var { x = 3 } = { x: undefined };
x; // 3

var { x = 3 } = { x: null };
x; // null
```

上面代码中，属性`x`等于`null`，因为`null`与`undefined`不严格相等，所以是个有效的赋值，导致默认值`3`不会生效。

###### 注意点

（1）如果要将一个已经声明的变量用于解构赋值，必须非常小心。

```javascript
// 错误的写法
let x;
{x} = {x: 1};
// SyntaxError: syntax error
```

上面代码的写法会报错，因为 JavaScript 引擎会将`{x}`理解成一个代码块，从而发生语法错误。只有不将大括号写在行首，避免 JavaScript 将其解释为代码块，才能解决这个问题。

```javascript
// 正确的写法
let x;
({ x } = { x: 1 });
```

上面代码将整个解构赋值语句，放在一个圆括号里面，就可以正确执行。关于圆括号与解构赋值的关系，参见下文。

（2）解构赋值允许等号左边的模式之中，不放置任何变量名。因此，可以写出非常古怪的赋值表达式。

```javascript
({} = [true, false]);
({} = "abc");
({} = []);
```

上面的表达式虽然毫无意义，但是语法是合法的，可以执行。

（3）由于数组本质是特殊的对象，因此可以对数组进行对象属性的解构。

```javascript
let arr = [1, 2, 3];
let { 0: first, [arr.length - 1]: last } = arr;
first; // 1
last; // 3
```

上面代码对数组进行对象解构。数组`arr`的`0`键对应的值是`1`，`[arr.length - 1]`就是`2`键，对应的值是`3`。方括号这种写法，属于“属性名表达式”（参见《对象的扩展》一章）。

##### 字符串的解构赋值

字符串也可以解构赋值。这是因为此时，字符串被转换成了一个类似数组的对象。

```javascript
const [a, b, c, d, e] = "hello";
a; // "h"
b; // "e"
c; // "l"
d; // "l"
e; // "o"
```

类似数组的对象都有一个`length`属性，因此还可以对这个属性解构赋值。

```javascript
let { length: len } = "hello";
len; // 5
```

##### 数值和布尔值的解构赋值

解构赋值时，如果等号右边是数值和布尔值，则会先转为对象。

```javascript
let { toString: s } = 123;
s === Number.prototype.toString; // true

let { toString: s } = true;
s === Boolean.prototype.toString; // true
```

上面代码中，数值和布尔值的包装对象都有`toString`属性，因此变量`s`都能取到值。

解构赋值的规则是，只要等号右边的值不是对象或数组，就先将其转为对象。由于`undefined`和`null`无法转为对象，所以对它们进行解构赋值，都会报错。

```javascript
let { prop: x } = undefined; // TypeError
let { prop: y } = null; // TypeError
```

##### 函数参数的解构赋值

函数的参数也可以使用解构赋值。

```javascript
function add([x, y]) {
  return x + y;
}

add([1, 2]); // 3
```

上面代码中，函数`add`的参数表面上是一个数组，但在传入参数的那一刻，数组参数就被解构成变量`x`和`y`。对于函数内部的代码来说，它们能感受到的参数就是`x`和`y`。

下面是另一个例子。

```javascript
[
  [1, 2],
  [3, 4],
].map(([a, b]) => a + b);
// [ 3, 7 ]
```

函数参数的解构也可以使用默认值。

```javascript
function move({ x = 0, y = 0 } = {}) {
  return [x, y];
}

move({ x: 3, y: 8 }); // [3, 8]
move({ x: 3 }); // [3, 0]
move({}); // [0, 0]
move(); // [0, 0]
```

上面代码中，函数`move`的参数是一个对象，通过对这个对象进行解构，得到变量`x`和`y`的值。如果解构失败，`x`和`y`等于默认值。

注意，下面的写法会得到不一样的结果。

```javascript
function move({ x, y } = { x: 0, y: 0 }) {
  return [x, y];
}

move({ x: 3, y: 8 }); // [3, 8]
move({ x: 3 }); // [3, undefined]
move({}); // [undefined, undefined]
move(); // [0, 0]
```

上面代码是为函数`move`的参数指定默认值，而不是为变量`x`和`y`指定默认值，所以会得到与前一种写法不同的结果。

`undefined`就会触发函数参数的默认值。

```javascript
[1, undefined, 3].map((x = "yes") => x);
// [ 1, 'yes', 3 ]
```

##### 解构赋值圆括号问题

解构赋值虽然很方便，但是解析起来并不容易。对于编译器来说，一个式子到底是模式，还是表达式，没有办法从一开始就知道，必须解析到（或解析不到）等号才能知道。

由此带来的问题是，如果模式中出现圆括号怎么处理。ES6 的规则是，只要有可能导致解构的歧义，就不得使用圆括号。

但是，这条规则实际上不那么容易辨别，处理起来相当麻烦。因此，建议只要有可能，就不要在模式中放置圆括号。

###### 不能使用圆括号的情况

以下三种解构赋值不得使用圆括号。

（1）变量声明语句

```javascript
// 全部报错
let [(a)] = [1];

let {x: (c)} = {};
let ({x: c}) = {};
let {(x: c)} = {};
let {(x): c} = {};

let { o: ({ p: p }) } = { o: { p: 2 } };
```

上面 6 个语句都会报错，因为它们都是变量声明语句，模式不能使用圆括号。

（2）函数参数

函数参数也属于变量声明，因此不能带有圆括号。

```javascript
// 报错
function f([(z)]) { return z; }
// 报错
function f([z,(x)]) { return x; }
```

（3）赋值语句的模式

```javascript
// 全部报错
({ p: a }) = { p: 42 };
([a]) = [5];
```

上面代码将整个模式放在圆括号之中，导致报错。

```javascript
// 报错
[({ p: a }), { x: c }] = [{}, {}];
```

上面代码将一部分模式放在圆括号之中，导致报错。

###### 可以使用圆括号的情况

可以使用圆括号的情况只有一种：赋值语句的非模式部分，可以使用圆括号。

```javascript
[b] = [3]; // 正确
({ p: d } = {}); // 正确
[parseInt.prop] = [3]; // 正确
```

上面三行语句都可以正确执行，因为首先它们都是赋值语句，而不是声明语句；其次它们的圆括号都不属于模式的一部分。第一行语句中，模式是取数组的第一个成员，跟圆括号无关；第二行语句中，模式是`p`，而不是`d`；第三行语句与第一行语句的性质一致。

##### 解构赋值的用途

变量的解构赋值用途很多。

**（1）交换变量的值**

```javascript
let x = 1;
let y = 2;

[x, y] = [y, x];
```

上面代码交换变量`x`和`y`的值，这样的写法不仅简洁，而且易读，语义非常清晰。

**（2）从函数返回多个值**

函数只能返回一个值，如果要返回多个值，只能将它们放在数组或对象里返回。有了解构赋值，取出这些值就非常方便。

```javascript
// 返回一个数组

function example() {
  return [1, 2, 3];
}
let [a, b, c] = example();

// 返回一个对象

function example() {
  return {
    foo: 1,
    bar: 2,
  };
}
let { foo, bar } = example();
```

**（3）函数参数的定义**

解构赋值可以方便地将一组参数与变量名对应起来。

```javascript
// 参数是一组有次序的值
function f([x, y, z]) { ... }
f([1, 2, 3]);

// 参数是一组无次序的值
function f({x, y, z}) { ... }
f({z: 3, y: 2, x: 1});
```

**（4）提取 JSON 数据**

解构赋值对提取 JSON 对象中的数据，尤其有用。

```javascript
let jsonData = {
  id: 42,
  status: "OK",
  data: [867, 5309],
};

let { id, status, data: number } = jsonData;

console.log(id, status, number);
// 42, "OK", [867, 5309]
```

上面代码可以快速提取 JSON 数据的值。

**（5）函数参数的默认值**

```javascript
jQuery.ajax = function (
  url,
  {
    async = true,
    beforeSend = function () {},
    cache = true,
    complete = function () {},
    crossDomain = false,
    global = true,
    // ... more config
  } = {}
) {
  // ... do stuff
};
```

指定参数的默认值，就避免了在函数体内部再写`var foo = config.foo || 'default foo';`这样的语句。

**（6）遍历 Map 结构**

任何部署了 Iterator 接口的对象，都可以用`for...of`循环遍历。Map 结构原生支持 Iterator 接口，配合变量的解构赋值，获取键名和键值就非常方便。

```javascript
const map = new Map();
map.set("first", "hello");
map.set("second", "world");

for (let [key, value] of map) {
  console.log(key + " is " + value);
}
// first is hello
// second is world
```

如果只想获取键名，或者只想获取键值，可以写成下面这样。

```javascript
// 获取键名
for (let [key] of map) {
  // ...
}

// 获取键值
for (let [, value] of map) {
  // ...
}
```

**（7）输入模块的指定方法**

加载模块时，往往需要指定输入哪些方法。解构赋值使得输入语句非常清晰。

```javascript
const { SourceMapConsumer, SourceNode } = require("source-map");
```

#### 函数的扩展

##### 函数参数的默认值

###### 基本用法

ES6 之前，不能直接为函数的参数指定默认值，只能采用变通的方法。

```javascript
function log(x, y) {
  y = y || "World";
  console.log(x, y);
}

log("Hello"); // Hello World
log("Hello", "China"); // Hello China
log("Hello", ""); // Hello World
```

上面代码检查函数`log()`的参数`y`有没有赋值，如果没有，则指定默认值为`World`。这种写法的缺点在于，如果参数`y`赋值了，但是对应的布尔值为`false`，则该赋值不起作用。就像上面代码的最后一行，参数`y`等于空字符，结果被改为默认值。

为了避免这个问题，通常需要先判断一下参数`y`是否被赋值，如果没有，再等于默认值。

```javascript
if (typeof y === "undefined") {
  y = "World";
}
```

ES6 允许为函数的参数设置默认值，即直接写在参数定义的后面。

```javascript
function log(x, y = "World") {
  console.log(x, y);
}

log("Hello"); // Hello World
log("Hello", "China"); // Hello China
log("Hello", ""); // Hello
```

可以看到，ES6 的写法比 ES5 简洁许多，而且非常自然。下面是另一个例子。

```javascript
function Point(x = 0, y = 0) {
  this.x = x;
  this.y = y;
}

const p = new Point();
p; // { x: 0, y: 0 }
```

除了简洁，ES6 的写法还有两个好处：首先，阅读代码的人，可以立刻意识到哪些参数是可以省略的，不用查看函数体或文档；其次，有利于将来的代码优化，即使未来的版本在对外接口中，彻底拿掉这个参数，也不会导致以前的代码无法运行。

参数变量是默认声明的，所以不能用`let`或`const`再次声明。

```javascript
function foo(x = 5) {
  let x = 1; // error
  const x = 2; // error
}
```

上面代码中，参数变量`x`是默认声明的，在函数体中，不能用`let`或`const`再次声明，否则会报错。

使用参数默认值时，函数不能有同名参数。

```javascript
// 不报错
function foo(x, x, y) {
  // ...
}

// 报错
function foo(x, x, y = 1) {
  // ...
}
// SyntaxError: Duplicate parameter name not allowed in this context
```

另外，一个容易忽略的地方是，参数默认值不是传值的，而是每次都重新计算默认值表达式的值。也就是说，参数默认值是惰性求值的。

```javascript
let x = 99;
function foo(p = x + 1) {
  console.log(p);
}

foo(); // 100

x = 100;
foo(); // 101
```

上面代码中，参数`p`的默认值是`x + 1`。这时，每次调用函数`foo()`，都会重新计算`x + 1`，而不是默认`p`等于 100。

###### 与解构赋值默认值结合使用

参数默认值可以与解构赋值的默认值，结合起来使用。

```javascript
function foo({ x, y = 5 }) {
  console.log(x, y);
}

foo({}); // undefined 5
foo({ x: 1 }); // 1 5
foo({ x: 1, y: 2 }); // 1 2
foo(); // TypeError: Cannot read property 'x' of undefined
```

上面代码只使用了对象的解构赋值默认值，没有使用函数参数的默认值。只有当函数`foo()`的参数是一个对象时，变量`x`和`y`才会通过解构赋值生成。如果函数`foo()`调用时没提供参数，变量`x`和`y`就不会生成，从而报错。通过提供函数参数的默认值，就可以避免这种情况。

```javascript
function foo({ x, y = 5 } = {}) {
  console.log(x, y);
}

foo(); // undefined 5
```

上面代码指定，如果没有提供参数，函数`foo`的参数默认为一个空对象。

下面是另一个解构赋值默认值的例子。

```javascript
function fetch(url, { body = "", method = "GET", headers = {} }) {
  console.log(method);
}

fetch("http://example.com", {});
// "GET"

fetch("http://example.com");
// 报错
```

上面代码中，如果函数`fetch()`的第二个参数是一个对象，就可以为它的三个属性设置默认值。这种写法不能省略第二个参数，如果结合函数参数的默认值，就可以省略第二个参数。这时，就出现了双重默认值。

```javascript
function fetch(url, { body = "", method = "GET", headers = {} } = {}) {
  console.log(method);
}

fetch("http://example.com");
// "GET"
```

上面代码中，函数`fetch`没有第二个参数时，函数参数的默认值就会生效，然后才是解构赋值的默认值生效，变量`method`才会取到默认值`GET`。

注意，函数参数的默认值生效以后，参数解构赋值依然会进行。

```javascript
function f({ a, b = "world" } = { a: "hello" }) {
  console.log(b);
}

f(); // world
```

上面示例中，函数`f()`调用时没有参数，所以参数默认值`{ a: 'hello' }`生效，然后再对这个默认值进行解构赋值，从而触发参数变量`b`的默认值生效。

作为练习，大家可以思考一下，下面两种函数写法有什么差别？

```javascript
// 写法一
function m1({ x = 0, y = 0 } = {}) {
  return [x, y];
}

// 写法二
function m2({ x, y } = { x: 0, y: 0 }) {
  return [x, y];
}

// 函数没有参数的情况
m1(); // [0, 0]
m2(); // [0, 0]

// x 和 y 都有值的情况
m1({ x: 3, y: 8 }); // [3, 8]
m2({ x: 3, y: 8 }); // [3, 8]

// x 有值，y 无值的情况
m1({ x: 3 }); // [3, 0]
m2({ x: 3 }); // [3, undefined]

// x 和 y 都无值的情况
m1({}); // [0, 0];
m2({}); // [undefined, undefined]

m1({ z: 3 }); // [0, 0]
m2({ z: 3 }); // [undefined, undefined]
```

###### 参数默认值的位置

通常情况下，定义了默认值的参数，应该是函数的尾参数。因为这样比较容易看出来，到底省略了哪些参数。如果非尾部的参数设置默认值，实际上这个参数是没法省略的。

```javascript
// 例一
function f(x = 1, y) {
  return [x, y];
}

f() // [1, undefined]
f(2) // [2, undefined]
f(, 1) // 报错
f(undefined, 1) // [1, 1]

// 例二
function f(x, y = 5, z) {
  return [x, y, z];
}

f() // [undefined, 5, undefined]
f(1) // [1, 5, undefined]
f(1, ,2) // 报错
f(1, undefined, 2) // [1, 5, 2]
```

上面代码中，有默认值的参数都不是尾参数。这时，无法只省略该参数，而不省略它后面的参数，除非显式输入`undefined`。

如果传入`undefined`，将触发该参数等于默认值，`null`则没有这个效果。

```javascript
function foo(x = 5, y = 6) {
  console.log(x, y);
}

foo(undefined, null);
// 5 null
```

上面代码中，`x`参数对应`undefined`，结果触发了默认值，`y`参数等于`null`，就没有触发默认值。

###### 函数的 length 属性

指定了默认值以后，函数的`length`属性，将返回没有指定默认值的参数个数。也就是说，指定了默认值后，`length`属性将失真。

```javascript
(function (a) {}
  .length(
    // 1
    function (a = 5) {}
  )
  .length(
    // 0
    function (a, b, c = 5) {}
  ).length); // 2
```

上面代码中，`length`属性的返回值，等于函数的参数个数减去指定了默认值的参数个数。比如，上面最后一个函数，定义了 3 个参数，其中有一个参数`c`指定了默认值，因此`length`属性等于`3`减去`1`，最后得到`2`。

这是因为`length`属性的含义是，该函数预期传入的参数个数。某个参数指定默认值以后，预期传入的参数个数就不包括这个参数了。同理，后文的 rest 参数也不会计入`length`属性。

```javascript
(function (...args) {}.length); // 0
```

如果设置了默认值的参数不是尾参数，那么`length`属性也不再计入后面的参数了。

```javascript
(function (a = 0, b, c) {}.length(
  // 0
  function (a, b = 1, c) {}
).length); // 1
```

###### 作用域

一旦设置了参数的默认值，函数进行声明初始化时，参数会形成一个单独的作用域（context）。等到初始化结束，这个作用域就会消失。这种语法行为，在不设置参数默认值时，是不会出现的。

```javascript
var x = 1;

function f(x, y = x) {
  console.log(y);
}

f(2); // 2
```

上面代码中，参数`y`的默认值等于变量`x`。调用函数`f`时，参数形成一个单独的作用域。在这个作用域里面，默认值变量`x`指向第一个参数`x`，而不是全局变量`x`，所以输出是`2`。

再看下面的例子。

```javascript
let x = 1;

function f(y = x) {
  let x = 2;
  console.log(y);
}

f(); // 1
```

上面代码中，函数`f`调用时，参数`y = x`形成一个单独的作用域。这个作用域里面，变量`x`本身没有定义，所以指向外层的全局变量`x`。函数调用时，函数体内部的局部变量`x`影响不到默认值变量`x`。

如果此时，全局变量`x`不存在，就会报错。

```javascript
function f(y = x) {
  let x = 2;
  console.log(y);
}

f(); // ReferenceError: x is not defined
```

下面这样写，也会报错。

```javascript
var x = 1;

function foo(x = x) {
  // ...
}

foo(); // ReferenceError: Cannot access 'x' before initialization
```

上面代码中，参数`x = x`形成一个单独作用域。实际执行的是`let x = x`，由于暂时性死区的原因，这行代码会报错。

如果参数的默认值是一个函数，该函数的作用域也遵守这个规则。请看下面的例子。

```javascript
let foo = "outer";

function bar(func = () => foo) {
  let foo = "inner";
  console.log(func());
}

bar(); // outer
```

上面代码中，函数`bar`的参数`func`的默认值是一个匿名函数，返回值为变量`foo`。函数参数形成的单独作用域里面，并没有定义变量`foo`，所以`foo`指向外层的全局变量`foo`，因此输出`outer`。

如果写成下面这样，就会报错。

```javascript
function bar(func = () => foo) {
  let foo = "inner";
  console.log(func());
}

bar(); // ReferenceError: foo is not defined
```

上面代码中，匿名函数里面的`foo`指向函数外层，但是函数外层并没有声明变量`foo`，所以就报错了。

下面是一个更复杂的例子。

```javascript
var x = 1;
function foo(
  x,
  y = function () {
    x = 2;
  }
) {
  var x = 3;
  y();
  console.log(x);
}

foo(); // 3
x; // 1
```

上面代码中，函数`foo`的参数形成一个单独作用域。这个作用域里面，首先声明了变量`x`，然后声明了变量`y`，`y`的默认值是一个匿名函数。这个匿名函数内部的变量`x`，指向同一个作用域的第一个参数`x`。函数`foo`内部又声明了一个内部变量`x`，该变量与第一个参数`x`由于不是同一个作用域，所以不是同一个变量，因此执行`y`后，内部变量`x`和外部全局变量`x`的值都没变。

如果将`var x = 3`的`var`去除，函数`foo`的内部变量`x`就指向第一个参数`x`，与匿名函数内部的`x`是一致的，所以最后输出的就是`2`，而外层的全局变量`x`依然不受影响。

```javascript
var x = 1;
function foo(
  x,
  y = function () {
    x = 2;
  }
) {
  x = 3;
  y();
  console.log(x);
}

foo(); // 2
x; // 1
```

###### 应用

利用参数默认值，可以指定某一个参数不得省略，如果省略就抛出一个错误。

```javascript
function throwIfMissing() {
  throw new Error("Missing parameter");
}

function foo(mustBeProvided = throwIfMissing()) {
  return mustBeProvided;
}

foo();
// Error: Missing parameter
```

上面代码的`foo`函数，如果调用的时候没有参数，就会调用默认值`throwIfMissing`函数，从而抛出一个错误。

从上面代码还可以看到，参数`mustBeProvided`的默认值等于`throwIfMissing`函数的运行结果（注意函数名`throwIfMissing`之后有一对圆括号），这表明参数的默认值不是在定义时执行，而是在运行时执行。如果参数已经赋值，默认值中的函数就不会运行。

另外，可以将参数默认值设为`undefined`，表明这个参数是可以省略的。

```javascript
function foo(optional = undefined) { ··· }
```

##### rest 参数

ES6 引入 rest 参数（形式为`...变量名`），用于获取函数的多余参数，这样就不需要使用`arguments`对象了。rest 参数搭配的变量是一个数组，该变量将多余的参数放入数组中。

```javascript
function add(...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }

  return sum;
}

add(2, 5, 3); // 10
```

上面代码的`add`函数是一个求和函数，利用 rest 参数，可以向该函数传入任意数目的参数。

下面是一个 rest 参数代替`arguments`变量的例子。

```javascript
// arguments变量的写法
function sortNumbers() {
  return Array.from(arguments).sort();
}

// rest参数的写法
const sortNumbers = (...numbers) => numbers.sort();
```

上面代码的两种写法，比较后可以发现，rest 参数的写法更自然也更简洁。

`arguments`对象不是数组，而是一个类似数组的对象。所以为了使用数组的方法，必须使用`Array.from`先将其转为数组。rest 参数就不存在这个问题，它就是一个真正的数组，数组特有的方法都可以使用。下面是一个利用 rest 参数改写数组`push`方法的例子。

```javascript
function push(array, ...items) {
  items.forEach(function (item) {
    array.push(item);
    console.log(item);
  });
}

var a = [];
push(a, 1, 2, 3);
```

注意，rest 参数之后不能再有其他参数（即只能是最后一个参数），否则会报错。

```javascript
// 报错
function f(a, ...b, c) {
  // ...
}
```

函数的`length`属性，不包括 rest 参数。

```javascript
(function (a) {}
  .length(
    // 1
    function (...a) {}
  )
  .length(
    // 0
    function (a, ...b) {}
  ).length); // 1
```

##### 严格模式

从 ES5 开始，函数内部可以设定为严格模式。

```javascript
function doSomething(a, b) {
  "use strict";
  // code
}
```

ES2016 做了一点修改，规定只要函数参数使用了默认值、解构赋值、或者扩展运算符，那么函数内部就不能显式设定为严格模式，否则会报错。

```javascript
// 报错
function doSomething(a, b = a) {
  'use strict';
  // code
}

// 报错
const doSomething = function ({a, b}) {
  'use strict';
  // code
};

// 报错
const doSomething = (...a) => {
  'use strict';
  // code
};

const obj = {
  // 报错
  doSomething({a, b}) {
    'use strict';
    // code
  }
};
```

这样规定的原因是，函数内部的严格模式，同时适用于函数体和函数参数。但是，函数执行的时候，先执行函数参数，然后再执行函数体。这样就有一个不合理的地方，只有从函数体之中，才能知道参数是否应该以严格模式执行，但是参数却应该先于函数体执行。

```javascript
// 报错
function doSomething(value = 070) {
  'use strict';
  return value;
}
```

上面代码中，参数`value`的默认值是八进制数`070`，但是严格模式下不能用前缀`0`表示八进制，所以应该报错。但是实际上，JavaScript 引擎会先成功执行`value = 070`，然后进入函数体内部，发现需要用严格模式执行，这时才会报错。

虽然可以先解析函数体代码，再执行参数代码，但是这样无疑就增加了复杂性。因此，标准索性禁止了这种用法，只要参数使用了默认值、解构赋值、或者扩展运算符，就不能显式指定严格模式。

两种方法可以规避这种限制。第一种是设定全局性的严格模式，这是合法的。

```javascript
"use strict";

function doSomething(a, b = a) {
  // code
}
```

第二种是把函数包在一个无参数的立即执行函数里面。

```javascript
const doSomething = (function () {
  "use strict";
  return function (value = 42) {
    return value;
  };
})();
```

##### name 属性

函数的`name`属性，返回该函数的函数名。

```javascript
function foo() {}
foo.name; // "foo"
```

这个属性早就被浏览器广泛支持，但是直到 ES6，才将其写入了标准。

需要注意的是，ES6 对这个属性的行为做出了一些修改。如果将一个匿名函数赋值给一个变量，ES5 的`name`属性，会返回空字符串，而 ES6 的`name`属性会返回实际的函数名。

```javascript
var f = function () {};

// ES5
f.name; // ""

// ES6
f.name; // "f"
```

上面代码中，变量`f`等于一个匿名函数，ES5 和 ES6 的`name`属性返回的值不一样。

如果将一个具名函数赋值给一个变量，则 ES5 和 ES6 的`name`属性都返回这个具名函数原本的名字。

```javascript
const bar = function baz() {};

// ES5
bar.name; // "baz"

// ES6
bar.name; // "baz"
```

`Function`构造函数返回的函数实例，`name`属性的值为`anonymous`。

```javascript
new Function().name; // "anonymous"
```

`bind`返回的函数，`name`属性值会加上`bound`前缀。

```javascript
function foo() {}
foo
  .bind({})
  .name(
    // "bound foo"

    function () {}
  )
  .bind({}).name; // "bound "
```

##### 箭头函数

###### 基本用法

ES6 允许使用“箭头”（`=>`）定义函数。

```javascript
var f = (v) => v;

// 等同于
var f = function (v) {
  return v;
};
```

如果箭头函数不需要参数或需要多个参数，就使用一个圆括号代表参数部分。

```javascript
var f = () => 5;
// 等同于
var f = function () {
  return 5;
};

var sum = (num1, num2) => num1 + num2;
// 等同于
var sum = function (num1, num2) {
  return num1 + num2;
};
```

如果箭头函数的代码块部分多于一条语句，就要使用大括号将它们括起来，并且使用`return`语句返回。

```javascript
var sum = (num1, num2) => {
  return num1 + num2;
};
```

由于大括号被解释为代码块，所以如果箭头函数直接返回一个对象，必须在对象外面加上括号，否则会报错。

```javascript
// 报错
let getTempItem = id => { id: id, name: "Temp" };

// 不报错
let getTempItem = id => ({ id: id, name: "Temp" });
```

下面是一种特殊情况，虽然可以运行，但会得到错误的结果。

```javascript
let foo = () => {
  a: 1;
};
foo(); // undefined
```

上面代码中，原始意图是返回一个对象`{ a: 1 }`，但是由于引擎认为大括号是代码块，所以执行了一行语句`a: 1`。这时，`a`可以被解释为语句的标签，因此实际执行的语句是`1;`，然后函数就结束了，没有返回值。

如果箭头函数只有一行语句，且不需要返回值，可以采用下面的写法，就不用写大括号了。

```javascript
let fn = () => void doesNotReturn();
```

箭头函数可以与变量解构结合使用。

```javascript
const full = ({ first, last }) => first + " " + last;

// 等同于
function full(person) {
  return person.first + " " + person.last;
}
```

箭头函数使得表达更加简洁。

```javascript
const isEven = (n) => n % 2 === 0;
const square = (n) => n * n;
```

上面代码只用了两行，就定义了两个简单的工具函数。如果不用箭头函数，可能就要占用多行，而且还不如现在这样写醒目。

箭头函数的一个用处是简化回调函数。

```javascript
// 普通函数写法
[1, 2, 3].map(function (x) {
  return x * x;
});

// 箭头函数写法
[1, 2, 3].map((x) => x * x);
```

另一个例子是

```javascript
// 普通函数写法
var result = values.sort(function (a, b) {
  return a - b;
});

// 箭头函数写法
var result = values.sort((a, b) => a - b);
```

下面是 rest 参数与箭头函数结合的例子。

```javascript
const numbers = (...nums) => nums;

numbers(1, 2, 3, 4, 5);
// [1,2,3,4,5]

const headAndTail = (head, ...tail) => [head, tail];

headAndTail(1, 2, 3, 4, 5);
// [1,[2,3,4,5]]
```

###### 使用注意点

箭头函数有几个使用注意点。

（1）箭头函数没有自己的`this`对象（详见下文）。

（2）不可以当作构造函数，也就是说，不可以对箭头函数使用`new`命令，否则会抛出一个错误。

（3）不可以使用`arguments`对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。

（4）不可以使用`yield`命令，因此箭头函数不能用作 Generator 函数。

上面四点中，最重要的是第一点。对于普通函数来说，内部的`this`指向函数运行时所在的对象，但是这一点对箭头函数不成立。它没有自己的`this`对象，内部的`this`就是定义时上层作用域中的`this`。也就是说，箭头函数内部的`this`指向是固定的，相比之下，普通函数的`this`指向是可变的。

```javascript
function foo() {
  setTimeout(() => {
    console.log("id:", this.id);
  }, 100);
}

var id = 21;

foo.call({ id: 42 });
// id: 42
```

上面代码中，`setTimeout()`的参数是一个箭头函数，这个箭头函数的定义生效是在`foo`函数生成时，而它的真正执行要等到 100 毫秒后。如果是普通函数，执行时`this`应该指向全局对象`window`，这时应该输出`21`。但是，箭头函数导致`this`总是指向函数定义生效时所在的对象（本例是`{id: 42}`），所以打印出来的是`42`。

下面例子是回调函数分别为箭头函数和普通函数，对比它们内部的`this`指向。

```javascript
function Timer() {
  this.s1 = 0;
  this.s2 = 0;
  // 箭头函数
  setInterval(() => this.s1++, 1000);
  // 普通函数
  setInterval(function () {
    this.s2++;
  }, 1000);
}

var timer = new Timer();

setTimeout(() => console.log("s1: ", timer.s1), 3100);
setTimeout(() => console.log("s2: ", timer.s2), 3100);
// s1: 3
// s2: 0
```

上面代码中，`Timer`函数内部设置了两个定时器，分别使用了箭头函数和普通函数。前者的`this`绑定定义时所在的作用域（即`Timer`函数），后者的`this`指向运行时所在的作用域（即全局对象）。所以，3100 毫秒之后，`timer.s1`被更新了 3 次，而`timer.s2`一次都没更新。

箭头函数实际上可以让`this`指向固定化，绑定`this`使得它不再可变，这种特性很有利于封装回调函数。下面是一个例子，DOM 事件的回调函数封装在一个对象里面。

```javascript
var handler = {
  id: "123456",

  init: function () {
    document.addEventListener(
      "click",
      (event) => this.doSomething(event.type),
      false
    );
  },

  doSomething: function (type) {
    console.log("Handling " + type + " for " + this.id);
  },
};
```

上面代码的`init()`方法中，使用了箭头函数，这导致这个箭头函数里面的`this`，总是指向`handler`对象。如果回调函数是普通函数，那么运行`this.doSomething()`这一行会报错，因为此时`this`指向`document`对象。

总之，箭头函数根本没有自己的`this`，导致内部的`this`就是外层代码块的`this`。正是因为它没有`this`，所以也就不能用作构造函数。

下面是 Babel 转箭头函数产生的 ES5 代码，就能清楚地说明`this`的指向。

```javascript
// ES6
function foo() {
  setTimeout(() => {
    console.log("id:", this.id);
  }, 100);
}

// ES5
function foo() {
  var _this = this;

  setTimeout(function () {
    console.log("id:", _this.id);
  }, 100);
}
```

上面代码中，转换后的 ES5 版本清楚地说明了，箭头函数里面根本没有自己的`this`，而是引用外层的`this`。

请问下面的代码之中，`this`的指向有几个？

```javascript
function foo() {
  return () => {
    return () => {
      return () => {
        console.log("id:", this.id);
      };
    };
  };
}

var f = foo.call({ id: 1 });

var t1 = f.call({ id: 2 })()(); // id: 1
var t2 = f().call({ id: 3 })(); // id: 1
var t3 = f()().call({ id: 4 }); // id: 1
```

答案是`this`的指向只有一个，就是函数`foo`的`this`，这是因为所有的内层函数都是箭头函数，都没有自己的`this`，它们的`this`其实都是最外层`foo`函数的`this`。所以不管怎么嵌套，`t1`、`t2`、`t3`都输出同样的结果。如果这个例子的所有内层函数都写成普通函数，那么每个函数的`this`都指向运行时所在的不同对象。

除了`this`，以下三个变量在箭头函数之中也是不存在的，指向外层函数的对应变量：`arguments`、`super`、`new.target`。

```javascript
function foo() {
  setTimeout(() => {
    console.log("args:", arguments);
  }, 100);
}

foo(2, 4, 6, 8);
// args: [2, 4, 6, 8]
```

上面代码中，箭头函数内部的变量`arguments`，其实是函数`foo`的`arguments`变量。

另外，由于箭头函数没有自己的`this`，所以当然也就不能用`call()`、`apply()`、`bind()`这些方法去改变`this`的指向。

```javascript
(function () {
  return [(() => this.x).bind({ x: "inner" })()];
}.call({ x: "outer" }));
// ['outer']
```

上面代码中，箭头函数没有自己的`this`，所以`bind`方法无效，内部的`this`指向外部的`this`。

长期以来，JavaScript 语言的`this`对象一直是一个令人头痛的问题，在对象方法中使用`this`，必须非常小心。箭头函数”绑定”`this`，很大程度上解决了这个困扰。

###### 不适用场合

由于箭头函数使得`this`从“动态”变成“静态”，下面两个场合不应该使用箭头函数。

第一个场合是定义对象的方法，且该方法内部包括`this`。

```javascript
const cat = {
  lives: 9,
  jumps: () => {
    this.lives--;
  },
};
```

上面代码中，`cat.jumps()`方法是一个箭头函数，这是错误的。调用`cat.jumps()`时，如果是普通函数，该方法内部的`this`指向`cat`；如果写成上面那样的箭头函数，使得`this`指向全局对象，因此不会得到预期结果。这是因为对象不构成单独的作用域，导致`jumps`箭头函数定义时的作用域就是全局作用域。

再看一个例子。

```javascript
globalThis.s = 21;

const obj = {
  s: 42,
  m: () => console.log(this.s),
};

obj.m(); // 21
```

上面例子中，`obj.m()`使用箭头函数定义。JavaScript 引擎的处理方法是，先在全局空间生成这个箭头函数，然后赋值给`obj.m`，这导致箭头函数内部的`this`指向全局对象，所以`obj.m()`输出的是全局空间的`21`，而不是对象内部的`42`。上面的代码实际上等同于下面的代码。

```javascript
globalThis.s = 21;
globalThis.m = () => console.log(this.s);

const obj = {
  s: 42,
  m: globalThis.m,
};

obj.m(); // 21
```

由于上面这个原因，对象的属性建议使用传统的写法定义，不要用箭头函数定义。

第二个场合是需要动态`this`的时候，也不应使用箭头函数。

```javascript
var button = document.getElementById("press");
button.addEventListener("click", () => {
  this.classList.toggle("on");
});
```

上面代码运行时，点击按钮会报错，因为`button`的监听函数是一个箭头函数，导致里面的`this`就是全局对象。如果改成普通函数，`this`就会动态指向被点击的按钮对象。

另外，如果函数体很复杂，有许多行，或者函数内部有大量的读写操作，不单纯是为了计算值，这时也不应该使用箭头函数，而是要使用普通函数，这样可以提高代码可读性。

###### 嵌套的箭头函数

箭头函数内部，还可以再使用箭头函数。下面是一个 ES5 语法的多重嵌套函数。

```javascript
function insert(value) {
  return {
    into: function (array) {
      return {
        after: function (afterValue) {
          array.splice(array.indexOf(afterValue) + 1, 0, value);
          return array;
        },
      };
    },
  };
}

insert(2).into([1, 3]).after(1); //[1, 2, 3]
```

上面这个函数，可以使用箭头函数改写。

```javascript
let insert = (value) => ({
  into: (array) => ({
    after: (afterValue) => {
      array.splice(array.indexOf(afterValue) + 1, 0, value);
      return array;
    },
  }),
});

insert(2).into([1, 3]).after(1); //[1, 2, 3]
```

下面是一个部署管道机制（pipeline）的例子，即前一个函数的输出是后一个函数的输入。

```javascript
const pipeline =
  (...funcs) =>
  (val) =>
    funcs.reduce((a, b) => b(a), val);

const plus1 = (a) => a + 1;
const mult2 = (a) => a * 2;
const addThenMult = pipeline(plus1, mult2);

addThenMult(5);
// 12
```

如果觉得上面的写法可读性比较差，也可以采用下面的写法。

```javascript
const plus1 = (a) => a + 1;
const mult2 = (a) => a * 2;

mult2(plus1(5));
// 12
```

箭头函数还有一个功能，就是可以很方便地改写 λ 演算。

```javascript
// λ演算的写法
fix = λf.(λx.f(λv.x(x)(v)))(λx.f(λv.x(x)(v)))

// ES6的写法
var fix = f => (x => f(v => x(x)(v)))
               (x => f(v => x(x)(v)));
```

上面两种写法，几乎是一一对应的。由于 λ 演算对于计算机科学非常重要，这使得我们可以用 ES6 作为替代工具，探索计算机科学。

##### 尾调用优化

###### 什么是尾调用？

尾调用（Tail Call）是函数式编程的一个重要概念，本身非常简单，一句话就能说清楚，就是指某个函数的最后一步是调用另一个函数。

```javascript
function f(x) {
  return g(x);
}
```

上面代码中，函数`f`的最后一步是调用函数`g`，这就叫尾调用。

以下三种情况，都不属于尾调用。

```javascript
// 情况一
function f(x) {
  let y = g(x);
  return y;
}

// 情况二
function f(x) {
  return g(x) + 1;
}

// 情况三
function f(x) {
  g(x);
}
```

上面代码中，情况一是调用函数`g`之后，还有赋值操作，所以不属于尾调用，即使语义完全一样。情况二也属于调用后还有操作，即使写在一行内。情况三等同于下面的代码。

```javascript
function f(x) {
  g(x);
  return undefined;
}
```

尾调用不一定出现在函数尾部，只要是最后一步操作即可。

```javascript
function f(x) {
  if (x > 0) {
    return m(x);
  }
  return n(x);
}
```

上面代码中，函数`m`和`n`都属于尾调用，因为它们都是函数`f`的最后一步操作。

###### 尾调用优化

尾调用之所以与其他调用不同，就在于它的特殊的调用位置。

我们知道，函数调用会在内存形成一个“调用记录”，又称“调用帧”（call frame），保存调用位置和内部变量等信息。如果在函数`A`的内部调用函数`B`，那么在`A`的调用帧上方，还会形成一个`B`的调用帧。等到`B`运行结束，将结果返回到`A`，`B`的调用帧才会消失。如果函数`B`内部还调用函数`C`，那就还有一个`C`的调用帧，以此类推。所有的调用帧，就形成一个“调用栈”（call stack）。

尾调用由于是函数的最后一步操作，所以不需要保留外层函数的调用帧，因为调用位置、内部变量等信息都不会再用到了，只要直接用内层函数的调用帧，取代外层函数的调用帧就可以了。

```javascript
function f() {
  let m = 1;
  let n = 2;
  return g(m + n);
}
f();

// 等同于
function f() {
  return g(3);
}
f();

// 等同于
g(3);
```

上面代码中，如果函数`g`不是尾调用，函数`f`就需要保存内部变量`m`和`n`的值、`g`的调用位置等信息。但由于调用`g`之后，函数`f`就结束了，所以执行到最后一步，完全可以删除`f(x)`的调用帧，只保留`g(3)`的调用帧。

这就叫做“尾调用优化”（Tail call optimization），即只保留内层函数的调用帧。如果所有函数都是尾调用，那么完全可以做到每次执行时，调用帧只有一项，这将大大节省内存。这就是“尾调用优化”的意义。

注意，只有不再用到外层函数的内部变量，内层函数的调用帧才会取代外层函数的调用帧，否则就无法进行“尾调用优化”。

```javascript
function addOne(a) {
  var one = 1;
  function inner(b) {
    return b + one;
  }
  return inner(a);
}
```

上面的函数不会进行尾调用优化，因为内层函数`inner`用到了外层函数`addOne`的内部变量`one`。

注意，目前只有 Safari 浏览器支持尾调用优化，Chrome 和 Firefox 都不支持。

###### 尾递归

函数调用自身，称为递归。如果尾调用自身，就称为尾递归。

递归非常耗费内存，因为需要同时保存成千上百个调用帧，很容易发生“栈溢出”错误（stack overflow）。但对于尾递归来说，由于只存在一个调用帧，所以永远不会发生“栈溢出”错误。

```javascript
function factorial(n) {
  if (n === 1) return 1;
  return n * factorial(n - 1);
}

factorial(5); // 120
```

上面代码是一个阶乘函数，计算`n`的阶乘，最多需要保存`n`个调用记录，复杂度 O(n) 。

如果改写成尾递归，只保留一个调用记录，复杂度 O(1) 。

```javascript
function factorial(n, total) {
  if (n === 1) return total;
  return factorial(n - 1, n * total);
}

factorial(5, 1); // 120
```

还有一个比较著名的例子，就是计算 Fibonacci 数列，也能充分说明尾递归优化的重要性。

非尾递归的 Fibonacci 数列实现如下。

```javascript
function Fibonacci(n) {
  if (n <= 1) {
    return 1;
  }

  return Fibonacci(n - 1) + Fibonacci(n - 2);
}

Fibonacci(10); // 89
Fibonacci(100); // 超时
Fibonacci(500); // 超时
```

尾递归优化过的 Fibonacci 数列实现如下。

```javascript
function Fibonacci2(n, ac1 = 1, ac2 = 1) {
  if (n <= 1) {
    return ac2;
  }

  return Fibonacci2(n - 1, ac2, ac1 + ac2);
}

Fibonacci2(100); // 573147844013817200000
Fibonacci2(1000); // 7.0330367711422765e+208
Fibonacci2(10000); // Infinity
```

由此可见，“尾调用优化”对递归操作意义重大，所以一些函数式编程语言将其写入了语言规格。ES6 亦是如此，第一次明确规定，所有 ECMAScript 的实现，都必须部署“尾调用优化”。这就是说，ES6 中只要使用尾递归，就不会发生栈溢出（或者层层递归造成的超时），相对节省内存。

###### 递归函数的改写

尾递归的实现，往往需要改写递归函数，确保最后一步只调用自身。做到这一点的方法，就是把所有用到的内部变量改写成函数的参数。比如上面的例子，阶乘函数 factorial 需要用到一个中间变量`total`，那就把这个中间变量改写成函数的参数。这样做的缺点就是不太直观，第一眼很难看出来，为什么计算`5`的阶乘，需要传入两个参数`5`和`1`？

两个方法可以解决这个问题。方法一是在尾递归函数之外，再提供一个正常形式的函数。

```javascript
function tailFactorial(n, total) {
  if (n === 1) return total;
  return tailFactorial(n - 1, n * total);
}

function factorial(n) {
  return tailFactorial(n, 1);
}

factorial(5); // 120
```

上面代码通过一个正常形式的阶乘函数`factorial`，调用尾递归函数`tailFactorial`，看起来就正常多了。

函数式编程有一个概念，叫做柯里化（currying），意思是将多参数的函数转换成单参数的形式。这里也可以使用柯里化。

```javascript
function currying(fn, n) {
  return function (m) {
    return fn.call(this, m, n);
  };
}

function tailFactorial(n, total) {
  if (n === 1) return total;
  return tailFactorial(n - 1, n * total);
}

const factorial = currying(tailFactorial, 1);

factorial(5); // 120
```

上面代码通过柯里化，将尾递归函数`tailFactorial`变为只接受一个参数的`factorial`。

第二种方法就简单多了，就是采用 ES6 的函数默认值。

```javascript
function factorial(n, total = 1) {
  if (n === 1) return total;
  return factorial(n - 1, n * total);
}

factorial(5); // 120
```

上面代码中，参数`total`有默认值`1`，所以调用时不用提供这个值。

总结一下，递归本质上是一种循环操作。纯粹的函数式编程语言没有循环操作命令，所有的循环都用递归实现，这就是为什么尾递归对这些语言极其重要。对于其他支持“尾调用优化”的语言（比如 Lua，ES6），只需要知道循环可以用递归代替，而一旦使用递归，就最好使用尾递归。

###### 严格模式

ES6 的尾调用优化只在严格模式下开启，正常模式是无效的。

这是因为在正常模式下，函数内部有两个变量，可以跟踪函数的调用栈。

- `func.arguments`：返回调用时函数的参数。
- `func.caller`：返回调用当前函数的那个函数。

尾调用优化发生时，函数的调用栈会改写，因此上面两个变量就会失真。严格模式禁用这两个变量，所以尾调用模式仅在严格模式下生效。

```javascript
function restricted() {
  "use strict";
  restricted.caller; // 报错
  restricted.arguments; // 报错
}
restricted();
```

###### 尾递归优化的实现

尾递归优化只在严格模式下生效，那么正常模式下，或者那些不支持该功能的环境中，有没有办法也使用尾递归优化呢？回答是可以的，就是自己实现尾递归优化。

它的原理非常简单。尾递归之所以需要优化，原因是调用栈太多，造成溢出，那么只要减少调用栈，就不会溢出。怎么做可以减少调用栈呢？就是采用“循环”换掉“递归”。

下面是一个正常的递归函数。

```javascript
function sum(x, y) {
  if (y > 0) {
    return sum(x + 1, y - 1);
  } else {
    return x;
  }
}

sum(1, 100000);
// Uncaught RangeError: Maximum call stack size exceeded(…)
```

上面代码中，`sum`是一个递归函数，参数`x`是需要累加的值，参数`y`控制递归次数。一旦指定`sum`递归 100000 次，就会报错，提示超出调用栈的最大次数。

蹦床函数（trampoline）可以将递归执行转为循环执行。

```javascript
function trampoline(f) {
  while (f && f instanceof Function) {
    f = f();
  }
  return f;
}
```

上面就是蹦床函数的一个实现，它接受一个函数`f`作为参数。只要`f`执行后返回一个函数，就继续执行。注意，这里是返回一个函数，然后执行该函数，而不是函数里面调用函数，这样就避免了递归执行，从而就消除了调用栈过大的问题。

然后，要做的就是将原来的递归函数，改写为每一步返回另一个函数。

```javascript
function sum(x, y) {
  if (y > 0) {
    return sum.bind(null, x + 1, y - 1);
  } else {
    return x;
  }
}
```

上面代码中，`sum`函数的每次执行，都会返回自身的另一个版本。

现在，使用蹦床函数执行`sum`，就不会发生调用栈溢出。

```javascript
trampoline(sum(1, 100000));
// 100001
```

蹦床函数并不是真正的尾递归优化，下面的实现才是。

```javascript
function tco(f) {
  var value;
  var active = false;
  var accumulated = [];

  return function accumulator() {
    accumulated.push(arguments);
    if (!active) {
      active = true;
      while (accumulated.length) {
        value = f.apply(this, accumulated.shift());
      }
      active = false;
      return value;
    }
  };
}

var sum = tco(function (x, y) {
  if (y > 0) {
    return sum(x + 1, y - 1);
  } else {
    return x;
  }
});

sum(1, 100000);
// 100001
```

上面代码中，`tco`函数是尾递归优化的实现，它的奥妙就在于状态变量`active`。默认情况下，这个变量是不激活的。一旦进入尾递归优化的过程，这个变量就激活了。然后，每一轮递归`sum`返回的都是`undefined`，所以就避免了递归执行；而`accumulated`数组存放每一轮`sum`执行的参数，总是有值的，这就保证了`accumulator`函数内部的`while`循环总是会执行。这样就很巧妙地将“递归”改成了“循环”，而后一轮的参数会取代前一轮的参数，保证了调用栈只有一层。

##### 函数参数的尾逗号

ES2017 [允许](https://github.com/jeffmo/es-trailing-function-commas)函数的最后一个参数有尾逗号（trailing comma）。

此前，函数定义和调用时，都不允许最后一个参数后面出现逗号。

```javascript
function clownsEverywhere(param1, param2) {
  /* ... */
}

clownsEverywhere("foo", "bar");
```

上面代码中，如果在`param2`或`bar`后面加一个逗号，就会报错。

如果像上面这样，将参数写成多行（即每个参数占据一行），以后修改代码的时候，想为函数`clownsEverywhere`添加第三个参数，或者调整参数的次序，就势必要在原来最后一个参数后面添加一个逗号。这对于版本管理系统来说，就会显示添加逗号的那一行也发生了变动。这看上去有点冗余，因此新的语法允许定义和调用时，尾部直接有一个逗号。

```javascript
function clownsEverywhere(param1, param2) {
  /* ... */
}

clownsEverywhere("foo", "bar");
```

这样的规定也使得，函数参数与数组和对象的尾逗号规则，保持一致了。

##### Function.prototype.toString()

[ES2019](https://github.com/tc39/Function-prototype-toString-revision) 对函数实例的`toString()`方法做出了修改。

`toString()`方法返回函数代码本身，以前会省略注释和空格。

```javascript
function /* foo comment */ foo() {}

foo.toString();
// function foo() {}
```

上面代码中，函数`foo`的原始代码包含注释，函数名`foo`和圆括号之间有空格，但是`toString()`方法都把它们省略了。

修改后的`toString()`方法，明确要求返回一模一样的原始代码。

```javascript
function /* foo comment */ foo() {}

foo.toString();
// "function /* foo comment */ foo () {}"
```

##### catch 命令的参数省略

JavaScript 语言的`try...catch`结构，以前明确要求`catch`命令后面必须跟参数，接受`try`代码块抛出的错误对象。

```javascript
try {
  // ...
} catch (err) {
  // 处理错误
}
```

上面代码中，`catch`命令后面带有参数`err`。

很多时候，`catch`代码块可能用不到这个参数。但是，为了保证语法正确，还是必须写。[ES2019](https://github.com/tc39/proposal-optional-catch-binding) 做出了改变，允许`catch`语句省略参数。

```javascript
try {
  // ...
} catch {
  // ...
}
```

#### 数组的扩展

##### 扩展运算符

###### 含义

扩展运算符（spread）是三个点（`...`）。它好比 rest 参数的逆运算，将一个数组转为用逗号分隔的参数序列。

```javascript
console.log(...[1, 2, 3])
// 1 2 3

console.log(1, ...[2, 3, 4], 5)
// 1 2 3 4 5

[...document.querySelectorAll('div')]
// [<div>, <div>, <div>]
```

该运算符主要用于函数调用。

```javascript
function push(array, ...items) {
  array.push(...items);
}

function add(x, y) {
  return x + y;
}

const numbers = [4, 38];
add(...numbers); // 42
```

上面代码中，`array.push(...items)`和`add(...numbers)`这两行，都是函数的调用，它们都使用了扩展运算符。该运算符将一个数组，变为参数序列。

扩展运算符与正常的函数参数可以结合使用，非常灵活。

```javascript
function f(v, w, x, y, z) {}
const args = [0, 1];
f(-1, ...args, 2, ...[3]);
```

扩展运算符后面还可以放置表达式。

```javascript
const arr = [...(x > 0 ? ["a"] : []), "b"];
```

如果扩展运算符后面是一个空数组，则不产生任何效果。

```javascript
[...[], 1];
// [1]
```

注意，只有函数调用时，扩展运算符才可以放在圆括号中，否则会报错。

```javascript
(...[1, 2])
// Uncaught SyntaxError: Unexpected number

console.log((...[1, 2]))
// Uncaught SyntaxError: Unexpected number

console.log(...[1, 2])
// 1 2
```

上面三种情况，扩展运算符都放在圆括号里面，但是前两种情况会报错，因为扩展运算符所在的括号不是函数调用。

###### 替代函数的 apply() 方法

由于扩展运算符可以展开数组，所以不再需要`apply()`方法将数组转为函数的参数了。

```javascript
// ES5 的写法
function f(x, y, z) {
  // ...
}
var args = [0, 1, 2];
f.apply(null, args);

// ES6 的写法
function f(x, y, z) {
  // ...
}
let args = [0, 1, 2];
f(...args);
```

下面是扩展运算符取代`apply()`方法的一个实际的例子，应用`Math.max()`方法，简化求出一个数组最大元素的写法。

```javascript
// ES5 的写法
Math.max.apply(null, [14, 3, 77]);

// ES6 的写法
Math.max(...[14, 3, 77]);

// 等同于
Math.max(14, 3, 77);
```

上面代码中，由于 JavaScript 不提供求数组最大元素的函数，所以只能套用`Math.max()`函数，将数组转为一个参数序列，然后求最大值。有了扩展运算符以后，就可以直接用`Math.max()`了。

另一个例子是通过`push()`函数，将一个数组添加到另一个数组的尾部。

```javascript
// ES5 的写法
var arr1 = [0, 1, 2];
var arr2 = [3, 4, 5];
Array.prototype.push.apply(arr1, arr2);

// ES6 的写法
let arr1 = [0, 1, 2];
let arr2 = [3, 4, 5];
arr1.push(...arr2);
```

上面代码的 ES5 写法中，`push()`方法的参数不能是数组，所以只好通过`apply()`方法变通使用`push()`方法。有了扩展运算符，就可以直接将数组传入`push()`方法。

下面是另外一个例子。

```javascript
// ES5
new (Date.bind.apply(Date, [null, 2015, 1, 1]))();

// ES6
new Date(...[2015, 1, 1]);
```

###### 扩展运算符的应用

**（1）复制数组**

数组是复合的数据类型，直接复制的话，只是复制了指向底层数据结构的指针，而不是克隆一个全新的数组。

```javascript
const a1 = [1, 2];
const a2 = a1;

a2[0] = 2;
a1; // [2, 2]
```

上面代码中，`a2`并不是`a1`的克隆，而是指向同一份数据的另一个指针。修改`a2`，会直接导致`a1`的变化。

ES5 只能用变通方法来复制数组。

```javascript
const a1 = [1, 2];
const a2 = a1.concat();

a2[0] = 2;
a1; // [1, 2]
```

上面代码中，`a1`会返回原数组的克隆，再修改`a2`就不会对`a1`产生影响。

扩展运算符提供了复制数组的简便写法。

```javascript
const a1 = [1, 2];
// 写法一
const a2 = [...a1];
// 写法二
const [...a2] = a1;
```

上面的两种写法，`a2`都是`a1`的克隆。

**（2）合并数组**

扩展运算符提供了数组合并的新写法。

```javascript
const arr1 = ["a", "b"];
const arr2 = ["c"];
const arr3 = ["d", "e"];

// ES5 的合并数组
arr1.concat(arr2, arr3);
// [ 'a', 'b', 'c', 'd', 'e' ]

// ES6 的合并数组
[...arr1, ...arr2, ...arr3];
// [ 'a', 'b', 'c', 'd', 'e' ]
```

不过，这两种方法都是浅拷贝，使用的时候需要注意。

```javascript
const a1 = [{ foo: 1 }];
const a2 = [{ bar: 2 }];

const a3 = a1.concat(a2);
const a4 = [...a1, ...a2];

a3[0] === a1[0]; // true
a4[0] === a1[0]; // true
```

上面代码中，`a3`和`a4`是用两种不同方法合并而成的新数组，但是它们的成员都是对原数组成员的引用，这就是浅拷贝。如果修改了引用指向的值，会同步反映到新数组。

**（3）与解构赋值结合**

扩展运算符可以与解构赋值结合起来，用于生成数组。

```javascript
// ES5
a = list[0], rest = list.slice(1)

// ES6
[a, ...rest] = list
```

下面是另外一些例子。

```javascript
const [first, ...rest] = [1, 2, 3, 4, 5];
first; // 1
rest; // [2, 3, 4, 5]

const [first, ...rest] = [];
first; // undefined
rest; // []

const [first, ...rest] = ["foo"];
first; // "foo"
rest; // []
```

如果将扩展运算符用于数组赋值，只能放在参数的最后一位，否则会报错。

```javascript
const [...butLast, last] = [1, 2, 3, 4, 5];
// 报错

const [first, ...middle, last] = [1, 2, 3, 4, 5];
// 报错
```

**（4）字符串**

扩展运算符还可以将字符串转为真正的数组。

```javascript
[..."hello"];
// [ "h", "e", "l", "l", "o" ]
```

上面的写法，有一个重要的好处，那就是能够正确识别四个字节的 Unicode 字符。

```javascript
'x\uD83D\uDE80y'.length // 4
[...'x\uD83D\uDE80y'].length // 3
```

上面代码的第一种写法，JavaScript 会将四个字节的 Unicode 字符，识别为 2 个字符，采用扩展运算符就没有这个问题。因此，正确返回字符串长度的函数，可以像下面这样写。

```javascript
function length(str) {
  return [...str].length;
}

length("x\uD83D\uDE80y"); // 3
```

凡是涉及到操作四个字节的 Unicode 字符的函数，都有这个问题。因此，最好都用扩展运算符改写。

```javascript
let str = 'x\uD83D\uDE80y';

str.split('').reverse().join('')
// 'y\uDE80\uD83Dx'

[...str].reverse().join('')
// 'y\uD83D\uDE80x'
```

上面代码中，如果不用扩展运算符，字符串的`reverse()`操作就不正确。

**（5）实现了 Iterator 接口的对象**

任何定义了遍历器（Iterator）接口的对象（参阅 Iterator 一章），都可以用扩展运算符转为真正的数组。

```javascript
let nodeList = document.querySelectorAll("div");
let array = [...nodeList];
```

上面代码中，`querySelectorAll()`方法返回的是一个`NodeList`对象。它不是数组，而是一个类似数组的对象。这时，扩展运算符可以将其转为真正的数组，原因就在于`NodeList`对象实现了 Iterator。

```javascript
Number.prototype[Symbol.iterator] = function* () {
  let i = 0;
  let num = this.valueOf();
  while (i < num) {
    yield i++;
  }
};

console.log([...5]); // [0, 1, 2, 3, 4]
```

上面代码中，先定义了`Number`对象的遍历器接口，扩展运算符将`5`自动转成`Number`实例以后，就会调用这个接口，就会返回自定义的结果。

对于那些没有部署 Iterator 接口的类似数组的对象，扩展运算符就无法将其转为真正的数组。

```javascript
let arrayLike = {
  0: "a",
  1: "b",
  2: "c",
  length: 3,
};

// TypeError: Cannot spread non-iterable object.
let arr = [...arrayLike];
```

上面代码中，`arrayLike`是一个类似数组的对象，但是没有部署 Iterator 接口，扩展运算符就会报错。这时，可以改为使用`Array.from`方法将`arrayLike`转为真正的数组。

**（6）Map 和 Set 结构，Generator 函数**

扩展运算符内部调用的是数据结构的 Iterator 接口，因此只要具有 Iterator 接口的对象，都可以使用扩展运算符，比如 Map 结构。

```javascript
let map = new Map([
  [1, "one"],
  [2, "two"],
  [3, "three"],
]);

let arr = [...map.keys()]; // [1, 2, 3]
```

Generator 函数运行后，返回一个遍历器对象，因此也可以使用扩展运算符。

```javascript
const go = function* () {
  yield 1;
  yield 2;
  yield 3;
};

[...go()]; // [1, 2, 3]
```

上面代码中，变量`go`是一个 Generator 函数，执行后返回的是一个遍历器对象，对这个遍历器对象执行扩展运算符，就会将内部遍历得到的值，转为一个数组。

如果对没有 Iterator 接口的对象，使用扩展运算符，将会报错。

```javascript
const obj = { a: 1, b: 2 };
let arr = [...obj]; // TypeError: Cannot spread non-iterable object
```

##### Array.from()

`Array.from()`方法用于将两类对象转为真正的数组：类似数组的对象（array-like object）和可遍历（iterable）的对象（包括 ES6 新增的数据结构 Set 和 Map）。

下面是一个类似数组的对象，`Array.from()`将它转为真正的数组。

```javascript
let arrayLike = {
  0: "a",
  1: "b",
  2: "c",
  length: 3,
};

// ES5 的写法
var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

// ES6 的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']
```

实际应用中，常见的类似数组的对象是 DOM 操作返回的 NodeList 集合，以及函数内部的`arguments`对象。`Array.from()`都可以将它们转为真正的数组。

```javascript
// NodeList 对象
let ps = document.querySelectorAll("p");
Array.from(ps).filter((p) => {
  return p.textContent.length > 100;
});

// arguments 对象
function foo() {
  var args = Array.from(arguments);
  // ...
}
```

上面代码中，`querySelectorAll()`方法返回的是一个类似数组的对象，可以将这个对象转为真正的数组，再使用`filter()`方法。

只要是部署了 Iterator 接口的数据结构，`Array.from()`都能将其转为数组。

```javascript
Array.from("hello");
// ['h', 'e', 'l', 'l', 'o']

let namesSet = new Set(["a", "b"]);
Array.from(namesSet); // ['a', 'b']
```

上面代码中，字符串和 Set 结构都具有 Iterator 接口，因此可以被`Array.from()`转为真正的数组。

如果参数是一个真正的数组，`Array.from()`会返回一个一模一样的新数组。

```javascript
Array.from([1, 2, 3]);
// [1, 2, 3]
```

值得提醒的是，扩展运算符（`...`）也可以将某些数据结构转为数组。

```javascript
// arguments对象
function foo() {
  const args = [...arguments];
}

// NodeList对象
[...document.querySelectorAll("div")];
```

扩展运算符背后调用的是遍历器接口（`Symbol.iterator`），如果一个对象没有部署这个接口，就无法转换。`Array.from()`方法还支持类似数组的对象。所谓类似数组的对象，本质特征只有一点，即必须有`length`属性。因此，任何有`length`属性的对象，都可以通过`Array.from()`方法转为数组，而此时扩展运算符就无法转换。

```javascript
Array.from({ length: 3 });
// [ undefined, undefined, undefined ]
```

上面代码中，`Array.from()`返回了一个具有三个成员的数组，每个位置的值都是`undefined`。扩展运算符转换不了这个对象。

对于还没有部署该方法的浏览器，可以用`Array.prototype.slice()`方法替代。

```javascript
const toArray = (() =>
  Array.from ? Array.from : (obj) => [].slice.call(obj))();
```

`Array.from()`还可以接受一个函数作为第二个参数，作用类似于数组的`map()`方法，用来对每个元素进行处理，将处理后的值放入返回的数组。

```javascript
Array.from(arrayLike, (x) => x * x);
// 等同于
Array.from(arrayLike).map((x) => x * x);

Array.from([1, 2, 3], (x) => x * x);
// [1, 4, 9]
```

下面的例子是取出一组 DOM 节点的文本内容。

```javascript
let spans = document.querySelectorAll("span.name");

// map()
let names1 = Array.prototype.map.call(spans, (s) => s.textContent);

// Array.from()
let names2 = Array.from(spans, (s) => s.textContent);
```

下面的例子将数组中布尔值为`false`的成员转为`0`。

```javascript
Array.from([1, , 2, , 3], (n) => n || 0);
// [1, 0, 2, 0, 3]
```

另一个例子是返回各种数据的类型。

```javascript
function typesOf() {
  return Array.from(arguments, (value) => typeof value);
}
typesOf(null, [], NaN);
// ['object', 'object', 'number']
```

如果`map()`函数里面用到了`this`关键字，还可以传入`Array.from()`的第三个参数，用来绑定`this`。

`Array.from()`可以将各种值转为真正的数组，并且还提供`map`功能。这实际上意味着，只要有一个原始的数据结构，你就可以先对它的值进行处理，然后转成规范的数组结构，进而就可以使用数量众多的数组方法。

```javascript
Array.from({ length: 2 }, () => "jack");
// ['jack', 'jack']
```

上面代码中，`Array.from()`的第一个参数指定了第二个参数运行的次数。这种特性可以让该方法的用法变得非常灵活。

`Array.from()`的另一个应用是，将字符串转为数组，然后返回字符串的长度。因为它能正确处理各种 Unicode 字符，可以避免 JavaScript 将大于`\uFFFF`的 Unicode 字符，算作两个字符的 bug。

```javascript
function countSymbols(string) {
  return Array.from(string).length;
}
```

##### Array.of()

`Array.of()`方法用于将一组值，转换为数组。

```javascript
Array.of(3, 11, 8); // [3,11,8]
Array.of(3); // [3]
Array.of(3).length; // 1
```

这个方法的主要目的，是弥补数组构造函数`Array()`的不足。因为参数个数的不同，会导致`Array()`的行为有差异。

```javascript
Array(); // []
Array(3); // [, , ,]
Array(3, 11, 8); // [3, 11, 8]
```

上面代码中，`Array()`方法没有参数、一个参数、三个参数时，返回的结果都不一样。只有当参数个数不少于 2 个时，`Array()`才会返回由参数组成的新数组。参数只有一个正整数时，实际上是指定数组的长度。

`Array.of()`基本上可以用来替代`Array()`或`new Array()`，并且不存在由于参数不同而导致的重载。它的行为非常统一。

```javascript
Array.of(); // []
Array.of(undefined); // [undefined]
Array.of(1); // [1]
Array.of(1, 2); // [1, 2]
```

`Array.of()`总是返回参数值组成的数组。如果没有参数，就返回一个空数组。

`Array.of()`方法可以用下面的代码模拟实现。

```javascript
function ArrayOf() {
  return [].slice.call(arguments);
}
```

##### 实例方法：copyWithin()

数组实例的`copyWithin()`方法，在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组。也就是说，使用这个方法，会修改当前数组。

```javascript
Array.prototype.copyWithin(target, (start = 0), (end = this.length));
```

它接受三个参数。

- target（必需）：从该位置开始替换数据。如果为负值，表示倒数。
- start（可选）：从该位置开始读取数据，默认为 0。如果为负值，表示从末尾开始计算。
- end（可选）：到该位置前停止读取数据，默认等于数组长度。如果为负值，表示从末尾开始计算。

这三个参数都应该是数值，如果不是，会自动转为数值。

```javascript
[1, 2, 3, 4, 5].copyWithin(0, 3);
// [4, 5, 3, 4, 5]
```

上面代码表示将从 3 号位直到数组结束的成员（4 和 5），复制到从 0 号位开始的位置，结果覆盖了原来的 1 和 2。

下面是更多例子。

```javascript
// 将3号位复制到0号位
[1, 2, 3, 4, 5].copyWithin(0, 3, 4)
// [4, 2, 3, 4, 5]

// -2相当于3号位，-1相当于4号位
[1, 2, 3, 4, 5].copyWithin(0, -2, -1)
// [4, 2, 3, 4, 5]

// 将3号位复制到0号位
[].copyWithin.call({length: 5, 3: 1}, 0, 3)
// {0: 1, 3: 1, length: 5}

// 将2号位到数组结束，复制到0号位
let i32a = new Int32Array([1, 2, 3, 4, 5]);
i32a.copyWithin(0, 2);
// Int32Array [3, 4, 5, 4, 5]

// 对于没有部署 TypedArray 的 copyWithin 方法的平台
// 需要采用下面的写法
[].copyWithin.call(new Int32Array([1, 2, 3, 4, 5]), 0, 3, 4);
// Int32Array [4, 2, 3, 4, 5]
```

##### 实例方法：find()，findIndex()，findLast()，findLastIndex()

数组实例的`find()`方法，用于找出第一个符合条件的数组成员。它的参数是一个回调函数，所有数组成员依次执行该回调函数，直到找出第一个返回值为`true`的成员，然后返回该成员。如果没有符合条件的成员，则返回`undefined`。

```javascript
[1, 4, -5, 10].find((n) => n < 0);
// -5
```

上面代码找出数组中第一个小于 0 的成员。

```javascript
[1, 5, 10, 15].find(function (value, index, arr) {
  return value > 9;
}); // 10
```

上面代码中，`find()`方法的回调函数可以接受三个参数，依次为当前的值、当前的位置和原数组。

数组实例的`findIndex()`方法的用法与`find()`方法非常类似，返回第一个符合条件的数组成员的位置，如果所有成员都不符合条件，则返回`-1`。

```javascript
[1, 5, 10, 15].findIndex(function (value, index, arr) {
  return value > 9;
}); // 2
```

这两个方法都可以接受第二个参数，用来绑定回调函数的`this`对象。

```javascript
function f(v) {
  return v > this.age;
}
let person = { name: "John", age: 20 };
[10, 12, 26, 15].find(f, person); // 26
```

上面的代码中，`find()`函数接收了第二个参数`person`对象，回调函数中的`this`对象指向`person`对象。

另外，这两个方法都可以发现`NaN`，弥补了数组的`indexOf()`方法的不足。

```javascript
[NaN]
  .indexOf(NaN)
  // -1

  [NaN].findIndex((y) => Object.is(NaN, y));
// 0
```

上面代码中，`indexOf()`方法无法识别数组的`NaN`成员，但是`findIndex()`方法可以借助`Object.is()`方法做到。

`find()`和`findIndex()`都是从数组的 0 号位，依次向后检查。[ES2022](https://github.com/tc39/proposal-array-find-from-last) 新增了两个方法`findLast()`和`findLastIndex()`，从数组的最后一个成员开始，依次向前检查，其他都保持不变。

```javascript
const array = [{ value: 1 }, { value: 2 }, { value: 3 }, { value: 4 }];

array.findLast((n) => n.value % 2 === 1); // { value: 3 }
array.findLastIndex((n) => n.value % 2 === 1); // 2
```

上面示例中，`findLast()`和`findLastIndex()`从数组结尾开始，寻找第一个`value`属性为奇数的成员。结果，该成员是`{ value: 3 }`，位置是 2 号位。

##### 实例方法：fill()

`fill`方法使用给定值，填充一个数组。

```javascript
["a", "b", "c"].fill(7);
// [7, 7, 7]

new Array(3).fill(7);
// [7, 7, 7]
```

上面代码表明，`fill`方法用于空数组的初始化非常方便。数组中已有的元素，会被全部抹去。

`fill`方法还可以接受第二个和第三个参数，用于指定填充的起始位置和结束位置。

```javascript
["a", "b", "c"].fill(7, 1, 2);
// ['a', 7, 'c']
```

上面代码表示，`fill`方法从 1 号位开始，向原数组填充 7，到 2 号位之前结束。

注意，如果填充的类型为对象，那么被赋值的是同一个内存地址的对象，而不是深拷贝对象。

```javascript
let arr = new Array(3).fill({ name: "Mike" });
arr[0].name = "Ben";
arr;
// [{name: "Ben"}, {name: "Ben"}, {name: "Ben"}]

let arr = new Array(3).fill([]);
arr[0].push(5);
arr;
// [[5], [5], [5]]
```

##### 实例方法：entries()，keys() 和 values()

ES6 提供三个新的方法——`entries()`，`keys()`和`values()`——用于遍历数组。它们都返回一个遍历器对象（详见《Iterator》一章），可以用`for...of`循环进行遍历，唯一的区别是`keys()`是对键名的遍历、`values()`是对键值的遍历，`entries()`是对键值对的遍历。

```javascript
for (let index of ["a", "b"].keys()) {
  console.log(index);
}
// 0
// 1

for (let elem of ["a", "b"].values()) {
  console.log(elem);
}
// 'a'
// 'b'

for (let [index, elem] of ["a", "b"].entries()) {
  console.log(index, elem);
}
// 0 "a"
// 1 "b"
```

如果不使用`for...of`循环，可以手动调用遍历器对象的`next`方法，进行遍历。

```javascript
let letter = ["a", "b", "c"];
let entries = letter.entries();
console.log(entries.next().value); // [0, 'a']
console.log(entries.next().value); // [1, 'b']
console.log(entries.next().value); // [2, 'c']
```

##### 实例方法：includes()

`Array.prototype.includes`方法返回一个布尔值，表示某个数组是否包含给定的值，与字符串的`includes`方法类似。ES2016 引入了该方法。

```javascript
[1, 2, 3]
  .includes(2) // true
  [(1, 2, 3)].includes(4) // false
  [(1, 2, NaN)].includes(NaN); // true
```

该方法的第二个参数表示搜索的起始位置，默认为`0`。如果第二个参数为负数，则表示倒数的位置，如果这时它大于数组长度（比如第二个参数为`-4`，但数组长度为`3`），则会重置为从`0`开始。

```javascript
[1, 2, 3].includes(3, 3); // false
[1, 2, 3].includes(3, -1); // true
```

没有该方法之前，我们通常使用数组的`indexOf`方法，检查是否包含某个值。

```javascript
if (arr.indexOf(el) !== -1) {
  // ...
}
```

`indexOf`方法有两个缺点，一是不够语义化，它的含义是找到参数值的第一个出现位置，所以要去比较是否不等于`-1`，表达起来不够直观。二是，它内部使用严格相等运算符（`===`）进行判断，这会导致对`NaN`的误判。

```javascript
[NaN].indexOf(NaN);
// -1
```

`includes`使用的是不一样的判断算法，就没有这个问题。

```javascript
[NaN].includes(NaN);
// true
```

下面代码用来检查当前环境是否支持该方法，如果不支持，部署一个简易的替代版本。

```javascript
const contains = (() =>
  Array.prototype.includes
    ? (arr, value) => arr.includes(value)
    : (arr, value) => arr.some((el) => el === value))();
contains(["foo", "bar"], "baz"); // => false
```

另外，Map 和 Set 数据结构有一个`has`方法，需要注意与`includes`区分。

- Map 结构的`has`方法，是用来查找键名的，比如`Map.prototype.has(key)`、`WeakMap.prototype.has(key)`、`Reflect.has(target, propertyKey)`。
- Set 结构的`has`方法，是用来查找值的，比如`Set.prototype.has(value)`、`WeakSet.prototype.has(value)`。

##### 实例方法：flat()，flatMap()

数组的成员有时还是数组，`Array.prototype.flat()`用于将嵌套的数组“拉平”，变成一维的数组。该方法返回一个新数组，对原数据没有影响。

```javascript
[1, 2, [3, 4]].flat();
// [1, 2, 3, 4]
```

上面代码中，原数组的成员里面有一个数组，`flat()`方法将子数组的成员取出来，添加在原来的位置。

`flat()`默认只会“拉平”一层，如果想要“拉平”多层的嵌套数组，可以将`flat()`方法的参数写成一个整数，表示想要拉平的层数，默认为 1。

```javascript
[1, 2, [3, [4, 5]]].flat()[
  // [1, 2, 3, [4, 5]]

  (1, 2, [3, [4, 5]])
].flat(2);
// [1, 2, 3, 4, 5]
```

上面代码中，`flat()`的参数为 2，表示要“拉平”两层的嵌套数组。

如果不管有多少层嵌套，都要转成一维数组，可以用`Infinity`关键字作为参数。

```javascript
[1, [2, [3]]].flat(Infinity);
// [1, 2, 3]
```

如果原数组有空位，`flat()`方法会跳过空位。

```javascript
[1, 2, , 4, 5].flat();
// [1, 2, 4, 5]
```

`flatMap()`方法对原数组的每个成员执行一个函数（相当于执行`Array.prototype.map()`），然后对返回值组成的数组执行`flat()`方法。该方法返回一个新数组，不改变原数组。

```javascript
// 相当于 [[2, 4], [3, 6], [4, 8]].flat()
[2, 3, 4].flatMap((x) => [x, x * 2]);
// [2, 4, 3, 6, 4, 8]
```

`flatMap()`只能展开一层数组。

```javascript
// 相当于 [[[2]], [[4]], [[6]], [[8]]].flat()
[1, 2, 3, 4].flatMap((x) => [[x * 2]]);
// [[2], [4], [6], [8]]
```

上面代码中，遍历函数返回的是一个双层的数组，但是默认只能展开一层，因此`flatMap()`返回的还是一个嵌套数组。

`flatMap()`方法的参数是一个遍历函数，该函数可以接受三个参数，分别是当前数组成员、当前数组成员的位置（从零开始）、原数组。

```javascript
arr.flatMap(function callback(currentValue[, index[, array]]) {
  // ...
}[, thisArg])
```

`flatMap()`方法还可以有第二个参数，用来绑定遍历函数里面的`this`。

##### 实例方法：at()

长久以来，JavaScript 不支持数组的负索引，如果要引用数组的最后一个成员，不能写成`arr[-1]`，只能使用`arr[arr.length - 1]`。

这是因为方括号运算符`[]`在 JavaScript 语言里面，不仅用于数组，还用于对象。对于对象来说，方括号里面就是键名，比如`obj[1]`引用的是键名为字符串`1`的键，同理`obj[-1]`引用的是键名为字符串`-1`的键。由于 JavaScript 的数组是特殊的对象，所以方括号里面的负数无法再有其他语义了，也就是说，不可能添加新语法来支持负索引。

为了解决这个问题，[ES2022](https://github.com/tc39/proposal-relative-indexing-method/) 为数组实例增加了`at()`方法，接受一个整数作为参数，返回对应位置的成员，并支持负索引。这个方法不仅可用于数组，也可用于字符串和类型数组（TypedArray）。

```javascript
const arr = [5, 12, 8, 130, 44];
arr.at(2); // 8
arr.at(-2); // 130
```

如果参数位置超出了数组范围，`at()`返回`undefined`。

```javascript
const sentence = "This is a sample sentence";

sentence.at(0); // 'T'
sentence.at(-1); // 'e'

sentence.at(-100); // undefined
sentence.at(100); // undefined
```

##### 实例方法：toReversed()，toSorted()，toSpliced()，with()

很多数组的传统方法会改变原数组，比如`push()`、`pop()`、`shift()`、`unshift()`等等。数组只要调用了这些方法，它的值就变了。现在有一个[提案](https://github.com/tc39/proposal-change-array-by-copy)，允许对数组进行操作时，不改变原数组，而返回一个原数组的拷贝。

这样的方法一共有四个。

- `Array.prototype.toReversed() -> Array`
- `Array.prototype.toSorted(compareFn) -> Array`
- `Array.prototype.toSpliced(start, deleteCount, ...items) -> Array`
- `Array.prototype.with(index, value) -> Array`

它们分别对应数组的原有方法。

- `toReversed()`对应`reverse()`，用来颠倒数组成员的位置。
- `toSorted()`对应`sort()`，用来对数组成员排序。
- `toSpliced()`对应`splice()`，用来在指定位置，删除指定数量的成员，并插入新成员。
- `with(index, value)`对应`splice(index, 1, value)`，用来将指定位置的成员替换为新的值。

上面是这四个新方法对应的原有方法，含义和用法完全一样，唯一不同的是不会改变原数组，而是返回原数组操作后的拷贝。

下面是示例。

```javascript
const sequence = [1, 2, 3];
sequence.toReversed(); // [3, 2, 1]
sequence; // [1, 2, 3]

const outOfOrder = [3, 1, 2];
outOfOrder.toSorted(); // [1, 2, 3]
outOfOrder; // [3, 1, 2]

const array = [1, 2, 3, 4];
array.toSpliced(1, 2, 5, 6, 7); // [1, 5, 6, 7, 4]
array; // [1, 2, 3, 4]

const correctionNeeded = [1, 1, 3];
correctionNeeded.with(1, 2); // [1, 2, 3]
correctionNeeded; // [1, 1, 3]
```

##### 实例方法：group()，groupToMap()

数组成员分组是一个常见需求，比如 SQL 有`GROUP BY`子句和函数式编程有 MapReduce 方法。现在有一个[提案](https://github.com/tc39/proposal-array-grouping)，为 JavaScript 新增了数组实例方法`group()`和`groupToMap()`，它们可以根据分组函数的运行结果，将数组成员分组。

`group()`的参数是一个分组函数，原数组的每个成员都会依次执行这个函数，确定自己是哪一个组。

```javascript
const array = [1, 2, 3, 4, 5];

array.group((num, index, array) => {
  return num % 2 === 0 ? "even" : "odd";
});
// { odd: [1, 3, 5], even: [2, 4] }
```

`group()`的分组函数可以接受三个参数，依次是数组的当前成员、该成员的位置序号、原数组（上例是`num`、`index`和`array`）。分组函数的返回值应该是字符串（或者可以自动转为字符串），以作为分组后的组名。

`group()`的返回值是一个对象，该对象的键名就是每一组的组名，即分组函数返回的每一个字符串（上例是`even`和`odd`）；该对象的键值是一个数组，包括所有产生当前键名的原数组成员。

下面是另一个例子。

```javascript
[6.1, 4.2, 6.3].groupBy(Math.floor);
// { '4': [4.2], '6': [6.1, 6.3] }
```

上面示例中，`Math.floor`作为分组函数，对原数组进行分组。它的返回值原本是数值，这时会自动转为字符串，作为分组的组名。原数组的成员根据分组函数的运行结果，进入对应的组。

`group()`还可以接受一个对象，作为第二个参数。该对象会绑定分组函数（第一个参数）里面的`this`，不过如果分组函数是一个箭头函数，该对象无效，因为箭头函数内部的`this`是固化的。

`groupToMap()`的作用和用法与`group()`完全一致，唯一的区别是返回值是一个 Map 结构，而不是对象。Map 结构的键名可以是各种值，所以不管分组函数返回什么值，都会直接作为组名（Map 结构的键名），不会强制转为字符串。这对于分组函数返回值是对象的情况，尤其有用。

```javascript
const array = [1, 2, 3, 4, 5];

const odd = { odd: true };
const even = { even: true };
array.groupToMap((num, index, array) => {
  return num % 2 === 0 ? even : odd;
});
//  Map { {odd: true}: [1, 3, 5], {even: true}: [2, 4] }
```

上面示例返回的是一个 Map 结构，它的键名就是分组函数返回的两个对象`odd`和`even`。

总之，按照字符串分组就使用`group()`，按照对象分组就使用`groupToMap()`。

##### 数组的空位

数组的空位指的是，数组的某一个位置没有任何值，比如`Array()`构造函数返回的数组都是空位。

```javascript
Array(3); // [, , ,]
```

上面代码中，`Array(3)`返回一个具有 3 个空位的数组。

注意，空位不是`undefined`，某一个位置的值等于`undefined`，依然是有值的。空位是没有任何值，`in`运算符可以说明这一点。

```javascript
0 in [undefined, undefined, undefined]; // true
0 in [, , ,]; // false
```

上面代码说明，第一个数组的 0 号位置是有值的，第二个数组的 0 号位置没有值。

ES5 对空位的处理，已经很不一致了，大多数情况下会忽略空位。

- `forEach()`, `filter()`, `reduce()`, `every()` 和`some()`都会跳过空位。
- `map()`会跳过空位，但会保留这个值
- `join()`和`toString()`会将空位视为`undefined`，而`undefined`和`null`会被处理成空字符串。

```javascript
// forEach方法
[,'a'].forEach((x,i) => console.log(i)); // 1

// filter方法
['a',,'b'].filter(x => true) // ['a','b']

// every方法
[,'a'].every(x => x==='a') // true

// reduce方法
[1,,2].reduce((x,y) => x+y) // 3

// some方法
[,'a'].some(x => x !== 'a') // false

// map方法
[,'a'].map(x => 1) // [,1]

// join方法
[,'a',undefined,null].join('#') // "#a##"

// toString方法
[,'a',undefined,null].toString() // ",a,,"
```

ES6 则是明确将空位转为`undefined`。

`Array.from()`方法会将数组的空位，转为`undefined`，也就是说，这个方法不会忽略空位。

```javascript
Array.from(["a", , "b"]);
// [ "a", undefined, "b" ]
```

扩展运算符（`...`）也会将空位转为`undefined`。

```javascript
[...["a", , "b"]];
// [ "a", undefined, "b" ]
```

`copyWithin()`会连空位一起拷贝。

```javascript
[, "a", "b", ,].copyWithin(2, 0); // [,"a",,"a"]
```

`fill()`会将空位视为正常的数组位置。

```javascript
new Array(3).fill("a"); // ["a","a","a"]
```

`for...of`循环也会遍历空位。

```javascript
let arr = [, ,];
for (let i of arr) {
  console.log(1);
}
// 1
// 1
```

上面代码中，数组`arr`有两个空位，`for...of`并没有忽略它们。如果改成`map()`方法遍历，空位是会跳过的。

`entries()`、`keys()`、`values()`、`find()`和`findIndex()`会将空位处理成`undefined`。

```javascript
// entries()
[...[,'a'].entries()] // [[0,undefined], [1,"a"]]

// keys()
[...[,'a'].keys()] // [0,1]

// values()
[...[,'a'].values()] // [undefined,"a"]

// find()
[,'a'].find(x => true) // undefined

// findIndex()
[,'a'].findIndex(x => true) // 0
```

由于空位的处理规则非常不统一，所以建议避免出现空位。

##### Array.prototype.sort() 的排序稳定性

排序稳定性（stable sorting）是排序算法的重要属性，指的是排序关键字相同的项目，排序前后的顺序不变。

```javascript
const arr = ["peach", "straw", "apple", "spork"];

const stableSorting = (s1, s2) => {
  if (s1[0] < s2[0]) return -1;
  return 1;
};

arr.sort(stableSorting);
// ["apple", "peach", "straw", "spork"]
```

上面代码对数组`arr`按照首字母进行排序。排序结果中，`straw`在`spork`的前面，跟原始顺序一致，所以排序算法`stableSorting`是稳定排序。

```javascript
const unstableSorting = (s1, s2) => {
  if (s1[0] <= s2[0]) return -1;
  return 1;
};

arr.sort(unstableSorting);
// ["apple", "peach", "spork", "straw"]
```

上面代码中，排序结果是`spork`在`straw`前面，跟原始顺序相反，所以排序算法`unstableSorting`是不稳定的。

常见的排序算法之中，插入排序、合并排序、冒泡排序等都是稳定的，堆排序、快速排序等是不稳定的。不稳定排序的主要缺点是，多重排序时可能会产生问题。假设有一个姓和名的列表，要求按照“姓氏为主要关键字，名字为次要关键字”进行排序。开发者可能会先按名字排序，再按姓氏进行排序。如果排序算法是稳定的，这样就可以达到“先姓氏，后名字”的排序效果。如果是不稳定的，就不行。

早先的 ECMAScript 没有规定，`Array.prototype.sort()`的默认排序算法是否稳定，留给浏览器自己决定，这导致某些实现是不稳定的。[ES2019](https://github.com/tc39/ecma262/pull/1340) 明确规定，`Array.prototype.sort()`的默认排序算法必须稳定。这个规定已经做到了，现在 JavaScript 各个主要实现的默认排序算法都是稳定的。

### 构造 Date 对象的字符串格式问题

JavaScript 构造 Date 对象时要传的字符串标准格式为 `yyyy/MM/dd HH:mm:ss`，正常情况下日期字符串的格式为 `yyyy-MM-dd HH:mm:ss` ，无法直接使用(Chrome 可以，IE 不可以)。需要字符串替换后使用 `replace(/-/g,"/")`。
