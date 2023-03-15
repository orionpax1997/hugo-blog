---
title: "SpaceVim 的使用"
date: 2023-03-09T14:09:38+08:00
categories: ["Geek"]
tags: ["Tool"]
series: ["生命不息 折腾不止"]
---

## 简介

SpaceVim 是一个社区驱动的 Vim 和 Neovim 发行版。它的灵感来自 spacemacs。它分层管理插件集合，这有助于将相关包收集在一起以提供功能。这种方法有助于保持配置井井有条，并通过让用户不必考虑要安装哪些包来减少用户的开销。

## 入门

{{< card "https://spacevim.org/quick-start-guide/" >}}

## 文档

{{< card "https://spacevim.org/documentation/" >}}

## 可用层

{{< card "https://spacevim.org/layers/" >}}

## 配置

```toml
#=============================================================================
# Copyright (c) 2019-2023 Humble.Xiang
# Author: Humble.Xiang < humble.xiang@gmail.com >
# URL: https://blog.humblex.top/
# License: GPLv3
#=============================================================================

[options]
    # 顶部标签列表序号类型
    buffer_index_type = 4
    # 引导函数，配置原生键位映射
    bootstrap_after = "myspacevim#after"
    # 主题
    colorscheme = "onedark"
    # 中文帮助
    vim_help_language = "cn"
    # 启用真彩色
    enable_guicolors = true
    # 顶部标签栏上的文件类型图标
    enable_tabline_filetype_icon = true
    # 状态栏上显示当前模式
    enable_statusline_mode = true
    # 文件树从左侧唤出
    filetree_direction = "left"
    # 文件树使用 defx
    filemanager = "defx"
    # 字体
    guifont = "FiraCode Nerd Font"
    # 活动窗口状态栏上的分割符号形状
    statusline_separator = "arrow"
    # 非活动窗口状态栏上的分割符号形状
    statusline_iseparator = "arrow"

# 自动补全
[[layers]]
name = 'autocomplete'
# Enter complete 完成当前选择
auto_completion_return_key_behavior = "complete"
# Tab smart 循环候选、扩展片段、跳转参数
auto_completion_tab_key_behavior = "smart"

# 中文
[[layers]]
name = "chinese"

# 主题
[[layers]]
name = "colorscheme"

# 核心
[[layers]]
name = 'core'
# 显示隐藏文件
filetree_show_hidden = true
# 文件树中显示 git 状态
enable_filetree_gitstatus = true

# 格式化
[[layers]]
name = "format"
# 保存时格式化
format_on_save = true

# Git
[[layers]]
name = "git"
git_plugin = 'fugitive'

# Shell
[[layers]]
name = 'shell'
# 设置 Shell 从底部唤出
default_position = 'bottom'

# 更好的高亮
[[layers]]
name = "treesitter"

# 模糊查询
[[layers]]
name = "telescope"

# 版本控制
[[layers]]
name = "VersionControl"

# 笔记 不加 telescope 启动会报错
[[layers]]
name = "zettelkasten"
```

## 应用场景

### 跳跃、加入和分裂

前缀`SPC j`用于跳跃、连接和拆分。

#### 跳跃

| 按键绑定  | 说明                                      |
| :-------- | :---------------------------------------- |
| `SPC j $` | 转到行尾（并在行中的前一个位置设置标记）  |
| `SPC j 0` | 转到行首（并在行中的前一个位置设置标记）  |
| `SPC j b` | 向后跳                                    |
| `SPC j c` | 跳转到上次更改                            |
| `SPC j d` | 跳转到当前目录的列表                      |
| `SPC j D` | 跳转到当前目录的列表（其他窗口）          |
| `SPC j f` | 向前跳                                    |
| `SPC j I` | 跳转到任何缓冲区中的定义（明确轮廓）      |
| `SPC j i` | 跳转到缓冲区中的定义（明确轮廓）          |
| `SPC j j` | 跳转到缓冲区中的一个字符（easymotion）    |
| `SPC j J` | 跳转到缓冲区中的一组两个字符 (easymotion) |
| `SPC j k` | 跳转到下一行并使用自动缩进规则缩进        |
| `SPC j l` | 使用 avy (easymotion) 跳转到一行          |
| `SPC j q` | 显示 dumb-jump quick look 工具提示 (TODO) |
| `SPC j u` | 跳转到当前窗口中的 URL                    |
| `SPC j v` | 跳转到 Emacs Lisp 变量的定义/声明 (TODO)  |
| `SPC j w` | 跳转到当前缓冲区中的一个词 (easymotion)   |

