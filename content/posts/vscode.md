---
title: "Visual Studio Code 的使用"
date: 2021-09-24T17:20:00+08:00
categories: ["Development"]
tags: ["Tool"]
featuredImage: "https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/vscode-banner.n67beq6fr8w.webp"
---

## 简介

Visual Studio Code（简称 VS Code）是一款由微软开发且跨平台的免费源代码编辑器。该软件支持语法高亮、代码自动补全（又称 IntelliSense）、代码重构、查看定义功能，并且内置了命令行工具和 Git 版本控制系统。用户可以更改主题和键盘快捷方式实现个性化设置，也可以通过内置的扩展程序商店安装扩展以拓展软件功能。

## 安装

mac 下执行 `brew install visual-studio-code`。

## 配置

```json
{
  // VSCode settings
  // Text Editor
  "editor.fontFamily": "'FiraCode Nerd Font', Menlo, Monaco, 'Courier New', monospace", // 字体
  "editor.fontLigatures": true, // 字体连字符
  // "editor.fontSize": 14, // 设置字体大小， 默认 14
  "editor.wordWrap": "bounded", // 设置 超过word Wrap Column设置的字符数、达到视口最小宽度，时自动换行
  "editor.wordWrapColumn": 160, // editor.wordWrap 配置为wordWrapColumn或者bounded时起作用
  "editor.tabSize": 2, // 一个制表符等于的空格数。在 `#editor.detectIndentation#` 启用时，根据文件内容，该设置可能会被覆盖。
  "editor.insertSpaces": true, // 设置输入tab键时是否自动转为插入空格（默认ture，即自动转空格）,当editor.detectIndentation配置为 true 时，该配置项将被自动覆盖
  "editor.detectIndentation": true, // 设置是否自动检测对齐，控制打开文件时是否基于文件内容，自动检测editor.tabSize 和editor.insertSpaces
  "editor.inlineSuggest.enabled": true, // 设置是否启用内联提示
  // 开启自动显示建议
  "editor.quickSuggestions": {
    "other": true,
    "comments": true,
    "strings": true
  },

  // Text Editor -> Formatting
  "editor.formatOnPaste": true, // 设置黏贴内容时是否自动格式化，true表示自动格式化，需要配置格式化器(formatter)才可使用
  "editor.formatOnSave": true, // 设置保存文件时是否自动格式化，true表示自动格式化,需要配置格式化器(formatter)才可使用
  "editor.formatOnSaveMode": "file", // 设置保存文件时格式化整个文件还是仅被修改处。该配置项仅在 "editor.formatOnPaste" 为 true时生效
  "editor.formatOnType": true, // 设置输入完成后是否自动格式化当前行

  // Text Editor -> Minimap
  "editor.minimap.maxColumn": 120, // 设置minimap的宽度以设置可渲染的最大列数，默认120
  "editor.minimap.renderCharacters": false, // 设置 minimap 渲染成小色块，而不是字符

  // Files
  // "files.autoSave": "afterDelay", //设置延迟一定的时间后自动保存文件
  // "files.autoSaveDelay": 5000, // 设置自动保存文件前需要延迟的时间，单位毫秒 默认1000
  // "files.enableTrash": true, // 设置删除文件、目录时是否允许删除到操作系统回收站，默认为true，即允许
  // "files.encoding": "utf8", // 设置读写文件时所用编码 默认UTF-8，可针对每种语言进行设置
  // "files.autoGuessEncoding": false, // 设置打开文件时，是否自动猜测字符编码，默认false，即不自动猜测，可针对每种语言进行设置

  // 设置各种代码的默认格式化器
  "[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[css]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[vue]": {
    "editor.defaultFormatter": "octref.vetur"
  },

  // 插件配置
  // Eslint插件配置
  "eslint.enable": true, // 启用/禁用 vscode-eslint。默认情况下是启用的
  "eslint.alwaysShowStatus": true, // 设置状态栏是否一直显示ESlint图标项，true表示一直显示
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true // 设置保存时是否自动修复代码
  },
  "eslint.format.enable": false, // 设置是否把ESlint作为一个格式化器，true表示启用

  // Prettier插件配置
  "prettier.useEditorConfig": false, // 设置不使用 .editorconfig 文件
  "prettier.enable": true, // 设置是否开启prettier插件，默认为true，即开启
  // "prettier.semi": false, // 设置是否在每行末尾添加分号，默认为 true
  // "prettier.singleQuote": true, // 设置格式化时，保持单引号，如果设置为true，则单引号会自动变成双引号
  // "prettier.tabWidth": 2, // 设置每个tab占用多少个空格
  // "prettier.printWidth": 120, // 设置每行可容纳字符数
  // "prettier.useTabs": false, // 设置是否使用tab键缩进行，默认为false，即不使用
  // "prettier.bracketSpacing": true, // 在对象，括号与文字之间加空格 true - Example: { foo: bar }   false - Example: {foo: bar}， 默认为true
  // "prettier.arrowParens": "avoid", //  (x) => {} 箭头函数参数只有一个时是否要有小括号。avoid：省略括号
  // "prettier.trailingComma": "none", // 在对象或数组最后一个元素后面是否加逗号

  // Vetur插件配置
  "vetur.format.enable": true, // 设置css代码(<style>包含的代码块）默认格式化器
  "vetur.format.defaultFormatter.sass": "sass-formatter",
  "vetur.format.defaultFormatter.postcss": "prettier",
  "vetur.format.defaultFormatter.scss": "prettier",
  "vetur.format.defaultFormatter.less": "prettier",
  "vetur.format.defaultFormatter.stylus": "stylus-supremacy",
  "vetur.format.defaultFormatter.html": "prettier", // 设置html代码(<template>包含的代码块)默认格式化器
  "vetur.format.defaultFormatter.js": "prettier-eslint", // 设置js代码<script>包含的代码块）默认格式化器
  "vetur.format.defaultFormatter.ts": "prettier", // 设置vetur默认使用 prettier格式化代码
  "vetur.format.options.tabSize": 2, // 设置tab键占用的空格数，该配置将被所有格式化器继承
  "vetur.format.options.useTabs": false,

  // Vue-helper 插件配置
  "vue-helper.alias": {
    "@": "src"
  },
  "vue-helper.componentPrefix": {
    "alias": "@",
    "path": "src"
  },

  // Copilot 插件配置
  "github.copilot.enable": {
    "*": true,
    "yaml": false,
    "plaintext": true,
    "markdown": false,
    "javascript": true
  },

  // 主题配置
  "workbench.colorTheme": "One Dark Pro Darker",
  "workbench.iconTheme": "vscode-great-icons",
  "oneDarkPro.vivid": true,
  "oneDarkPro.bold": true
}
```

## 插件

{{< card "https://github.com/viatsko/awesome-vscode" >}}

### Official

{{< card "https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-zh-hans" >}}

### **Migrating from other editors**

{{< card "https://marketplace.visualstudio.com/items?itemName=vscodevim.vim" >}}

### **Productivity**

{{< card "https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=giovdk21.vscode-sublime-merge" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=GitHub.copilot" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=octref.vetur" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=shenjiaolong.vue-helper" >}}

### Beautification

{{< card "https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=emmanuelbeziat.vscode-great-icons" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2" >}}
{{< card "https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight" >}}

## 应用场景

### 如何使用 ESLint+Prettier 来统一前端代码风格

#### Vue 项目整合 Vetur、ESLint、Prettier

1. 确认 VSCode 安装了 Vetur、ESLint、Prettier - Code formatter 插件。
2. 配置 Prettier。
   - 参考 .prettierrc
     ```json
     {
       "semi": true,
       "singleQuote": true,
       "tabWidth": 2,
       "printWidth": 120,
       "useTabs": false,
       "bracketSpacing": true,
       "arrowParens": "avoid",
       "trailingComma": "none",
       "htmlWhitespaceSensitivity": "ignore"
     }
     ```
3. 配置 VSCode。

   - 参考 settings.json

     ```json
     {
       // Text Editor
       "editor.wordWrap": "bounded", // 设置 超过word Wrap Column设置的字符数、达到视口最小宽度，时自动换行
       "editor.wordWrapColumn": 160, // editor.wordWrap 配置为wordWrapColumn或者bounded时起作用
       "editor.tabSize": 2, // 一个制表符等于的空格数。在 `#editor.detectIndentation#` 启用时，根据文件内容，该设置可能会被覆盖。
       "editor.insertSpaces": true, // 设置输入tab键时是否自动转为插入空格（默认ture，即自动转空格）,当editor.detectIndentation配置为 true 时，该配置项将被自动覆盖
       "editor.detectIndentation": true, // 设置是否自动检测对齐，控制打开文件时是否基于文件内容，自动检测editor.tabSize 和editor.insertSpaces
       // 开启自动显示建议
       "editor.quickSuggestions": {
         "other": true,
         "comments": true,
         "strings": true
       },
       // "editor.fontSize": 14, // 设置字体大小， 默认 14

       // Text Editor -> Formatting
       "editor.formatOnPaste": true, // 设置黏贴内容时是否自动格式化，true表示自动格式化，需要配置格式化器(formatter)才可使用
       "editor.formatOnSave": true, // 设置保存文件时是否自动格式化，true表示自动格式化,需要配置格式化器(formatter)才可使用
       "editor.formatOnSaveMode": "file", // 设置保存文件时格式化整个文件还是仅被修改处。该配置项仅在 "editor.formatOnPaste" 为 true时生效
       "editor.formatOnType": true, // 设置输入完成后是否自动格式化当前行

       // Text Editor -> Minimap
       "editor.minimap.maxColumn": 120, // 设置minimap的宽度以设置可渲染的最大列数，默认120
       "editor.minimap.renderCharacters": false, // 设置 minimap 渲染成小色块，而不是字符

       // Files
       // "files.autoSave": "afterDelay", //设置延迟一定的时间后自动保存文件
       // "files.autoSaveDelay": 5000, // 设置自动保存文件前需要延迟的时间，单位毫秒 默认1000
       // "files.enableTrash": true, // 设置删除文件、目录时是否允许删除到操作系统回收站，默认为true，即允许
       // "files.encoding": "utf8", // 设置读写文件时所用编码 默认UTF-8，可针对每种语言进行设置
       // "files.autoGuessEncoding": false, // 设置打开文件时，是否自动猜测字符编码，默认false，即不自动猜测，可针对每种语言进行设置

       // 设置各种代码的默认格式化器
       "[html]": {
         "editor.defaultFormatter": "esbenp.prettier-vscode"
       },
       "[css]": {
         "editor.defaultFormatter": "esbenp.prettier-vscode"
       },
       "[javascript]": {
         "editor.defaultFormatter": "esbenp.prettier-vscode"
       },
       "[json]": {
         "editor.defaultFormatter": "esbenp.prettier-vscode"
       },
       "[vue]": {
         "editor.defaultFormatter": "octref.vetur"
       },

       // Eslint插件配置
       "eslint.enable": true, // 启用/禁用 vscode-eslint。默认情况下是启用的
       "eslint.alwaysShowStatus": true, // 设置状态栏是否一直显示ESlint图标项，true表示一直显示
       "editor.codeActionsOnSave": {
         "source.fixAll.eslint": true // 设置保存时是否自动修复代码
       },
       "eslint.format.enable": false, // 设置是否把ESlint作为一个格式化器，true表示启用

       // Prettier插件配置
       "prettier.useEditorConfig": false, // 设置不使用 .editorconfig 文件
       "prettier.enable": true, // 设置是否开启prettier插件，默认为true，即开启
       // "prettier.semi": false, // 设置是否在每行末尾添加分号，默认为 true
       // "prettier.singleQuote": true, // 设置格式化时，保持单引号，如果设置为true，则单引号会自动变成双引号
       // "prettier.tabWidth": 2, // 设置每个tab占用多少个空格
       // "prettier.printWidth": 120, // 设置每行可容纳字符数
       // "prettier.useTabs": false, // 设置是否使用tab键缩进行，默认为false，即不使用
       // "prettier.bracketSpacing": true, // 在对象，括号与文字之间加空格 true - Example: { foo: bar }   false - Example: {foo: bar}， 默认为true
       // "prettier.arrowParens": "avoid", //  (x) => {} 箭头函数参数只有一个时是否要有小括号。avoid：省略括号
       // "prettier.trailingComma": "none", // 在对象或数组最后一个元素后面是否加逗号

       // Vetur插件配置
       "vetur.format.enable": true, // 设置css代码(<style>包含的代码块）默认格式化器
       "vetur.format.defaultFormatter.sass": "sass-formatter",
       "vetur.format.defaultFormatter.postcss": "prettier",
       "vetur.format.defaultFormatter.scss": "prettier",
       "vetur.format.defaultFormatter.less": "prettier",
       "vetur.format.defaultFormatter.stylus": "stylus-supremacy",
       "vetur.format.defaultFormatter.html": "prettier", // 设置html代码(<template>包含的代码块)默认格式化器
       "vetur.format.defaultFormatter.js": "prettier-eslint", // 设置js代码<script>包含的代码块）默认格式化器
       "vetur.format.defaultFormatter.ts": "prettier", // 设置vetur默认使用 prettier格式化代码
       "vetur.format.options.tabSize": 2, // 设置tab键占用的空格数，该配置将被所有格式化器继承
       "vetur.format.options.useTabs": false
     }
     ```

4. 未安装 eslint 的话，使用 npm 或者 yarn 安装 eslint 和需要的 eslint 插件。`npm i -D eslint eslint-plugin-vue`
5. 处理 eslint 和 prettier 的冲突规则。通过关闭 eslint 的自动修复来判断。

{{< card "https://eslint.bootcss.com/docs/rules/" >}}
{{< card "https://prettier.io/docs/en/options.html" >}}
{{< card "https://cloud.tencent.com/developer/article/1802491" >}}
{{< card "https://segmentfault.com/a/1190000015315545" >}}
{{< card "https://segmentfault.com/a/1190000016964384" >}}
{{< card "https://segmentfault.com/a/1190000009077086" >}}

### VSCode 如何支持三路合并？

- 安装 sublime merge app
- 安装 VSCode 插件 Sublime Merge for VSCode
- 合并遇到冲突后在文件中右键打开 Sublime Merge
- 点击冲突文件的 resolve，可以进入三路合并

{{< card "https://github.com/PeterChen1997/MyBlog/issues/24" >}}
