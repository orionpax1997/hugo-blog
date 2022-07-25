---
title: "Homebrew 的使用"
date: 2021-09-03T08:34:50+08:00
categories: ["Geek"]
tags: ["Command-line Tool"]
series: ["生命不息 折腾不止"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/homebrew-banner.2ht2xznez020.webp"
---

## 简介

> Homebrew 由开发者 Max Howell 开发，并基于 BSD 开源，是一个非常方便的包管理器工具。在早期， Homebrew 仅有 macOS 的版本，后续随着用户的增多，Homebrew 还提供了 Linux 的版本，帮助开发者在 Linux 同样使用 Homebrew 来配置环境。

{{< card "https://github.com/beeftornado/homebrew-rmtree" >}}

**Homebrew 的几个核心概念**

| 词汇        | 含义                                                                                           |
| ----------- | ---------------------------------------------------------------------------------------------- |
| formula (e) | 安装包的描述文件，formulae 为复数                                                              |
| cellar      | 安装好后所在的目录                                                                             |
| keg         | 具体某个包所在的目录，keg 是 cellar 的子目录                                                   |
| bottle      | 预先编译好的包，不需要现场下载编译源码，速度会快很多；官方库中的包大多都是通过 bottle 方式安装 |
| tap         | 下载源，可以类比于 Linux 下的包管理器 repository                                               |
| cask        | 安装 macOS native 应用的扩展，你也可以理解为有图形化界面的应用。                               |
| bundle      | 描述 Homebrew 依赖的扩展                                                                       |

## 安装

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 使用

### 基础

```bash
# 搜索包
brew search [包名]
# 安装包
brew install [包名]
# 查看已经安装的包
brew list
```

### 更新

```bash
# 查看所有具有更新版本的包 [贪婪模式]
brew outdated [--greedy]
# 更新所有的包 [贪婪模式]
brew upgrade [--greedy]
# 更新指定的包
brew upgrade [包名]
# 锁定某个包
brew pin [包名]
# 取消锁定包
brew unpin [包名]
# 命令来清理系统中所有软件的历史版本
brew cleanup
```

### 卸载

```bash
# 卸载软件
brew uninstall [软件名]
# 安装 rmtree tap
brew tap beeftornado/rmtree
# 卸载 [包名]，卸载 Formula 使用 rmtree，同时卸载无用依赖包
brew rmtree [包名]
# 命令来清理系统中所有软件的历史版本
brew cleanup
```

### tap 管理

```bash
# 查看已添加的 tap
brew tap
# 添加 tap
brew tap [user/repo]
# 删除 tap
brew untap [user/repo]
```

### 其他

```bash
# 查询叶子节点包
brew leaves
# 查看已安装的包的依赖，树形显示
brew deps --installed --tree
# 自我检查
brew doctor
```
