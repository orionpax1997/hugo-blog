---
title: "使用 Surfingkeys 以 VIM 的方式操作你的浏览器"
date: 2021-11-23T09:15:25+08:00
tags: ["Essay"]
series: ["生命不息 折腾不止"]
---

## 简介

Surfingkeys 和现有的一些插件一样，让你尽可能的通过键盘来使用 Chrome/Firefox 浏览器，比如跳转网页，上下左右滚屏。但不只是给 vim 用户使用，Surfingkeys 的基本特性是让你自己写一段 Javascript 脚本，然后通过`mapkey`映射到某些按键。之后当你按了那几个键以后，对应的 Javascript 脚本就会被执行。

## 安装

{{< card "https://chrome.google.com/webstore/detail/surfingkeys/gfbliohnnapiefjpjlpjnehglfpaknnc" >}}
{{< card "https://addons.mozilla.org/en-US/firefox/addon/surfingkeys_ff/" >}}
{{< card "https://microsoftedge.microsoft.com/addons/detail/kgnghhfkloifoabeaobjkgagcecbnppg" >}}

## 配置

```jsx
// 按键映射
cmap("<Ctrl-j>", "<ArrowDown>");
cmap("<Ctrl-k>", "<ArrowDown>");
```

## 默认快捷键

### 帮助

| 操作      | 功能                                                    |
| --------- | ------------------------------------------------------- |
| `<Alt-s>` | 在当前网站开关 SurfingKeys                              |
| ;ql       | 显示最近一次操作                                        |
| .         | 重复最近一次操作                                        |
| ?         | 查看帮助                                                |
| `<Alt-i>` | 进入 PassThrough 模式，暂时放弃 SurfingKeys             |
| p         | 进入 PassThrough 模式，暂时放弃 SurfingKeys, 1 秒后恢复 |

### 鼠标点击

| 操作       | 功能                                                                        |
| ---------- | --------------------------------------------------------------------------- |
| cf         | 在新标签页打开多个链接                                                      |
| gf         | 在新标签页后台打开链接                                                      |
| gi         | 跳到第一个输入框                                                            |
| f          | Open a link, press SHIFT to flip overlapped hints, hold SPACE to hide hints |
| ;fs        | Display hints to focus scrollable elements                                  |
| ;m         | 把鼠标移出最近的元素                                                        |
| ;di        | 下载图片                                                                    |
| af         | 在新标签页打开链接                                                          |
| C          | 在新标签页后台打开链接                                                      |
| `<Ctrl-h>` | 触发元素的鼠标移入事件                                                      |
| `<Ctrl-j>` | 触发元素的鼠标移出事件                                                      |
| i          | 选择输入框                                                                  |
| I          | 选择输入框，并打开 VIM 编辑器                                               |
| O          | 打开文字中的超级链接                                                        |
| `<Ctrl-i>` | 选择输入框，并打开 VIM 编辑器                                               |
| q          | 点击图片或按钮                                                              |
| [[         | 点击当前页上的上一页链接                                                    |
| ]]         | 点击当前页上的下一页链接                                                    |
| #          | 滚动页面／元素                                                              |
| 0          | 滚到最左边                                                                  |
| cS         | 重置滚动目标                                                                |
| cs         | 切换滚动目标                                                                |
| e          | Scroll half page up                                                         |
| d          | Scroll half page down                                                       |
| gg         | 滚到最上边                                                                  |
| G          | 滚到最下边                                                                  |
| j          | 向下滚动                                                                    |
| k          | 向上滚动                                                                    |
| h          | 向左滚动                                                                    |
| l          | 向右滚动                                                                    |
| $          | 滚到最右边                                                                  |
| %          | 滚动百分之 x                                                                |
| ;w         | 聚焦到主窗口                                                                |
| u          | Scroll half page up                                                         |
| w          | 切换 frames                                                                 |

### 标签页

| 操作      | 功能                           |
| --------- | ------------------------------ |
| yt        | 复制当前标签页                 |
| yT        | 在后台复制当前标签页           |
| g0        | 跳到第一个标签页               |
| g$        | 跳到最后一个标签页             |
| gx0       | 关闭左侧所有标签页             |
| gxt       | 关闭左侧标签页                 |
| gxT       | 关闭右侧标签页                 |
| gx$       | 关闭右侧所有标签页             |
| gxx       | 关闭当前标签页之外的所有标签页 |
| E         | 跳到左侧标签页                 |
| R         | 跳到右侧标签页                 |
| zr        | 重置缩放比例                   |
| zi        | 放大页面                       |
| zo        | 缩小页面                       |
| T         | 选择标签页                     |
| `<Alt-p>` | 固定／解除固定当前标签页       |
| `<Alt-m>` | 静音／解除静音当前标签页       |
| on        | 打开新标签                     |
| x         | 关闭当前标签页                 |
| X         | 恢复刚关闭的标签页             |
| W         | 把当前标签页移入新窗口         |
| <<        | 往左移动当前标签页             |
| >>        | 往右移动当前标签页             |