#### 加入和分裂

| 按键绑定  | 说明                                                      |
| :-------- | :-------------------------------------------------------- |
| `J`       | 加入当前行与下一行                                        |
| `SPC j o` | 将代码块连接到单行语句中                                  |
| `SPC j m` | 将单行拆分为多行                                          |
| `SPC j k` | 转到下一行并使用自动缩进规则缩进                          |
| `SPC j n` | 在点处拆分当前行，插入新行并自动缩进                      |
| `SPC j o` | 在 point 处拆分当前行，但让 point 在当前行上              |
| `SPC j s` | 就地拆分带引号的字符串或 s-expression                     |
| `SPC j S` | 用 拆分带引号的字符串或 s-expression `\n`，并自动缩进新行 |

### 编辑

#### 扩展文本区域

| 按键绑定 | 说明                             |
| :------- | :------------------------------- |
| `v`      | 将文本的视觉选择扩展到更大的区域 |
| `V`      | 将文本的视觉选择缩小到较小的区域 |

#### 复制和粘贴

| 按键绑定     | 说明                             |
| :----------- | :------------------------------- |
| `<Leader> y` | 将所选文本复制到系统剪贴板       |
| `<Leader> p` | 在此处之后粘贴系统剪贴板中的文本 |

#### 增加/减少数字

| 按键绑定  | 说明                         |
| :-------- | :--------------------------- |
| `SPC n +` | 将光标下的数字加一并启动瞬态 |
| `SPC n -` | 将光标下的数字减一并启动瞬态 |

在瞬态：

| 按键绑定   | 说明               |
| :--------- | :----------------- |
| `+`        | 将光标下的数字加一 |
| `-`        | 将光标下的数字减一 |
| 任何其他键 | 离开过渡状态       |

**提示：**您可以使用前缀参数设置步长（默认为 1）（即`10 SPC n +`会将光标下的数字加 10）

#### 用 iedit 替换文本

SpaceVim 使用强大的 iedit 模式来快速编辑多次出现的符号或选择。

**两种新模式：** `iedit-Normal` /`iedit-Insert`

iedit 的默认颜色是`red`/ `green`，它基于当前的配色方案。

**状态转换：**

| 按键绑定  | 描述                     |
| :-------- | :----------------------- |
| `SPC s e` | 使用所有匹配项启动 iedit |
| `SPC s E` | 仅使用当前匹配启动 iedit |

**在 iedit-Normal 模式下：**

`iedit-Normal`mode 继承自`Normal`mode，以下键绑定是特定于`iedit-Normal`mode 的。

| 按键绑定      | 说明                                         |
| :------------ | :------------------------------------------- |
| `<Esc>`       | 回到`Normal`模式                             |
| `i`           | 当前字符后的启动`iedit-Insert`模式           |
| `a`           | `iedit-Insert`当前字符之前的启动模式         |
| `I`           | 转到开头和启动`iedit-Insert`模式             |
| `A`           | 转到结束和开始`iedit-Insert`模式             |
| `<Left>`/`h`  | 向左移动光标                                 |
| `<Right>`/`l` | 向右移动光标                                 |
| `0`/`<Home>`  | 转到当前事件的开头                           |
| `$`/`<End>`   | 转到当前事件的末尾                           |
| `C`           | 从光标位置删除到结束和开始`iedit-Insert`模式 |
| `D`           | 删除事件                                     |
| `s`           | 删除光标下的字符并启动 iedit-Insert 模式     |
| `S`           | 删除事件并启动 iedit-Insert 模式             |
| `x`           | 删除所有出现的光标下的字符                   |
| `X`           | 删除所有出现的光标之前的字符                 |
| `gg`          | 去第一次出现                                 |
| `G`           | 转到最后一次出现                             |
| `f{char}`     | 第一次出现`{char}`在右边。                   |
| `n`           | 转到下一个事件                               |
| `N`           | 转到上一个事件                               |
| `p`           | 用最后被抽出（复制）的文本替换出现的地方     |
| `<Tab>`       | 切换当前事件                                 |
| `Ctrl-n`      | 前进并激活下一场比赛                         |
| `Ctrl-x`      | 停用当前比赛并继续前进                       |
| `Ctrl-p`      | 停用当前匹配项并向后移动                     |
| `e`           | 前进到词尾                                   |
| `w`           | 前进到下一个单词的开头                       |
| `b`           | 移动到当前单词的开头                         |

