---
title: "Git 的使用"
date: 2019-08-29T20:03:23+08:00
categories: ["Development"]
tags: ["Command-line Tool"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/git-banner.1ubrnpzvtoio.webp"
---

## 简介

> 一个开源的分布式版本控制系统，可以有效、高速的处理从很小到非常大的项目版本管理。Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。

{{< card "https://www.liaoxuefeng.com/wiki/896043488029600" >}}

### Git 的三种对象

- commit 对象
  - 用于表示一个提交
  - commit 对象之间会组织成一棵树的结构
  - 每一次提交都会产生一个 commit 对象
  - 除了第一次提交产生的 commit 对象，其它的 commit 对象都会有父亲 commit 对象
  - 如果只是提交操作，则父亲节点只有 1 个
  - 如果是 merge 操作，则父亲节点会有 2 个
  - commit 对象包含的信息有
    ```
    parent，父亲提交对象
    tree, 根目录树对象
    author，作者
    committer，提交者
    ```
- tree 对象
  - 用于表示一个目录
- blob 对象
  - 用于表示一个文件
- tree 和 blob 对象可以看成是 git 内部采用的文件系统对象
- 这些对象都保存在.git/objects/目录下，每一个对象都会生成 1 个 40 位的哈希值，前 2 位作为文件夹，后 38 位作为文件名
- 不同名，相同内容的文件，其哈希值相同，其 blob 对象也是共用的

### Git 中的工作区、暂存区、版本库

{{< card "https://segmentfault.com/a/1190000017053187" >}}

![Git-中的工作区、暂存区、版本库](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/Git-中的工作区、暂存区、版本库.zefosvz18dc.webp "Git 中的工作区、暂存区、版本库")

Git 命令图解

- 工作区：用来编辑保存项目文件的地方，也是用户能直接操作到的地方。
- 暂存区：保存了下次将提交的文件列表信息，一般在 Git 仓库目录中，是一个叫 index 的文件，通常多数说法还是叫暂存区域。
- 版本库：也叫本地版本库，之所以说 git 快，是因为它是分布式版本控制系统，大部分提交都是对本地仓库而言的，不依赖网络，最后一次会推送的到远程仓库。

总结 git 基本的工作流程如下：

1. 在工作目录中修改(此处修改包含了创建和删除)文件；
2. 暂存文件，将文件 add 放入暂存区域；
3. 提交更新，找到暂存区域的文件，将暂存区的文件 commit 到版本库；
4. 如果工作区的文件改乱了（包括了误删、误改），想回到上一版本，就可以使用 git checkout 命令将版本库中的文件检出到工作区将本次更改 discard(覆盖)掉。

### Git 和 SVN 有什么区别？

| GIT          | SVN          |
| ------------ | ------------ |
| 分布式       | 集中式       |
| 可以离线提交 | 只能在线提交 |

### 什么是 Git 中的“裸存储库”？

Git 中的 “裸” 存储库只包含版本控制信息而没有工作文件（没有工作树）。也就是只有 .git 文件夹。

### git pull 和 git fetch 有什么区别？

git pull = git fetch + git merge

### 如果想要在提交之前运行代码性检查工具，并在测试失败时阻止提交，该怎样配置 Git 存储库？

可以通过与存储库的 pre-commit hook 相关的简单脚本来完成。git 会在提交之前触发 pre-commit hook。你可以在脚本里对代码进行检查，如果脚本以非 0 退出，将会阻止提交操作。

### Git 有什么分支策略？

- 功能分支（Feature branching）
  要素分支模型将特定要素的所有更改保留在分支内。当通过自动化测试对功能进行全面测试和验证时，该分支将合并到主服务器中。
- 任务分支（Task branching）
  在此模型中，每个任务都在其自己的分支上实现，任务键包含在分支名称中。很容易看出哪个代码实现了哪个任务，只需在分支名称中查找任务键。
- 发布分支（Release branching）
  一旦开发分支获得了足够的发布功能，你就可以克隆该分支来形成发布分支。创建该分支将会启动下一个发布周期，所以在此之后不能再添加任何新功能，只有错误修复，文档生成和其他面向发布的任务应该包含在此分支中。一旦准备好发布，该版本将合并到主服务器并标记版本号。此外，它还应该再将自发布以来已经取得的进展合并回开发分支。

## 配置

### 初始化配置

```bash
# 最小配置信息
git config --global user.name 'your_name'
git config --global user.email 'your_email'

# config的三个作用域
# 当前仓库有效
git config --local
# 当前用户所有仓库有效
git config --global
# 当前系统所有用户的所有仓库有效
git config --system

# 显示config配置
git config --list [作用域]# 最小配置信息git config --global user.name 'your_name'git config --global user.email 'your_email'# config的三个作用域# 当前仓库有效git config --local# 当前用户所有仓库有效git config --global# 当前系统所有用户的所有仓库有效git config --system# 显示config配置git config --list [作用域]
```

### 修改 HTTP 传输请求数据时最大的缓存字节数

```bash
git config --global http.postBuffer 524288000
```

### 远程 HTTPS 验证时记住密码

```bash
git config --global credential.helper store
```

### 配置全局 git 编码

```bash
# 解决中文乱码情况
git config --global gui.encoding utf-8
```

### 使用代理提高 git 速度

```bash
git config --global http.proxy http://127.0.0.1:1080
git config --global https.proxy http://127.0.0.1:1080
```

## 应用场景

### 本地仓库管理

```bash
# 已有项目加入Git管理
cd <项目目录>
git init

# 新增项目并使用Git管理
git init <your_project>

# 检查修改内容
git status

# 将文件加入Git版本控制(工作目录 -> 暂存区)
git add [文件名] [-u : 管理全部修改]

# 提交暂存区更新内容(暂存区 -> 版本库)
git commit -m '提交原因'
```

### 远程仓库管理

```bash
# 密钥位置 C:\Users\ibm\.ssh\*
# 默认公钥文件名称 id_rsa.pub (需在github添加公钥)
# 没有使用过 ssh 的需要创建ssh-keygen(公私钥对)
ssh-keygen -C 'your_email'

# 将本地仓库和远程仓库关联
git remote add origin <*.git>

# 克隆远程仓库
git clone [--depth=number] <仓库地址>

# 使用本地引用更新远程引用，同时发送完成给定引用所需的对象
git push [远程主机名: 通常origin] [-u : 指定默认主机(以后origin可省)]

# 将远程存储库中的更改合并到当前分支中
git pull [远程主机名] [远程分支名]

# 建立追踪关系(如果当前分支与远程分支存在追踪关系，git pull就可以省略远程分支名)
# 如果当前分支只有一个追踪分支，连远程主机名都可以省略。
git branch --set-upstream [本地分支名] origin/[远程分支名]
```

### 分支管理

```bash
# 拉去远程分支信息
git fetch

# 创建分支
git branch <branchName>

# 创建并切换分支
git switch -c <branchName>

# 使用远程分支创建本地对应分支
git switch -c <branchName> origin/<originBranchName>

# 切换分支
git switch <branchName>

# 查看分支
git branch [-a: 查看远程]

# 合并指定分支到当前分支
git merge <branchName>

# 删除分支
git branch -d <branchName>

# 删除远程分支
git push origin --delete <branchName>

# 同步远程删除的分支
git remote prune origin
```

### 查看 commit 历史

```bash
git log [--oneline : 单行简洁] [--all : 查看所有分支] [-n<number> : 查看最近number次提交] [--graph : 分支演化]

# 查看参考日志
git reflog

# 打开可视化 git log 查看器
gitk

# 常用git log 命令 设置别名
# 查看自己的提交(简洁描述)
git config --global alias.lm  "log --no-merges --color --date=format:'%Y-%m-%d %H:%M:%S' --author='your_name' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"

# 查看自己的提交(展示修改的文件概览)
git config --global alias.lms  "log --no-merges --color --stat --date=format:'%Y-%m-%d %H:%M:%S' --author='your_name' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"

# 查看提交(简洁描述)
git config --global alias.ls "log --no-merges --color --graph --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"

# 查看提交(展示修改的文件概览)

git config --global alias.lss "log --no-merges --color --stat --graph --date=format:'%Y-%m-%d %H:%M:%S' --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Cblue %s %Cgreen(%cd) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

### 比较文件差异

```bash
# 工作区和暂存区
git diff [filename : 指定文件]

# 暂存区和 GIT 仓库
git diff --cached [commit : 指定GIT仓库的提交版本] [filename : 指定文件]

# 工作目录和 GIT 仓库
git diff [commit : 指定GIT仓库的提交版本] [filename : 指定文件]

# Commit 和 Commit
git diff <commit_id> <commit_id>

# 以上命令可以不指定 <filename>，则对全部文件操作。commit 可以设置为HEAD指针。
```

### 退回已提交未推送的 commit

```bash
# 记下当前 commit 的 id
# HEAD 指向上一次提交
git reset --hard HEAD~1
# 将相应的 commit 的内容覆盖回暂存区
git checkout <commit> -- .
```

### 从暂存区退回工作区修改

```bash
git restore --staged <files>
# or
git reset HEAD
```

### 丢弃工作区修改

```bash
git restore <files>
# or
git checkout -- .
```

### 丢弃工作区和暂存区的修改

```bash
git checkout HEAD -- .
# or
git reset --hard HEAD
```

### 丢弃未提交的 commit

```bash
# 找到要将 HEAD 指针移动到的 commit 的 Id
git reset --hard <commit_id>
# 将头指针指向上一次的 commit，并覆盖工作区和暂存区
git reset --hard HEAD~1
```

### 丢弃已提交的 commit

```bash
git revert -n <commit>
git commit -m <message>
```

### 恢复误操作丢弃的 commit

```bash
# 查看参考日志找到丢弃的 commit 的 id
git reflog
# 将头指针指向对应 commit
git reset --hard <commit_id>
```

### 暂存工作区修改去干其它重要的事情

```bash
# 该命令保存本地修改，并恢复工作目录以匹配HEAD提交
git stash

# 查看已有存储
git stash list

# 查看存储stash的文件变化
git stash show

# 取回存储
git stash pop [stash_name]
```

### 忽略已被 git 管理的文件

```bash
# 从git管理中删除指定文件
git rm --cached <文件>
# 更新 .gitignore 后提交
```

### 忽略不想要提交的本地修改

```bash
git update-index --skip-worktree /path/to/file
```

{{< card "https://mengqi92.github.io/2020/07/17/hide-files-from-git/" >}}

### 查看 git 对象

```bash
git对象查看
git cat-file [-t : 查看类型] [-p : 查看内容] <git对象hash>
```

### Git 合并多个commit，保持历史简洁

```bash
git rebase -i  [startpoint]  [endpoint]
# 合并前三条
git rebase -i HEAD~3
```

{{< card "https://juejin.cn/post/6844903600976576519" >}}

### 修改 Commit 作者信息

```bash
git commit --amend --author="your_name <your_email>"
```

### 修改 Commit 提交时间

```bash
# 日期年月日和时分秒中间的T是固定字符
GIT_COMMITTER_DATE="yyyy-MM-ddTHH:mm:ss" git commit --amend --date="yyyy-MM-ddTHH:mm:ss"
```

## 扩展

### 多人协作工作流程

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

- 查看远程库信息，使用 `git remote -v`；
- 本地新建的分支如果不推送到远程，对其他人就是不可见的；
- 在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-name`，本地和远程分支的名称最好一致；
- 如果 git pull 提示 no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`；

### 同时使用 Github 和 GitLab 如何管理多个 SSH Key ?

当有多个 git 账号的时候，比如一个 github，用于自己进行一些开发活动，再来一个 gitlab，一般是公司内部的 git。如果两者邮箱不同的话，就需要生成两个不同的 SSH Key，并在连接不同的 host 的时候自动区分需要使用的 Key。

1. `ssh-keygen -C 'your_email'` 生成 SSH Key 时，对文件进行命名。

   ![同时使用-Github-和-GitLab-如何管理多个-SSH-Key-1](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/同时使用-Github-和-GitLab-如何管理多个-SSH-Key-1.4glzuamwuse.webp)

2. 运行私钥管理器 `ssh-agent bash`
3. 将生成的私钥添加到管理器 `ssh-add ~/.ssh/your_id_rsa`
4. 在 Github 或 GitLab 的 SSH Key 设置里添加公钥文件文本内容。公钥文件位置为 `~/.ssh/your_id_rsa.pub`
5. 创建配置文件 `touch ~/.ssh/config`

   ```bash
   # 默认 GitHub
   Host github.com
   HostName github.com
   PreferredAuthentications publickey
   IdentityFile ~/.ssh/id_rsa
   user YourName

   # 公司 GitLab
   Host creating
   HostName your gitlab host
   PreferredAuthentications publickey
   IdentityFile ~/.ssh/your_id_rsa
   user YourName

   #Host                          #配置别名
   #HostName                      #这个是真实的域名地址
   #IdentityFile                  #这里是id_rsa的地址
   #PreferredAuthentications
   #配置登录时用什么权限认证--可设置publickey,password publickey,keyboard-interactive等
   #User                          #配置使用用户名
   ```

6. 测试 `ssh -T git@Host`

   ![同时使用-Github-和-GitLab-如何管理多个-SSH-Key-2](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/同时使用-Github-和-GitLab-如何管理多个-SSH-Key-2.7fj9tiay2280.webp)

### 如何在 GitHub 上搜索感兴趣的项目

{{< card "https://docs.github.com/en/search-github/searching-on-github/searching-for-repositories" >}}