### 网页浏览

| 操作       | 功能                                         |
| ---------- | -------------------------------------------- |
| gT         | 跳到最早的那个标签页                         |
| gt         | 跳到最新的那个标签页                         |
| gu         | 跳到当前地址的上一级                         |
| g?         | 移除当前网址中的查询参数（问号后的所有部分） |
| g#         | 移除当前网址中#后的所有部分                  |
| gU         | 跳到当前地址的根路径                         |
| ;u         | 用 VIM 编辑器编辑当前地址，并在新标签页打开  |
| ;U         | 用 VIM 编辑器编辑当前地址，并刷新            |
| B          | 返回前一个标签页                             |
| F          | 往后一个标签页                               |
| `<Ctrl-6>` | 切换到最近使用的前一个标签页                 |
| S          | 后退                                         |
| D          | 前进                                         |
| r          | 刷新当前页                                   |

### 会话

| 操作 | 功能             |
| ---- | ---------------- |
| ZZ   | 保存会话并退出   |
| ZR   | 恢复最近一次会话 |

### 搜索选中文本

| 操作 | 功能                           |
| ---- | ------------------------------ |
| sg   | 用谷歌搜索选中文本             |
| sd   | 用 duckduckgo 搜索选中文本     |
| sb   | 用百度搜索选中文本             |
| se   | Search selected with wikipedia |
| sw   | 用必应搜索选中文本             |
| ss   | 用 stackoverflow 搜索选中文本  |
| sh   | 用 github 搜索选中文本         |
| sy   | Search selected with youtube   |

### 剪贴板

| 操作 | 功能                               |
| ---- | ---------------------------------- |
| yG   | 截长屏                             |
| yS   | 截当前滚动元素                     |
| ya   | 复制链接                           |
| yma  | 选择复制多个链接                   |
| ymc  | 复制一个表格的多列                 |
| ymv  | 选择复制多个指定文本               |
| yc   | 复制表格的一列                     |
| yq   | 复制 pre 文本                      |
| yv   | 选择复制指定文本                   |
| yi   | 复制输入框中内容                   |
| ys   | 复制当前页源码                     |
| yj   | 复制当前设置                       |
| yd   | 复制当前正在下载的链接             |
| yy   | 复制当前地址                       |
| yh   | 复制当前域名                       |
| yl   | 复制当前页标题                     |
| yQ   | 复制所有翻译历史                   |
| yf   | 复制当前页的表单数据，用 JSON 格式 |
| yg   | 截屏                               |
| yp   | 复制当前页的表单数据               |
| cq   | 选词翻译                           |
| cc   | 打开选中的网址或系统剪贴板里的网址 |
| ;pj  | 从剪贴板恢复数据                   |
| ;pf  | 用 yf 复制出来的结果填充表单       |
| ;pp  | 在当前页粘贴 HTML                  |

### 搜索栏