**在 iedit-Insert 模式下：**

| 按键绑定               | 说明                       |
| :--------------------- | :------------------------- |
| `Ctrl-g`/`<Esc>`       | 回到`iedit-Normal`模式     |
| `Ctrl-b`/`<Left>`      | 向左移动光标               |
| `Ctrl-f`/`<Right>`     | 向右移动光标               |
| `Ctrl-a`/`<Home>`      | 将光标移动到当前事件的开头 |
| `Ctrl-e`/`<End>`       | 将光标移动到当前事件的末尾 |
| `Ctrl-w`               | 删除光标前的单词           |
| `Ctrl-k`               | 删除光标后的所有单词       |
| `Ctrl-u`               | 删除光标前的所有字符       |
| `Ctrl-h`/`<Backspace>` | 删除光标前的字符           |
| `<Delete>`             | 删除光标后的字符           |

### 文件树的使用

#### 文件树导航

导航以`hjkl`按键为中心，希望提供像[vifm](https://github.com/vifm)中那样的快速导航体验

| 按键绑定         | 说明                           |
| :--------------- | :----------------------------- |
| `<F3>`/`SPC f t` | 切换文件资源管理器             |
| **在文件树中**   |                                |
| `<Left>`/`h`     | 转到父节点并折叠展开的目录     |
| `<Down>`/`j`     | 选择下一个文件或目录           |
| `<Up>`/`k`       | 选择上一个文件或目录           |
| `<right>`/`l`    | 打开选定的文件或展开目录       |
| `<Enter>`        | 打开文件或切换到目录           |
| `N`              | 在光标下创建新文件             |
| `r`              | 重命名光标下的文件             |
| `d`              | 删除光标下的文件               |
| `K`              | 在光标下创建新目录             |
| `y y`            | 将文件完整路径复制到系统剪贴板 |
| `y Y`            | 将文件复制到系统剪贴板         |
| `P`              | 将文件粘贴到光标下的位置       |
| `.`              | 切换隐藏文件                   |
| `s v`            | 拆分编辑                       |
| `s g`            | 垂直分割编辑                   |
| `p`              | 预览                           |
| `i`              | 切换到目录历史                 |
| `v`              | 快速查看                       |
| `g x`            | 与 vimfiler 关联执行           |
| `'`              | 切换标记当前行                 |
| `V`              | 清除所有标记                   |
| `>`              | 增加文件树屏幕宽度             |
| `<`              | 减少文件树屏幕宽度             |
| `<Home>`         | 跳转到第一行                   |
| `<End>`          | 跳转到最后一行                 |
| `Ctrl-Home`      | 切换到项目根目录               |
| `Ctrl-r`         | 重绘                           |

#### 使用文件树打开文件

如果只打开一个文件缓冲区，则在活动窗口中打开一个文件，否则我们需要使用 vim-choosewin 来选择一个窗口打开文件

| 按键绑定      | 说明                     |
| :------------ | :----------------------- |
| `l`/`<Enter>` | 在一个窗口中打开文件     |
| `s g`         | 在垂直分割窗口中打开文件 |
| `s v`         | 在水平分割窗口中打开文件 |

### 窗口管理器使用

窗口管理器键绑定只能在正常模式下使用。默认领导者`[WIN]`是，您可以通过以下部分`s`更改它：` windows_leader``[options] `

```
[options]
    windows_leader = "s"
```

| 按键绑定    | 说明                       |
| :---------- | :------------------------- |
| `q`         | 智能缓冲关闭               |
| `WIN v`     | ：分裂                     |
| `WIN V`     | 与前一个缓冲区分开         |
| `WIN g`     | :vsplit                    |
| `WIN G`     | 与前一个缓冲区垂直分割     |
| `WIN t`     | 打开新标签页 (:tabnew)     |
| `WIN o`     | 关闭其他窗口（：仅）       |
| `WIN x`     | 删除缓冲区，留下空白窗口   |
| `WIN q`     | 删除当前缓冲区             |
| `WIN Q`     | 关闭当前缓冲区 (:close)    |
| `Shift-Tab` | 切换到备用窗口（来回切换） |

SpaceVim 已经映射 normal `q`(record a macro) 为 smart buffer close，并且 record a macro (vim's `q`) 已经被映射到`<Leader> q r`，如果你想禁用这个特性，你可以使用`vimcompatible`mode.

#### 通用编辑器窗口

| 按键绑定     | 说明                         |
| :----------- | :--------------------------- |
| `<F2>`       | 切换标签栏                   |
| `<F3>`       | 切换 Vimfiler                |
| `Ctrl-Down`  | 移动到拆分下方 ( `Ctrl-w j`) |
| `Ctrl-Up`    | 移动到上拆分 ( `Ctrl-w k`)   |
| `Ctrl-Left`  | 向左移动拆分 ( `Ctrl-w h`)   |
| `Ctrl-Right` | 向右拆分 ( `Ctrl-w l`)       |

#### 窗口操作键绑定

每个窗口都有一个数字显示在状态行的开头，可以使用 快速访问`SPC number`。

| 按键绑定 | 说明        |
| :------- | :---------- |
| `SPC 1`  | 去 1 号窗口 |
| `SPC 2`  | 去 2 号窗口 |
| `SPC 3`  | 去 3 号窗口 |
| `SPC 4`  | 去 4 号窗口 |
| `SPC 5`  | 去 5 号窗口 |
| `SPC 6`  | 去 6 号窗口 |
| `SPC 7`  | 去 7 号窗口 |
| `SPC 8`  | 去 8 号窗口 |
| `SPC 9`  | 去 9 号窗口 |

Windows 操作命令（以 开头`w`）：

| 按键绑定            | 说明                                                    |
| :------------------ | :------------------------------------------------------ |
| `SPC w .`           | 窗口瞬态                                                |
| `SPC w <Tab>`       | 切换到当前帧中的备用窗口（来回切换）                    |
| `SPC w =`           | 平衡分割窗口                                            |
| `SPC w b`           | 强制焦点回到迷你缓冲区（TODO）                          |
| `SPC w c`           | 分心阅读当前窗口（工具层）                              |
| `SPC w C`           | 通过 vim-choosewin（工具层）无干扰阅读其他窗口          |
| `SPC w d`           | 删除一个窗口                                            |
| `SPC u SPC w d`     | 删除窗口及其当前缓冲区（不删除文件）（TODO）            |
| `SPC w D`           | 使用 vim-choosewin 删除另一个窗口                       |
| `SPC u SPC w D`     | 使用 vim-choosewin 删除另一个窗口及其当前缓冲区（TODO） |
| `SPC w t`           | 切换窗口专用（专用窗口不能被模式重用）（TODO）          |
| `SPC w f`           | 切换跟随模式                                            |
| `SPC w F`           | 创建新标签                                              |
| `SPC w h`           | 移动到左边的窗口                                        |
| `SPC w H`           | 向左移动窗口                                            |
| `SPC w j`           | 移动到下面的窗口                                        |
| `SPC w J`           | 将窗口移动到底部                                        |
| `SPC w k`           | 移动到上面的窗口                                        |
| `SPC w K`           | 将窗口移动到顶部                                        |
| `SPC w l`           | 移动到右边的窗口                                        |
| `SPC w L`           | 向右移动窗口                                            |
| `SPC w m`           | 最大化/最小化窗口                                       |
| `SPC w M`           | 使用 vim-choosewin 交换窗口                             |
| `SPC w o`           | 在选项卡之间循环和聚焦                                  |
| `SPC w p m`         | 在弹出窗口中打开消息缓冲区 (TODO)                       |
| `SPC w p p`         | 关闭当前的粘性弹出窗口 (TODO)                           |
| `SPC w r`           | 向前旋转窗口                                            |
| `SPC w R`           | 向后旋转窗口                                            |
| `SPC w s`/`SPC w -` | 水平分割                                                |
| `SPC w S`           | 水平拆分并聚焦新窗口                                    |
| `SPC w u`           | 撤消窗口布局                                            |
| `SPC w U`           | 重做窗口布局                                            |
| `SPC w v`/`SPC w /` | 垂直分割                                                |
| `SPC w V`           | 垂直拆分并聚焦新窗口                                    |
| `SPC w w`           | 窗口之间的循环和焦点                                    |
| `SPC w W`           | 使用 vim-choosewin 选择窗口                             |
| `SPC w x`           | 与下一个窗口交换当前窗口                                |

### Shell 使用

{{< card "https://spacevim.org/layers/shell/" >}}

### Git 使用

{{< card "https://spacevim.org/layers/git/" >}}

### 撤消树使用

撤消树将撤消历史可视化，可以更轻松地浏览和切换不同的撤消分支。默认键绑定是`F7`. 如果`+python`或`+python3`被启用，mundo 将被加载，否则 undotree 将被加载。

撤消树窗口中的键绑定：

| 按键绑定        | 描述           |
| :-------------- | :------------- |
| `G`             | 移至底部       |
| `J`             | 搬老写         |
| `K`             | 移动更新写入   |
| `N`             | 上一场比赛     |
| `P`             | 玩             |
| `<2-LeftMouse>` | 鼠标点击       |
| `/`             | 搜索           |
| `<CR>`          | 预览           |
| `d`             | 差异           |
| `<down>`        | 变老           |
| `<up>`          | 更新           |
| `i`             | 切换内联       |
| `j`             | 变老           |
| `k`             | 更新           |
| `n`             | 下一场比赛     |
| `o`             | 预览           |
| `p`             | 差分电流缓冲器 |
| `q`             | 辞职           |
| `r`             | 差异           |
| `gg`            | 移到顶部       |
| `?`             | 切换帮助       |

### 自定义 Snippets

{{< card "https://spacevim.org/layers/autocomplete/#completion-engine" >}}

### 自定义按键绑定

由于 toml 配置的局限性，SpaceVim 提供了两种启动函数 `bootstrap_before` 和 `bootstrap_after`，在该函数内可以使用 Vim script。 可通过 `~/.SpaceVim.d/init.toml` 的 `[options]` 片段中的这两个选项 `bootstrap_before` 和 `bootstrap_after` 来指定函数名称，例如：

```yaml
[options]
    bootstrap_before = "myspacevim#before"
    bootstrap_after  = "myspacevim#after"
```

这两种启动函数的区别在于，`bootstrap_before`函数是在载入用户配置时候执行的， 而`bootstrap_after`函数是在触发`VimEnter`事件时执行的。

启动函数文件应放置在 Vim &runtimepath 的 autoload 文件夹内。例如：

文件名：`~/.SpaceVim.d/autoload/myspacevim.vim`

```vim
function! myspacevim#before() abort
    let g:neomake_c_enabled_makers = ['clang']
    nnoremap jk <esc>
endfunction

function! myspacevim#after() abort
    iunmap jk
endfunction
```

在启动函数中，可以使用`:lua` 命令对 SpaceVim 进行配置，比如：

```vim
function! myspacevim#before() abort
    lua << EOF
    local opt = requires('spacevim.opt')
    opt.enable_projects_cache = false
    opt.enable_statusline_mode = true
EOF
endfunction
```

函数 `bootstrap_before` 将在读取用户配置后执行，而函数 `bootstrap_after` 将在 VimEnter autocmd 之后执行。

如果你需要添加自定义以 `SPC` 为前缀的快捷键，你需要使用 bootstrap function， 在其中加入以下代码（注意你定义的按键必须是 SpaceVim 没有使用的）：

```vim
function! myspacevim#before() abort
    call SpaceVim#custom#SPCGroupName(['G'], '+TestGroup')
    call SpaceVim#custom#SPC('nore', ['G', 't'], 'echom 1', 'echomessage 1', 1)
endfunction
```

同样地，如果你需要定义语言相关的功能，可以使用以下函数定义：

```vim
function! myspacevim#before() abort
    call SpaceVim#custom#LangSPCGroupName('python', ['G'], '+TestGroup')
    call SpaceVim#custom#LangSPC('python', 'nore', ['G', 't'], 'echom 1', 'echomessage 1', 1)
endfunction
```

这些按键绑定以语言相关的前缀键开头，默认的前缀键是 `,` 。 同样，你为特定语言定义的按键必须是 SpaceVim 没有使用的。
