# Windows 下的终端解决方案


## 前言

本文已过时。现在个人的解决方案为 Windows Terminal + [fishshell](https://fishshell.com/) + [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish)， 从 zsh 转到 fish 的原因就是因为 zsh 太慢了。

~~WIN10 命令行工具最终选择了 WSL + Ubuntu + Terinus + Oh My Zsh。在 Hyper 和 Terminus 之前选择了 Terminus，只是因为 Terminus 模糊透明真的好看，一位伟人曾经说过好看就是第一生产力。~~

## 搭建

1. 启用 WSL ，管理员运行 PowerShell ，执行 `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`
2. 去 Microsoft Store 搜索 WSL 下载一个，推荐选择 Ubuntu
3. 初始化 Ubuntu 系统
4. 使用 Scoop 安装 Terminus `scoop install terminus`
5. 修改 Terminus 配置，Shell -> Profile 选择 WSL / Ubuntu 。样式上就按自己的需求改
6. 安装 zsh ，`sudo apt udpate && sudo apt install -y zsh`
7. 安装 Oh My Zsh ，`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
8. 设置 zsh 为默认 shell ，`chsh -s $(which zsh)`
9. 修改 zsh 的[主题](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)并添加需要的插件

## WSL 的 PATH 会包含 WIN10 的 PATH 问题

```bash
// 两个系统里存在的同名的命令就会有问题
sudo vim ~/.bashrc
// 追加
PATH=$(/usr/bin/printenv PATH | /usr/bin/perl -ne 'print join(":", grep { !/\/mnt\/[a-z]/ } split(/:/));')
```

## 参考

{{< card "https://p3terx.com/archives/the-strongest-terminal-solution-under-windows-10.html#E5AE89E8A385WSL" >}}
{{< card "https://medium.com/@ssharizal/hyper-js-oh-my-zsh-as-ubuntu-on-windows-wsl-terminal-8bf577cdbd97" >}}