| 操作            | 功能                                     |
| --------------- | ---------------------------------------- |
| go              | 在当前标签页打开网页                     |
| ab              | 收藏当前页面                             |
| t               | 打开网页                                 |
| oi              | 打开隐身窗口                             |
| ox              | 打开搜索栏查找最近关闭的网址             |
| oh              | 打开搜索栏查找访问历史                   |
| om              | 打开搜索栏查找类 VIM 标签                |
| ob              | 打开百度搜索栏                           |
| og              | 打开谷歌搜索栏                           |
| od              | 打开 duckduckgo 搜索栏                   |
| ow              | 打开必应搜索栏                           |
| oy              | 打开 Youtube 搜索栏                      |
| H               | 打开搜索栏查找当前标签页访问过的所有网址 |
| Q               | 打开搜索栏查单词                         |
| b               | 打开一个收藏                             |
| :               | 打开命令                                 |
| `<Ctrl-d>`      | 从收藏夹或访问历史中删除选中条目         |
| `<Ctrl-i>`      | 用 VIM 编辑器编辑选中 URL 再打开         |
| `<Ctrl-j>`      | 切换搜索栏位置                           |
| `<Ctrl-.>`      | 显示下一页搜索结果                       |
| `<Ctrl-,>`      | 显示上一页搜索结果                       |
| `<Ctrl-c>`      | 复制当前列出的结果                       |
| `<Ctrl-D>`      | 从收藏夹或访问记录中删除当前列出的结果   |
| `<Ctrl-r>`      | 按访问次数或最近访问时间重现排序         |
| `<Es>`          | 关闭搜索栏                               |
| `<Ctrl-m>`      | 为选中项目创建类 VIM 标签                |
| `<Tab>`         | 切到下一个条目                           |
| `<Shift-Tab>`   | 切回上一个条目                           |
| `<Ctrl-'>`      | 给当前输入加双引号                       |
| `<ArrowDown>`   | 切到下一个条目                           |
| `<ArrowUp>`     | 切回上一个条目                           |
| `<Ctrl-n>`      | 切到下一个条目                           |
| `<Ctrl-p>`      | 切回上一个条目                           |
| #               | 可视模式                                 |
| v               | 切换可视模式                             |
| /               | 在当前页查找                             |
| n               | 下一处                                   |
| N               | 上一处                                   |
| zv              | 进入可视模式，并全选指定文本             |
| V               | 恢复可视模式                             |
| `\*`            | 在当前页查找选中文本                     |
| 0               | 跳到行首                                 |
| l               | 前进一个字符                             |
| h               | 后退一个字符                             |
| j               | 下一行                                   |
| k               | 上一行                                   |
| w               | 前进一个单词                             |
| e               | 前进一个单词                             |
| b               | 后退一个单词                             |
| )               | 前进一个句子                             |
| (               | 后退一个句子                             |
| }               | 前进一个段落                             |
| {               | 后退一个段落                             |
| $               | 跳到行尾                                 |
| G               | 跳到页面结尾                             |
| gg              | 跳到页面开头                             |
| gr              | 电脑语音阅读选中文本                     |
| o               | 把光标定位到高亮区域到另一端             |
| `\*`            | 查找光标下的单词                         |
| `<Enter>`       | 点击光标下的元素                         |
| `<Shift-Enter>` | 点击光标下的元素                         |
| zz              | 把光标所在的位置放在屏幕中间             |
| f               | 往前查找字符                             |
| F               | 往后查找字符                             |
| ;               | 重复相应的 f/F                           |
| ,               | 反向重复相应的 f/F                       |
| p               | Expand selection to parent element       |
| q               | 翻译光标下的单词                         |
| V               | 选中一个单词(w)／行(l)／句子(s)／段落(p) |
| `<Ctrl-u>`      | 往上 20 行                               |
| `<Ctrl-d>`      | 向下 20 行                               |
| t               | 用谷歌翻译选中文本                       |
| #               | 类 VIM 标签                              |
| m               | 为当前 URL 设置类 VIM 标示               |
| '               | 访问类 VIM 标签                          |
| `<Ctrl-'>`      | 在新标签页里访问类 VIM 标签              |

### 设置

| 操作           | 功能                    |
| -------------- | ----------------------- |
| ;pm            | 预览 markdown           |
| ;e             | 编辑设置                |
| `<Ctrl-Alt-d>` | 打开 Mermaid 图形生成器 |

### Chrome 内置功能

| 操作 | 功能                 |
| ---- | -------------------- |
| ga   | 打开关于             |
| gb   | 打开收藏夹           |
| gc   | 打开缓存             |
| gd   | 打开下载             |
| gh   | 打开历史记录         |
| gk   | 打开 Cookies         |
| ge   | 打开扩展             |
| gn   | 打开 net-internals   |
| gs   | 查看网页源码         |
| ;i   | 打开审查元素         |
| ;j   | 关闭下载完毕的提示框 |

### 代理

| 操作 | 功能                         |
| ---- | ---------------------------- |
| cp   | 为当前网址开关代理           |
| ;cp  | 复制代理信息                 |
| ;ap  | 应用剪贴板中的代理信息       |
| ;pa  | 一直使用代理                 |
| ;pb  | 只针对加入列表的站点使用代理 |
| ;pd  | 不使用代理                   |
| ;ps  | 使用系统设置                 |
| ;pc  | Surfingkeys 放弃代理设置     |

### 其它

| 操作 | 功能                                 |
| ---- | ------------------------------------ |
| gr   | 电脑语音阅读选中文本或剪贴板里的文本 |
| ;s   | 切换 PDF 阅读器                      |
| ;dh  | 删除 30 天前的所有访问历史记录       |
| ;db  | 从收藏夹里删除当前网址               |
| ;t   | 用谷歌翻译选中文本                   |

### 插入模式

| 操作       | 功能                        |
| ---------- | --------------------------- |
| `<Ctrl-e>` | 把光标放到行尾              |
| `<Ctrl-f>` | 把光标放到行首              |
| `<Ctrl-u>` | 删除光标前的所有字符        |
| `<Alt-b>`  | 把光标往后移一个单词        |
| `<Alt-f>`  | 把光标往前移一个单词        |
| `<Alt-w>`  | 删除光标前一个单词          |
| `<Alt-d>`  | 删除光标后一个单词          |
| `<Esc>`    | 退出插入模式                |
| :          | 输入字符表情                |
| `<Ctrl-'>` | 给当前输入加双引号          |
| `<Ctrl-i>` | 打开 VIM 编辑器编辑当前输入 |

## 参考

{{< card "https://github.com/brookhong/Surfingkeys" >}}
{{< card "https://github.com/brookhong/Surfingkeys/blob/master/README_CN.md#%E5%8A%9F%E8%83%BD%E7%89%B9%E6%80%A7" >}}
