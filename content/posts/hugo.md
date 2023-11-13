---
title: "如何使用 Hugo 进行个人博客搭建？"
date: 2019-07-08T21:19:27+08:00
categories: ["Geek"]
tags: ["Command-line Tool"]
series: ["生命不息 折腾不止"]
featuredImage: "https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/Development/hugo-banner.mlfdu0pbh9c.webp"
---

## 简介

> Hugo 是一个用 Go 编写的快速、现代的静态网站生成器，旨在让网站创建再次变得有趣。

> Hugo 是一个通用的网站框架。从技术上讲，Hugo 是一个静态站点生成器。与根据每个访问者请求动态构建页面的系统不同，Hugo 在您创建或更新内容时构建页面。由于网站的查看频率远高于编辑频率，因此 Hugo 旨在为您网站的最终用户提供最佳的查看体验，并为网站作者提供理想的写作体验。

{{< card "https://gohugo.io/getting-started/" >}}

## 安装

{{< card "https://gohugo.io/getting-started/quick-start/" >}}

```bash
# windows 下使用 scoop 安装
scoop install hugo
# macOS 下使用 brew 安装
brew install hugo
```

安装完就来验证一下吧

```bash
# 创建site
hugo new site quickstart
# 进入site目录
cd quickstart
# 初始化
git init
# 选择一个主题
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
# 配置文件设置主题
echo theme = \"ananke\" >> config.toml
# 创建文章并修改内容
hugo new posts/my-first-post.md
# 运行本地服务查看效果
hugo server -D
```

## 主题选择

挑选一个好看的主题吧

{{< card "https://themes.gohugo.io/" >}}

## 扩展

### Vercel 配置

