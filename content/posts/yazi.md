---
title: "命令行下的文件管理器 Yazi"
date: 2025-02-24T16:39:20+08:00
tags: ["Command-line Tool"]
series: ["生命不息 折腾不止"]
---

## 简介

Yazi 是一个基于异步 I/O 编写的Rust的快速快速终端文件管理器。

{{< card "https://yazi-rs.github.io/" >}}

## 安装

windows 使用 `scoop` 命令安装。zoxide 最好配置一下，一个智能的用于替换 `cd` 的命令行工具。

```bash
scoop install yazi
# Install the optional dependencies (recommended):
scoop install ffmpeg 7zip jq poppler fd ripgrep fzf zoxide imagemagick
```

{{< card "https://yazi-rs.github.io/docs/installation" >}}

## 快速入门

{{< card "https://yazi-rs.github.io/docs/quick-start" >}}
