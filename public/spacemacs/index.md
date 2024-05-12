# Spacemacs 的使用


## 简介

Spacemacs 是一种体验 Emacs 的新方式——它是一个复杂而优美的设置，专注于人体工程学、记忆法和一致性。

只需克隆并启动它，然后按空格键即可探索精心挑选的键绑定的交互式列表。您还可以按主缓冲区的 [?]按钮来尝试一些很棒的第一键绑定。

Emacs 和 Vim 用户都可以自然地使用 Spacemacs——您甚至可以混合使用这两种编辑风格。能够在输入样式之间快速切换，使 Spacemacs 成为结对编程的绝佳工具。

Spacemacs 目前处于测试阶段，非常欢迎任何贡献。

{{< card "https://www.spacemacs.org" >}}

## 入门

{{< card "https://www.spacemacs.org/doc/QUICK_START.html" >}}

## 文档

{{< card "https://www.spacemacs.org/doc/DOCUMENTATION.html" >}}

## 图层

{{< card "https://github.com/syl20bnr/spacemacs/blob/develop/layers/LAYERS.org" >}}

## 我的配置

```lisp
   ;; List of configuration layers to load.
   dotspacemacs-configuration-layers
   '(
     ;; ----------------------------------------------------------------
     ;; Example of useful layers you may want to use right away.
     ;; Uncomment some layer names and press `SPC f e R' (Vim style) or
     ;; `M-m f e R' (Emacs style) to install them.
     ;; ----------------------------------------------------------------

     ;; Checkers
     syntax-checking

     ;; Completion
     (auto-completion :variables
                      ;; 按使用频率排序
                      auto-completion-enable-sort-by-usage t
                      ;; 自动完成弹出框中显示 snippets
                      auto-completion-enable-snippets-in-popup t
                      ;; 显示当前候选项文档
                      auto-completion-enable-help-tooltip t)
     helm

     ;; Emacs
     helpful
     (ibuffer :variables ibuffer-group-buffers-by 'projects)
     tabs

     ;; File trees
     (treemacs :variables
               ;; 使用 all-the-icons-theme，需要安装字体库 M-x all-the-icons-install-fonts
               treemacs-use-all-the-icons-theme t
               ;; 配置启用 git 模式
               treemacs-use-git-mode 'deferred)

     ;; Fonts
     (unicode-fonts :variables
                    ;; 启用连字符
                    unicode-fonts-enable-ligatures t
                    ;; 启用彩色表情符号
                    unicode-fonts-enable-ligatures t)

     ;; Fun
     emoji

     ;; Miscellaneous
     multiple-cursors

     ;; Programming languages
     emacs-lisp
     (html :variables
           ;; CSS 启用 LSP
           css-enable-lsp t
           ;; HTML 启用 LSP
           html-enable-lsp t
           ;; 配置格式化器使用 Prettier
           web-fmt-tool 'prettier)
     (javascript :variables
                 ;; 配置后端使用 LSP
                 javascript-backend 'lsp
                 ;; 配置格式化使用 Prettier
                 javascript-fmt-tool 'prettier
                 ;; 配置保存时自动格式化
                 javascript-fmt-on-save t)
     (markdown :variables markdown-live-preview-engine 'vmd)
     (vue :variables vue-backend 'lsp)

     ;; Source control
     (version-control :variables
                      ;; 设置差异显示在左侧
                      version-control-diff-side 'left)

     ;; Themes
     (colors :variables
             ;; 为所有标识符着色
             colors-colorize-identifiers 'all
             ;; 启用 Nyan 🐱
             colors-enable-nyan-cat-progress-bar t)

     ;; Tools
     (lsp :variables
          ;; 显示 Code lens
          lsp-lens-enable t)
     (shell :variables
            ;; 配置默认 shell 为 vterm
            shell-default-shell 'vterm
            ;; 配置默认高度
            shell-default-height 30
            ;; 配置底部显示
            shell-default-position 'bottom)
    )

   dotspacemacs-additional-packages '(keyfreq go-translate grip-mode)

(defun dotspacemacs/user-config ()
  "Configuration for user code:
This function is called at the very end of Spacemacs startup, after layer
configuration.
Put your configuration code here, except for variables that should be set
before packages are loaded."
  ;; markdown 自定义配置 FIX "Wrong type argument: consp, nil"
  (setq native-comp-deferred-compilation-deny-list '("markdown-mode\\.el$"))
  ;; keyfreq 支持按键分析
  (use-package keyfreq
    :config
    (keyfreq-mode 1)
    (keyfreq-autosave-mode 1)
  )
  ;; tabs layer 支持 ace jump
  (use-package centaur-tabs
    :config
    (spacemacs/set-leader-keys "jt" 'centaur-tabs-ace-jump)
  )
  ;; treemacs 自定义配置
  (use-package treemacs
    :config
    ;; 配置显示本地 repo 领先或落后于其远程对应项目的提交数
    (when treemacs-python-executable (treemacs-git-commit-diff-mode t))
    ;; 配置自动切换到当前缓冲区的项目
    (treemacs-project-follow-mode t)
  )
  ;; go-translate 自定义配置
  (use-package go-translate
    :config
    (setq gts-translate-list '(("en" "zh")))
    (defconst go-translator-text (gts-translator :picker gts-noprompt-picker :engines gts-google-engine :render gts-buffer-render :splitter gts-paragraph-splitter))
    (defun go-translate-command-text () (interactive) (gts-translate go-translator-text))
    (spacemacs/set-leader-keys "gt" 'go-translate-command-text)
    (add-hook 'gts-after-buffer-render-hook 'turn-off-evil-mode)
  )
)
```