[Vercel](https://vercel.com/) 可以依托 `Git`仓库 ，在线自动构建和发布`Web`静态项目，支持自定义域名，可以自动签发`SSL`证书，开启`HTTPS`，还有一个特点，拥有全球`CDN`，国内速度不错。支持多套框架和模版，如：Hugo、Jekyll、Hexo、Next、Vue…

点击 [Deploy](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FHumble-Xiang%2FDoIt-vercel-hugo-template&env=HUGO_VERSION&envDescription=HUGO_VERSION%20%E9%9C%80%E8%A6%81%E8%AE%BE%E7%BD%AE%E4%B8%BA%200.92.1) 部署同款。

{{< card "https://github.com/Humble-Xiang/DoIt-vercel-hugo-template" >}}
{{< card "https://segmentfault.com/a/1190000040063325" >}}

### ~~GitHub Page 配置~~

建议使用更简单的 Hugo + Vercel 的方式来完成 CI。

```bash
# hugo命令会将site内容生成静态文件放在public目录下, 注意所有 draft: true 的文章不会被build
hugo
# 切换目录
cd .\public\
# 初始化git项目
git init
git add .
git commit -m 'first commit'
# 关联一个远程仓库，想要使用GitHub Page，项目的名称必须为 "<你的昵称>.github.io"
git remote add origin <你的项目地址>
git push -u origin master
# 如果你有自己的域名的话，可以将GitHub Page映射到自己的域名
```

{{< card "https://pages.github.com/" >}}
{{< card title="创建Github Page并设置自定义域名" url="https://www.jianshu.com/p/8ac6c7c037c5" >}}

### ~~Wercker 配置~~

#### ~~Wercker 简介~~

~~CI 使用的 [Wercker](https://app.wercker.com/), 简单直接使用 GitHub 账号注册登录，不需要麻烦的过程。CI 的简单理解就是向一个仓库提交代码后会自动执行的脚本。~~
建议使用更简单的 Hugo + [Vercel](https://vercel.com/docs) 的方式来完成 CI。

#### ~~Hugo + Wercker~~

- 首先要在 github 上新建两个仓库，一个用来存放 site 项目，一个用来存放静态的 public 项目(如使用 GitHub Page 项目名称必须为 username.github.io)。
- 在 [Wercker](https://app.wercker.com/)下创建 Application, 请参考[教程](https://gohugo.io/hosting-and-deployment/deployment-with-wercker/), 注意需要关联的仓库为 site, 会读取仓库下的 wercker.yml 文件执行脚本。
- 去 GitHub 上创建一个 token 给 Wercker 操作 GitHub 仓库用，请参考[教程](https://help.github.com/en/articles/creating-a-personal-access-token-for-the-command-line), 就是 wercker 脚本里的环境变量, 也要在后台添加下。
- 因为在 Site 项目里存在子项目，如果使用 submodule 了请参考 [Git submodule 子模块的管理和使用](https://www.jianshu.com/p/9000cd49822c), 不使用要修改下 wercker.yml 文件，如果报已存在的错误，就先把文件加删除再根据 git 给出的错误提示`git rm --cached <moduleName>`, 然后再操作。
- 在你的 site 仓库根目录下创建 wercker.yml 文件，参考下面。
- 最后进行 push, 去你的 Wercker 后台看看吧，Enjoy!

#### wercker.yml

```yaml
# This references a standard debian container from the
# Docker Hub https://registry.hub.docker.com/_/debian/
# Read more about containers on our dev center
# http://devcenter.wercker.com/docs/containers/index.html
box: debian
# You can also use services such as databases. Read more on our dev center:
# http://devcenter.wercker.com/docs/services/index.html
# services:
# - postgres
# http://devcenter.wercker.com/docs/services/postgresql.html

# - mongo
# http://devcenter.wercker.com/docs/services/mongodb.html

# This is the build pipeline. Pipelines are the core of wercker
# Read more about pipelines on our dev center
# http://devcenter.wercker.com/docs/pipelines/index.html
build:
  # Steps make up the actions in your pipeline
  # Read more about steps on our dev center:
  # http://devcenter.wercker.com/docs/steps/index.html
  steps:
    - script:
        name: install git
        code: |
          apt-get update
          apt-get install git -y
    - script:
        # 如果使用submodules, 记得添加配置文件.gitmodules
        name: initialize and update git submodules
        code: |
          git submodule init
          git submodule update --remote --recursive
    - arjen/hugo-build:
        theme: LoveIt
        flags: --buildDrafts=true
    - npm-install
    - script:
        name: publish algolia json
        code: |
          npm run algolia
deploy:
  steps:
    - install-packages:
        packages: git ssh-client
    # 官方给的lukevivier/gh-pages@0.2.1会部署到gh-pages分支，17年我用的时候没这毛病，这里改用别的Step
    # 部署public目录下的静态文件至username.github.io的master分支
    - sf-zhou/gh-pages@0.2.6:
        token: $GIT_TOKEN
        domain: http://blog.orionpax.top
        repo: OrionPax19970905/OrionPax19970905.github.io
        branch: master
        basedir: public
```

## 同款 Blog 搭建保姆级全流程

1. (可选，已有 GitHub 账号的跳过这一步) 注册并登录 GitHub

{{< card "https://www.msy.plus/2021/10/04/github-singup/" >}}

2. 点击 [clone](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FHumble-Xiang%2FDoIt-vercel-hugo-template&env=HUGO_VERSION&envDescription=HUGO_VERSION%20%E9%9C%80%E8%A6%81%E8%AE%BE%E7%BD%AE%E4%B8%BA%200.92.1) 通过 [Vercel 模版](https://github.com/Humble-Xiang/DoIt-vercel-hugo-template) 构建项目，输入项目名称创建项目，填写环境变量并点击 Deploy，耐心等待一段时间，Congratulations! 点击 Go to Dashboard - Visit 你已经看到你的博客网站了。使用 Vercel 创建的项目是已经配置了 CI 的，当你向 GitHub 的仓库提交代码时，Vercel 会自动重新打包并发布项目，因此你做的所有提交都会使网站重新构建。

![Create Git Repository](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/geek/image.2km7cyjvqhg0.webp "Create Git Repository")
![Configure Project](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.6zgp55b2u0g0.webp "Configure Project")

3. Vercel 自动生成的域名可能不是你想要的，`Vercel -> Project -> Settings -> Domains` 中可以进行修改，没有自己域名的话可以使用 Vercel 提供的二级域名并修改前缀。有自己的域名可以直接添加已有的域名，然后到域名商管理系统配置域名记录，等待生效，生效后会自动签发 SSL 证书，开启 HTTPS。

4. 然后我们根据需要修改下博客的配置文件 `config.toml`。以下是正常情况下需要个性化修改的初始化配置：

```yaml
# 博客主页地址
baseURL = ""
# ......
# 网站标题
title = "网站标题"
# ......
[languages]
  [languages.zh-cn]
    [languages.zh-cn.menu]
      [[languages.zh-cn.menu.main]]
        identifier = "github"
        pre = "<i class='fab fa-github fa-fw'></i>"
        post = ""
        name = ""
        # GitHub主页地址
        url = ""
    # ......
    [languages.zh-cn.params]
      # 网站描述
      description = "网站描述"
      # 网站关键词
      keywords = ["Theme", "Hugo"]
      #......
      [languages.zh-cn.params.home]
        [languages.zh-cn.params.home.profile]
          # 主页显示头像的 URL
          avatarURL = "/images/avatar.webp"
          # 主页显示的网站标题 (支持 HTML 格式)
          title = "主页标题"
          # 主页显示的网站副标题
          subtitle = "主页副标题"
      # 主页的社交信息设置
      [languages.zh-cn.params.social]
      # 社交配置根据需要配置就不一一列出来了
      # ......
[params]
  # 网站标题
  title = "网站标题"
  # ......
  [params.header]
    [params.header.title]
      # 标题名称
      name = "头部标题"
    # ......
    [params.page.share]
      [params.page.share.ogimage]
        # og-image 服务地址
        serverURL = "https://og-image-demo.dramacat.top/"
        # 文章分享时的默认图片，文章存在 featuredImage 时优先使用 featuredImage
        defaultImage = "https://assets.vercel.com/image/upload/front/assets/design/vercel-triangle-black.svg"
      # ......
      # Waline 评论系统设置 (https://waline.js.org)
      [params.page.comment.waline]
        enable = false
        serverURL = ""
    # ......
    [params.page.library]
      # 卡片引用配置
      [params.page.library.js]
        # 额外引入第三方 JS 地址
        websiteCardEmbedJavaScript = "https://website-card-embed-demo.dramacat.top/website-card-embed-loveit.js"
      # see https://github.com/Humble-Xiang/website-card-embed
      [params.page.library.card]
        # website-card-embed 服务地址
        serverURL = 'https://website-card-embed-demo.dramacat.top/'
# ......
# 作者配置
[author]
  name = ""
  email = ""
  link = ""
  avatar = "/images/avatar.webp"
  gravatarEmail = ""
```

5. (可选，如果你需要卡片引入) [Deploy](https://vercel.com/import/project?template=https://github.com/Humble-Xiang/website-card-embed) 你自己的 Website Card Embed 服务端，并修改配置文件中的 `params.page.libaray.card.serverURL` 和 `websiteCardEmbedJavaScript` 为你自己的服务地址。

{{< card "https://blog.dramacat.top/website-card-embed" >}}

6. (可选，如果你需要带文章标题的分享图) [Deploy](https://vercel.com/import/project?template=https://github.com/Humble-Xiang/og-image) 你自己的 og-image 服务端，并修改 `params.page.share.ogimage` 中的配置。

{{< card "https://github.com/Humble-Xiang/og-image" >}}

7. (可选，如果你需要评论系统) 部署你自己的 Waline 服务端，并修改 `params.page.comment.waline` 中的配置。

{{< card "https://waline.js.org/guide/get-started.html" >}}

8. 开写！