## 应用场景

### 如何进行项目管理？

- `projectile-add-know-project` 添加目录作为项目管理
- `projectile-remove-know-project` 删除项目
- `SPC p !` 在项目的根目录下运行 shell 命令
- `SPC p p` 切换项目
- `SPC p f` 在当前项目中查找文件
- `SPC p r` 打开最近的文件
- `SPC p v` 查看当前项目 Git Status

### 如何使用搜索和替换？

- `SPC s s` 在当前 Buffer 中搜索
- `SPC /` 在当前项目中搜索
- 在当前 Buffer 中替换，使用 `SPC s e` 或 `SPC v` 选中范围后进入 iedit 模式，`n/N` 跳转命中，`TAB` 开关命中，编辑后`ESC ESC`
- 在当前项目中替换，搜索后 `C-c C-e` 进入编辑 Buffer，然后在 Buffer 中进行替换，完成后 `C-c C-c` 保存

### 如何进行语法错误检查？

- `SPC e` 错误相关 Function
- `SPC e l` 显示所有错误的列表
- `SPC e x` 如果检查器支持，请解释选定的错误

### 如何使用多光标编辑？

{{< card url="https://develop.spacemacs.org/layers/+misc/multiple-cursors/README.html" title="multiple-cursors layer" description="support for multiple cursors." >}}
{{< card "https://github.com/gabesoft/evil-mc" >}}

- 使用 `g r q` 退出多光标模式
- 按 `V` 然后选中多行，使用 `g r A` 或 `g r I` 在选中行的前后创建多光标

### 如何添加自定义键绑定？

```lisp
(defun dotspacemacs/user-config ()
  "Configuration function for user code.
This function is called at the very end of Spacemacs initialization after
layers configuration.
This is the place where most of your configurations should be done. Unless it is
explicitly specified that a variable should be set before a package is loaded,
you should place your code here."
  ;; 通过 define-key 方法绑定
  (define-key evil-normal-state-map (kbd "C-s") #'save-buffer)
  (define-key evil-insert-state-map (kbd "C-s") #'save-buffer)
  ;; 通过 spacemacs/set-leader-keys 方法绑定
  (spacemacs/set-leader-keys "jt" 'centaur-tabs-ace-jump)
)
```

## 扩展

{{< card "https://liuzhijun-source.github.io/spacemacs-14-days/#/" >}}
{{< card "http://smacs.github.io/elisp/" >}}

