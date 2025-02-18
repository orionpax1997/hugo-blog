---
title: "Kickstart Nvim"
date: 2025-02-13T14:04:17+08:00
categories: ["Geek"]
tags: ["Tool"]
series: ["生命不息 折腾不止"]
---

## 简介

{{< card "https://github.com/nvim-lua/kickstart.nvim" >}}

不是 Neovim 发行版，而是您的配置的起点。

- Small
- Single-file
- Completely Documented

## VIM 入门

{{< card "https://orionpax.vercel.app/neovim" >}}

## 另一个可选的 Neovim 发行版 SpaceVim

{{< card "https://orionpax.vercel.app/spacevim" >}}

## 配置说明

```lua
--[[

=====================================================================
==================== READ THIS BEFORE CONTINUING ====================
=====================================================================
========                                    .-----.          ========
========         .----------------------.   | === |          ========
========         |.-""""""""""""""""""-.|   |-----|          ========
========         ||                    ||   | === |          ========
========         ||   KICKSTART.NVIM   ||   |-----|          ========
========         ||                    ||   | === |          ========
========         ||                    ||   |-----|          ========
========         ||:Tutor              ||   |:::::|          ========
========         |'-..................-'|   |____o|          ========
========         `"")----------------(""`   ___________      ========
========        /::::::::::|  |::::::::::\  \ no mouse \     ========
========       /:::========|  |==hjkl==:::\  \ required \    ========
========      '""""""""""""'  '""""""""""""'  '""""""""""'   ========
========                                                     ========
=====================================================================
=====================================================================

What is Kickstart?
什么是 Kickstart？

  Kickstart.nvim is *not* a distribution.
  Kickstart.nvim *不是* 发行版。

  Kickstart.nvim is a starting point for your own configuration.
  Kickstart.nvim 是您自己配置的起点。
    The goal is that you can read every line of code, top-to-bottom, understand
    what your configuration is doing, and modify it to suit your needs.
    其目标是让您逐行阅读代码，理解配置的作用，并根据需要进行修改。

    Once you've done that, you can start exploring, configuring and tinkering to
    make Neovim your own! That might mean leaving Kickstart just the way it is for a while
    or immediately breaking it into modular pieces. It's up to you!
    在此基础上，您可以开始探索、配置和调整 Neovim，使其更符合您的需求。

    If you don't know anything about Lua, I recommend taking some time to read through
    a guide. One possible example which will only take 10-15 minutes:
    如果您对 Lua 语言不熟悉，建议先阅读一些入门指南，例如：
      - https://learnxinyminutes.com/docs/lua/

    After understanding a bit more about Lua, you can use `:help lua-guide` as a
    reference for how Neovim integrates Lua.
    在了解了 Lua 的基本知识后，您可以使用 :help lua-guide 作为参考，了解 Neovim 如何集成 Lua。
    - :help lua-guide
    - (or HTML version): https://neovim.io/doc/user/lua-guide.html

Kickstart Guide:
Kickstart 指南：

  TODO: The very first thing you should do is to run the command `:Tutor` in Neovim.
  TODO: 您应该首先做的事情是运行 Neovim 中的 :Tutor 命令。

    If you don't know what this means, type the following:
    如果您不知道这是什么意思，请按以下步骤操作：
      - <escape key>
      - :
      - Tutor
      - <enter key>

    (If you already know the Neovim basics, you can skip this step.)
    （如果您已经了解 Neovim 的基础知识，可以跳过此步骤。）

  Once you've completed that, you can continue working through **AND READING** the rest
  of the kickstart init.lua.
  完成后，继续操作并*阅读*剩下的 Kickstart init.lua 文件。

  Next, run AND READ `:help`.
  接下来，运行并阅读 :help。
    This will open up a help window with some basic information
    about reading, navigating and searching the builtin help documentation.
    这将打开一个帮助窗口，其中包含有关阅读、导航和搜索内置帮助文档的基本信息。

    This should be the first place you go to look when you're stuck or confused
    with something. It's one of my favorite Neovim features.
    这是您在遇到困惑或不确定时应该首先查看的地方。这是我最喜欢的 Neovim 特性之一。

    MOST IMPORTANTLY, we provide a keymap "<space>sh" to [s]earch the [h]elp documentation,
    which is very useful when you're not exactly sure of what you're looking for.
    最重要的是，我们提供了一个键位映射 "<space>sh" 来 [s]earch [h]elp 文档，在您不确定具体想查找什么时非常有用。

  I have left several `:help X` comments throughout the init.lua
  我在 init.lua 中留了一些 :help X 注释。
    These are hints about where to find more information about the relevant settings,
    plugins or Neovim features used in Kickstart.
    这些是关于相关设置、插件或在 Kickstart 中使用的 Neovim 功能的提示。

   NOTE: Look for lines like this
   NOTE: 请查找像这样的行。

    Throughout the file. These are for you, the reader, to help you understand what is happening.
    Feel free to delete them once you know what you're doing, but they should serve as a guide
    for when you are first encountering a few different constructs in your Neovim config.
    这些是留给您的提示，帮助您理解配置中的不同构造。可以在您理解这些内容后删除它们，
    但它们应该能帮助您更好地理解 Neovim 配置中的各个部分。

If you experience any errors while trying to install kickstart, run `:checkhealth` for more info.
如果在安装 Kickstart 时遇到任何错误，请运行 `:checkhealth` 以获取更多信息。

I hope you enjoy your Neovim journey,
希望您喜欢 Neovim 的旅程
- TJ

P.S. You can delete this when you're done too. It's your config now! :)
P.S. 完成后您也可以删除这部分内容。这是您的配置了！ :)
--]]

-- Set <space> as the leader key
-- See `:help mapleader`
-- 设置全局和本地的 Leader Key
--  NOTE: Must happen before plugins are loaded (otherwise wrong leader will be used)
--  NOTE: 必须在加载插件之前（否则将使用错误的 Leader Key）
vim.g.mapleader = ' '
vim.g.maplocalleader = ' '

-- Set to true if you have a Nerd Font installed and selected in the terminal
-- 如果您在终端安装并选择了书呆子字体，请设置为 true
vim.g.have_nerd_font = true

-- [[ Setting options ]]
-- [[ 设置选项 ]]
-- See `:help vim.opt`
-- NOTE: You can change these options as you wish!
--  For more options, you can see `:help option-list`
-- NOTE: 您可以根据需要更改这些选项！有关更多选项，您可以看 `:help option-list`

-- Make line numbers default
-- 使行号默认
vim.opt.number = true
-- You can also add relative line numbers, to help with jumping.
-- 您还可以添加相对行号，以帮助跳跃。
-- Experiment for yourself to see if you like it!
-- 自己试验是否喜欢！
-- vim.opt.relativenumber = true

-- Enable mouse mode, can be useful for resizing splits for example!
-- 启用鼠标模式，调整拆分大小可能很有用！
vim.opt.mouse = 'a'

-- Don't show the mode, since it's already in the status line
-- 不要显示模式，因为它已经在状态行中
vim.opt.showmode = false

-- Sync clipboard between OS and Neovim.
-- 在操作系统和 Neovim 之间同步剪贴板。
--  Schedule the setting after `UiEnter` because it can increase startup-time.
--  在 `UiEnter` 事件后设置此选项，以避免增加启动时间。
--  Remove this option if you want your OS clipboard to remain independent.
--  如果希望操作系统的剪贴板保持独立，请移除此选项。
--  See `:help 'clipboard'`
vim.schedule(function()
  vim.opt.clipboard = 'unnamedplus'
end)

-- Enable break indent
-- 启用换行缩进
vim.opt.breakindent = true

-- Save undo history
-- 保存撤销历史
vim.opt.undofile = true

-- Case-insensitive searching UNLESS \C or one or more capital letters in the search term
-- 默认情况下，搜索不区分大小写，除非使用 `\C` 或搜索词中包含一个或多个大写字母
vim.opt.ignorecase = true
vim.opt.smartcase = true

-- Keep signcolumn on by default
-- 默认启用标志列
vim.opt.signcolumn = 'yes'

-- Decrease update time
-- 减少更新间隔时间
vim.opt.updatetime = 250

-- Decrease mapped sequence wait time
-- 减少映射序列等待时间
vim.opt.timeoutlen = 300

-- Configure how new splits should be opened
-- 配置新分割窗口的打开方式
vim.opt.splitright = true
vim.opt.splitbelow = true

-- Sets how neovim will display certain whitespace characters in the editor.
-- 设置 Neovim 如何在编辑器中显示某些空白字符。
--  See `:help 'list'`
--  and `:help 'listchars'`
vim.opt.list = true
vim.opt.listchars = { tab = '» ', trail = '·', nbsp = '␣' }

-- Preview substitutions live, as you type!
-- 在输入时实时预览替换内容！
vim.opt.inccommand = 'split'

-- Show which line your cursor is on
-- 显示光标所在行
vim.opt.cursorline = true

-- Minimal number of screen lines to keep above and below the cursor.
-- 光标上下方最少保留的屏幕行数
vim.opt.scrolloff = 10

-- [[ Basic Keymaps ]]
-- [[ 基本键位映射 ]]
--  See `:help vim.keymap.set()`

-- Clear highlights on search when pressing <Esc> in normal mode
-- 在普通模式下按下 <Esc> 键时，清除搜索高亮
--  See `:help hlsearch`
vim.keymap.set('n', '<Esc>', '<cmd>nohlsearch<CR>')

-- Diagnostic keymaps
-- 诊断键绑定
vim.keymap.set('n', '<leader>q', vim.diagnostic.setloclist, { desc = 'Open diagnostic [Q]uickfix list' })

-- Exit terminal mode in the builtin terminal with a shortcut that is a bit easier
-- for people to discover. Otherwise, you normally need to press <C-\><C-n>, which
-- is not what someone will guess without a bit more experience.
-- 在内置终端模式下使用更容易发现的快捷键退出终端模式
-- 否则，通常需要按 <C-\><C-n>，但没有一定经验的人很难猜到
--
-- NOTE: This won't work in all terminal emulators/tmux/etc. Try your own mapping
-- or just use <C-\><C-n> to exit terminal mode
-- NOTE: 注意：此映射在所有终端仿真器/tmux 等中可能不适用。可以尝试自己的映射，或者使用 <C-\><C-n> 退出终端模式。
vim.keymap.set('t', '<Esc><Esc>', '<C-\\><C-n>', { desc = 'Exit terminal mode' })

-- TIP: Disable arrow keys in normal mode
-- TIP: 禁用普通模式下的箭头键
-- vim.keymap.set('n', '<left>', '<cmd>echo "Use h to move!!"<CR>')
-- vim.keymap.set('n', '<right>', '<cmd>echo "Use l to move!!"<CR>')
-- vim.keymap.set('n', '<up>', '<cmd>echo "Use k to move!!"<CR>')
-- vim.keymap.set('n', '<down>', '<cmd>echo "Use j to move!!"<CR>')

-- Keybinds to make split navigation easier.
-- 使分屏导航更容易的快捷键绑定。
--  Use CTRL+<hjkl> to switch between windows
-- 使用 CTRL+<hjkl> 来在不同的窗口之间切换
--
--  See `:help wincmd` for a list of all window commands
vim.keymap.set('n', '<C-h>', '<C-w><C-h>', { desc = 'Move focus to the left window' })
vim.keymap.set('n', '<C-l>', '<C-w><C-l>', { desc = 'Move focus to the right window' })
vim.keymap.set('n', '<C-j>', '<C-w><C-j>', { desc = 'Move focus to the lower window' })
vim.keymap.set('n', '<C-k>', '<C-w><C-k>', { desc = 'Move focus to the upper window' })

-- [[ Basic Autocommands ]]
-- [[ 基本自动命令 ]]
--  See `:help lua-guide-autocommands`

-- Highlight when yanking (copying) text
-- 在复制文本时高亮显示
--  Try it with `yap` in normal mode
--  你可以在普通模式下试试 `yap` 命令
--  See `:help vim.highlight.on_yank()`
vim.api.nvim_create_autocmd('TextYankPost', {
  desc = 'Highlight when yanking (copying) text',
  group = vim.api.nvim_create_augroup('kickstart-highlight-yank', { clear = true }),
  callback = function()
    vim.highlight.on_yank()
  end,
})

-- [[ Install `lazy.nvim` plugin manager ]]
-- [[ 安装 `lazy.nvim` 插件管理器 ]]
--    See `:help lazy.nvim.txt` or https://github.com/folke/lazy.nvim for more info
local lazypath = vim.fn.stdpath 'data' .. '/lazy/lazy.nvim'
if not (vim.uv or vim.loop).fs_stat(lazypath) then
  local lazyrepo = 'https://github.com/folke/lazy.nvim.git'
  local out = vim.fn.system { 'git', 'clone', '--filter=blob:none', '--branch=stable', lazyrepo, lazypath }
  if vim.v.shell_error ~= 0 then
    error('Error cloning lazy.nvim:\n' .. out)
  end
end ---@diagnostic disable-next-line: undefined-field
vim.opt.rtp:prepend(lazypath)

-- [[ Configure and install plugins ]]
-- [[ 配置和安装插件 ]]
--
--  To check the current status of your plugins, run
--  要查看当前插件的状态，可以运行
--    :Lazy
--
--  You can press `?` in this menu for help. Use `:q` to close the window
--  在这个菜单中，你可以按 `?` 获取帮助。使用 `:q` 关闭窗口
--
--  To update plugins you can run
--  要更新插件，你可以运行
--    :Lazy update
--
-- NOTE: Here is where you install your plugins.
-- NOTE: 在这里是你安装插件的地方。
require('lazy').setup({
  -- NOTE: Plugins can be added with a link (or for a github repo: 'owner/repo' link).
  -- NOTE: 插件可以通过链接添加（或者对于 GitHub 仓库，可以用 'owner/repo' 格式的链接）。

  -- Detect tabstop and shiftwidth automatically
  -- 自动检测 tabstop 和 shiftwidth
  'tpope/vim-sleuth',

  -- NOTE: Plugins can also be added by using a table,
  -- NOTE: 插件也可以通过使用表格的方式添加，

  -- with the first argument being the link and the following
  -- keys can be used to configure plugin behavior/loading/etc.
  -- 第一个参数是插件链接，后续的键值对可以用来配置插件的行为/加载等。
  --
  -- Use `opts = {}` to force a plugin to be loaded.
  -- 使用 `opts = {}` 强制插件被加载。
  --

  -- Here is a more advanced example where we pass configuration
  -- 这是一个更高级的示例，我们为 `gitsigns.nvim` 传递配置选项。
  -- options to `gitsigns.nvim`. This is equivalent to the following Lua:
  -- 这等价于以下 Lua 代码：
  --    require('gitsigns').setup({ ... })
  --
  -- See `:help gitsigns` to understand what the configuration keys do
  { -- Adds git related signs to the gutter, as well as utilities for managing changes
    -- 向编辑器的边栏添加与 Git 相关的标志，并提供管理变更的工具
    'lewis6991/gitsigns.nvim',
    opts = {
      signs = {
        add = { text = '+' },
        change = { text = '~' },
        delete = { text = '_' },
        topdelete = { text = '‾' },
        changedelete = { text = '~' },
      },
    },
  },

  -- NOTE: Plugins can also be configured to run Lua code when they are loaded.
  -- NOTE: 插件也可以配置为在加载时运行 Lua 代码。
  --
  -- This is often very useful to both group configuration, as well as handle
  -- lazy loading plugins that don't need to be loaded immediately at startup.
  -- 这通常非常有用，可以将配置归类到一起，并处理不需要在启动时立即加载的懒加载插件。
  --
  -- For example, in the following configuration, we use:
  -- 例如，在下面的配置中，我们使用：
  --  event = 'VimEnter'
  --
  -- which loads which-key before all the UI elements are loaded. Events can be
  -- 这将在所有 UI 元素加载之前加载 which-key 插件。事件可以是
  -- normal autocommands events (`:help autocmd-events`).
  -- 普通的自动命令事件（参见 `:help autocmd-events`）。
  --
  -- Then, because we use the `opts` key (recommended), the configuration runs
  -- 然后，由于我们使用了 `opts` 键（推荐方式），配置会在插件
  -- after the plugin has been loaded as `require(MODULE).setup(opts)`.
  -- 被加载后通过 `require(MODULE).setup(opts)` 来运行。

  { -- Useful plugin to show you pending keybinds.
    -- 用于显示待定的快捷键绑定的插件。
    'folke/which-key.nvim',
    -- Sets the loading event to 'VimEnter'
    -- 设置加载事件为 'VimEnter'
    event = 'VimEnter',
    opts = {
      -- delay between pressing a key and opening which-key (milliseconds)
      -- 按下一个键并打开 which-key 之间的延迟（毫秒）
      -- this setting is independent of vim.opt.timeoutlen
      -- 这个设置独立于 vim.opt.timeoutlen
      delay = 0,
      icons = {
        -- set icon mappings to true if you have a Nerd Font
        -- 如果你有 Nerd Font，请将 mappings 设置为 true
        mappings = vim.g.have_nerd_font,
        -- If you are using a Nerd Font: set icons.keys to an empty table which will use the
        -- default which-key.nvim defined Nerd Font icons, otherwise define a string table
        -- 如果你使用 Nerd Font：将 icons.keys 设置为空表格，它将使用默认的 which-key.nvim 定义的 Nerd Font 图标，否则定义一个字符串表
        keys = vim.g.have_nerd_font and {} or {
          Up = '<Up> ',
          Down = '<Down> ',
          Left = '<Left> ',
          Right = '<Right> ',
          C = '<C-…> ',
          M = '<M-…> ',
          D = '<D-…> ',
          S = '<S-…> ',
          CR = '<CR> ',
          Esc = '<Esc> ',
          ScrollWheelDown = '<ScrollWheelDown> ',
          ScrollWheelUp = '<ScrollWheelUp> ',
          NL = '<NL> ',
          BS = '<BS> ',
          Space = '<Space> ',
          Tab = '<Tab> ',
          F1 = '<F1>',
          F2 = '<F2>',
          F3 = '<F3>',
          F4 = '<F4>',
          F5 = '<F5>',
          F6 = '<F6>',
          F7 = '<F7>',
          F8 = '<F8>',
          F9 = '<F9>',
          F10 = '<F10>',
          F11 = '<F11>',
          F12 = '<F12>',
        },
      },

      -- Document existing key chains
      -- 文档现有的快捷键链
      spec = {
        { '<leader>c', group = '[C]ode', mode = { 'n', 'x' } },
        { '<leader>d', group = '[D]ocument' },
        { '<leader>r', group = '[R]ename' },
        { '<leader>s', group = '[S]earch' },
        { '<leader>w', group = '[W]orkspace' },
        { '<leader>t', group = '[T]oggle' },
        { '<leader>h', group = 'Git [H]unk', mode = { 'n', 'v' } },
      },
    },
  },

  -- NOTE: Plugins can specify dependencies.
  -- NOTE: 插件可以指定依赖项
  --
  -- The dependencies are proper plugin specifications as well - anything
  -- you do for a plugin at the top level, you can do for a dependency.
  -- 依赖项也是插件，任何你对插件在顶层做的事情，都可以对依赖项做。
  --
  -- Use the `dependencies` key to specify the dependencies of a particular plugin
  -- 使用 `dependencies` key 来指定特定插件的依赖

  { -- Fuzzy Finder (files, lsp, etc)
    -- 模糊查找（文件、LSP 等）
    'nvim-telescope/telescope.nvim',
    event = 'VimEnter',
    branch = '0.1.x',
    dependencies = {
      'nvim-lua/plenary.nvim',
      { -- If encountering errors, see telescope-fzf-native README for installation instructions
        -- 如果遇到错误，查看 telescope-fzf-native 的 README 获取安装说明
        'nvim-telescope/telescope-fzf-native.nvim',

        -- `build` is used to run some command when the plugin is installed/updated.
        -- `build` 用来在插件安装/更新时执行某个命令。
        -- This is only run then, not every time Neovim starts up.
        -- 这只在插件安装时执行，而不是每次 Neovim 启动时执行。
        build = 'make',

        -- `cond` is a condition used to determine whether this plugin should be
        -- `cond` 是用来判断插件是否需要安装和加载的条件。
        -- installed and loaded.
        -- 如果条件不成立，插件将不会被加载。
        cond = function()
          return vim.fn.executable 'make' == 1
        end,
      },
      { 'nvim-telescope/telescope-ui-select.nvim' },

      -- Useful for getting pretty icons, but requires a Nerd Font.
      -- 用于获取漂亮的图标，但需要安装 Nerd Font 字体。
      { 'nvim-tree/nvim-web-devicons', enabled = vim.g.have_nerd_font },
    },
    config = function()
      -- Telescope is a fuzzy finder that comes with a lot of different things that
      -- it can fuzzy find! It's more than just a "file finder", it can search
      -- many different aspects of Neovim, your workspace, LSP, and more!
      -- Telescope 是一个模糊查找工具，它不仅可以查找文件，还可以查找 Neovim 中的很多其他内容，如 LSP、工作区等！
      --
      -- The easiest way to use Telescope, is to start by doing something like:
      -- 使用 Telescope 的最简单方式之一是运行类似下面的命令：
      --  :Telescope help_tags
      --
      -- After running this command, a window will open up and you're able to
      -- type in the prompt window. You'll see a list of `help_tags` options and
      -- a corresponding preview of the help.
      -- 执行该命令后，会打开一个窗口，你可以在提示框中输入搜索内容，看到 `help_tags` 的选项列表，并且对应的帮助信息也会预览。
      --
      -- Two important keymaps to use while in Telescope are:
      -- 在 Telescope 中，两个非常有用的快捷键是：
      --  - Insert mode: <c-/>
      --  - Normal mode: ?
      --
      -- This opens a window that shows you all of the keymaps for the current
      -- Telescope picker. This is really useful to discover what Telescope can
      -- do as well as how to actually do it!
      -- 这将会显示当前 Telescope 选择器的所有键位绑定，帮助你发现 Telescope 的更多功能，并且教你如何使用它们！

      -- [[ Configure Telescope ]]
      -- See `:help telescope` and `:help telescope.setup()`
      require('telescope').setup {
        -- You can put your default mappings / updates / etc. in here
        -- 可以在这里设置默认的映射、更新等
        -- All the info you're looking for is in `:help telescope.setup()`
        -- 所有需要的配置信息都可以在 `:help telescope.setup()` 中找到
        --
        -- defaults = {
        --   mappings = {
        --     i = { ['<c-enter>'] = 'to_fuzzy_refine' },
        --   },
        -- },
        -- pickers = {}
        extensions = {
          ['ui-select'] = {
            require('telescope.themes').get_dropdown(),
          },
        },
      }

      -- Enable Telescope extensions if they are installed
      -- 如果插件被安装，加载 Telescope 扩展
      pcall(require('telescope').load_extension, 'fzf')
      pcall(require('telescope').load_extension, 'ui-select')

      -- See `:help telescope.builtin`
      -- 详细配置见 `:help telescope.builtin`
      local builtin = require 'telescope.builtin'
      vim.keymap.set('n', '<leader>sh', builtin.help_tags, { desc = '[S]earch [H]elp' })
      vim.keymap.set('n', '<leader>sk', builtin.keymaps, { desc = '[S]earch [K]eymaps' })
      vim.keymap.set('n', '<leader>sf', builtin.find_files, { desc = '[S]earch [F]iles' })
      vim.keymap.set('n', '<leader>ss', builtin.builtin, { desc = '[S]earch [S]elect Telescope' })
      vim.keymap.set('n', '<leader>sw', builtin.grep_string, { desc = '[S]earch current [W]ord' })
      vim.keymap.set('n', '<leader>sg', builtin.live_grep, { desc = '[S]earch by [G]rep' })
      vim.keymap.set('n', '<leader>sd', builtin.diagnostics, { desc = '[S]earch [D]iagnostics' })
      vim.keymap.set('n', '<leader>sr', builtin.resume, { desc = '[S]earch [R]esume' })
      vim.keymap.set('n', '<leader>s.', builtin.oldfiles, { desc = '[S]earch Recent Files ("." for repeat)' })
      vim.keymap.set('n', '<leader><leader>', builtin.buffers, { desc = '[ ] Find existing buffers' })

      -- Slightly advanced example of overriding default behavior and theme
      -- 这是一个稍微复杂的示例，展示如何覆盖默认行为和主题
      vim.keymap.set('n', '<leader>/', function()
        -- You can pass additional configuration to Telescope to change the theme, layout, etc.
        -- 你可以传递额外的配置来改变 Telescope 的主题、布局等
        builtin.current_buffer_fuzzy_find(require('telescope.themes').get_dropdown {
          winblend = 10,
          previewer = false,
          layout_config = {
            width = 0.7, -- 宽度占屏幕 70%（0~1 之间的百分比，或像素值）
            height = 30, -- 高度设置为 30 行
          },
        })
      end, { desc = '[/] Fuzzily search in current buffer' })

      -- It's also possible to pass additional configuration options.
      -- 也可以传递额外的配置选项。
      --  See `:help telescope.builtin.live_grep()` for information about particular keys
      vim.keymap.set('n', '<leader>s/', function()
        builtin.live_grep {
          grep_open_files = true,
          prompt_title = 'Live Grep in Open Files',
        }
      end, { desc = '[S]earch [/] in Open Files' })

      -- Shortcut for searching your Neovim configuration files
      -- 搜索 Neovim 配置文件的快捷键
      vim.keymap.set('n', '<leader>sn', function()
        builtin.find_files { cwd = vim.fn.stdpath 'config' }
      end, { desc = '[S]earch [N]eovim files' })
    end,
  },

  -- LSP Plugins
  {
    -- `lazydev` configures Lua LSP for your Neovim config, runtime and plugins
    -- `lazydev` 配置 Lua LSP 用于你的 Neovim 配置、运行时和插件
    -- used for completion, annotations and signatures of Neovim apis
    -- 用于补全、注释和 Neovim API 的签名
    'folke/lazydev.nvim',
    ft = 'lua',
    opts = {
      library = {
        -- Load luvit types when the `vim.uv` word is found
        -- 加载 luvit 当发现 `vim.uv` 这个词时
        { path = '${3rd}/luv/library', words = { 'vim%.uv' } },
      },
    },
  },
  {
    -- Main LSP Configuration
    -- 主 LSP 配置
    'neovim/nvim-lspconfig',
    dependencies = {
      -- Automatically install LSPs and related tools to stdpath for Neovim
      -- 自动安装 LSP 及相关工具到 Neovim 的标准路径
      -- Mason must be loaded before its dependents so we need to set it up here.
      -- Mason 必须在其依赖项之前加载，因此我们需要在这里设置它。
      -- NOTE: `opts = {}` is the same as calling `require('mason').setup({})`
      -- NOTE: `opts = {}` 和调用 `require('mason').setup({})` 是一样的
      { 'williamboman/mason.nvim', opts = {} },
      'williamboman/mason-lspconfig.nvim',
      'WhoIsSethDaniel/mason-tool-installer.nvim',

      -- Useful status updates for LSP.
      -- LSP 的有用状态更新。
      { 'j-hui/fidget.nvim', opts = {} },

      -- Allows extra capabilities provided by nvim-cmp
      -- 允许 nvim-cmp 提供额外的功能
      'hrsh7th/cmp-nvim-lsp',
    },
    config = function()
      -- Brief aside: **What is LSP?**
      -- 简短说明：**什么是 LSP？**
      --
      -- LSP is an initialism you've probably heard, but might not understand what it is.
      -- LSP 是你可能听过的首字母缩写，但可能不太了解它是什么。
      --
      -- LSP stands for Language Server Protocol. It's a protocol that helps editors
      -- and language tooling communicate in a standardized fashion.
      -- LSP 代表语言服务器协议（Language Server Protocol）。它是一个帮助编辑器和语言工具以标准化的方式进行通信的协议。
      --
      -- In general, you have a "server" which is some tool built to understand a particular
      -- 一般来说，你有一个“服务器”，这是一个用来理解特定语言的工具
      -- language (such as `gopls`, `lua_ls`, `rust_analyzer`, etc.). These Language Servers
      -- （如 `gopls`、`lua_ls`、`rust_analyzer` 等）。这些语言服务器
      -- (sometimes called LSP servers, but that's kind of like ATM Machine) are standalone
      -- processes that communicate with some "client" - in this case, Neovim!
      -- （有时也叫 LSP 服务器，但这就像 ATM 机一样的说法）是独立的进程，它们和某个“客户端”进行通信——在这种情况下是 Neovim！
      --
      -- LSP provides Neovim with features like:
      -- LSP 为 Neovim 提供了如下功能：
      --  - Go to definition
      --  - 跳转到定义
      --  - Find references
      --  - - 查找引用
      --  - Autocompletion
      --  - 自动补全
      --  - Symbol Search
      --  - 符号搜索
      --  - and more!
      --  - 以及更多！
      --
      -- Thus, Language Servers are external tools that must be installed separately from
      -- Neovim. This is where `mason` and related plugins come into play.
      -- 因此，语言服务器是需要单独安装的外部工具，与 Neovim 分开安装。这就是 `mason` 和相关插件的作用。
      --
      -- If you're wondering about lsp vs treesitter, you can check out the wonderfully
      -- and elegantly composed help section, `:help lsp-vs-treesitter`
      -- 如果你在疑惑 LSP 和 treesitter 的区别，可以查看帮助文档 `:help lsp-vs-treesitter`

      --  This function gets run when an LSP attaches to a particular buffer.
      --    That is to say, every time a new file is opened that is associated with
      --    an lsp (for example, opening `main.rs` is associated with `rust_analyzer`) this
      --    function will be executed to configure the current buffer
      -- 这个函数会在 LSP 附加到特定缓冲区时运行。也就是说，每次打开与 LSP 相关的文件时
      -- （例如，打开 `main.rs` 关联 `rust_analyzer`），这个函数会被执行来配置当前缓冲区。
      vim.api.nvim_create_autocmd('LspAttach', {
        group = vim.api.nvim_create_augroup('kickstart-lsp-attach', { clear = true }),
        callback = function(event)
          -- NOTE: Remember that Lua is a real programming language, and as such it is possible
          -- to define small helper and utility functions so you don't have to repeat yourself.
          -- NOTE: 记住 Lua 是一门真正的编程语言，因此可以定义小的助手和工具函数，这样你就不必重复相同的代码。
          --
          -- In this case, we create a function that lets us more easily define mappings specific
          -- for LSP related items. It sets the mode, buffer and description for us each time.
          -- 在这里，我们创建了一个函数，可以让我们更轻松地为与 LSP 相关的操作定义快捷键。每次都会设置模式、缓冲区和描述。
          local map = function(keys, func, desc, mode)
            mode = mode or 'n'
            vim.keymap.set(mode, keys, func, { buffer = event.buf, desc = 'LSP: ' .. desc })
          end

          -- Jump to the definition of the word under your cursor.
          -- 跳转到光标下单词的定义。
          -- This is where a variable was first declared, or where a function is defined, etc.
          -- 这是变量第一次声明的位置，或函数定义的位置等。
          -- To jump back, press <C-t>.
          -- 要跳回来，按 <C-t>。
          map('gd', require('telescope.builtin').lsp_definitions, '[G]oto [D]efinition')

          -- Find references for the word under your cursor.
          -- 查找光标下单词的引用。
          map('gr', require('telescope.builtin').lsp_references, '[G]oto [R]eferences')

          -- Jump to the implementation of the word under your cursor.
          -- 跳转到光标下单词的实现。
          -- Useful when your language has ways of declaring types without an actual implementation.
          -- 当你的语言中有声明类型而没有实际实现时很有用。
          map('gI', require('telescope.builtin').lsp_implementations, '[G]oto [I]mplementation')

          -- Jump to the type of the word under your cursor.
          -- 跳转到光标下单词的类型。
          --  Useful when you're not sure what type a variable is and you want to see
          --  the definition of its *type*, not where it was *defined*.
          --  当你不确定某个变量的类型时，可以查看它的*类型*定义，而不是它的*定义*位置。
          map('<leader>D', require('telescope.builtin').lsp_type_definitions, 'Type [D]efinition')

          -- Fuzzy find all the symbols in your current document.
          -- 在当前文档中模糊查找所有符号。
          --  Symbols are things like variables, functions, types, etc.
          --  符号包括变量、函数、类型等。
          map('<leader>ds', require('telescope.builtin').lsp_document_symbols, '[D]ocument [S]ymbols')

          -- Fuzzy find all the symbols in your current workspace.
          -- 在当前工作区中模糊查找所有符号。
          --  Similar to document symbols, except searches over your entire project.
          --  类似文档符号，只不过是搜索整个项目。
          map('<leader>ws', require('telescope.builtin').lsp_dynamic_workspace_symbols, '[W]orkspace [S]ymbols')

          -- Rename the variable under your cursor.
          -- 重命名光标下的变量。
          --  Most Language Servers support renaming across files, etc.
          --  大多数语言服务器支持跨文件重命名。
          map('<leader>rn', vim.lsp.buf.rename, '[R]e[n]ame')

          -- Execute a code action, usually your cursor needs to be on top of an error
          -- or a suggestion from your LSP for this to activate.
          -- 执行代码操作，通常光标需要停留在 LSP 提供的错误或建议上才能激活。
          map('<leader>ca', vim.lsp.buf.code_action, '[C]ode [A]ction', { 'n', 'x' })

          -- WARN: This is not Goto Definition, this is Goto Declaration.
          -- WARN: 警告：这不是跳转到定义，这是跳转到声明。
          --  For example, in C this would take you to the header.
          --  例如，在 C 语言中，这将带你到头文件。
          map('gD', vim.lsp.buf.declaration, '[G]oto [D]eclaration')

          -- The following two autocommands are used to highlight references of the
          -- word under your cursor when your cursor rests there for a little while.
          -- 以下两个自动命令用于在光标停留一段时间后高亮显示光标下单词的引用。
          --    See `:help CursorHold` for information about when this is executed
          --
          -- When you move your cursor, the highlights will be cleared (the second autocommand).
          -- 当你移动光标时，突出显示将被清除（第二个自动命令）。
          local client = vim.lsp.get_client_by_id(event.data.client_id)
          if client and client.supports_method(vim.lsp.protocol.Methods.textDocument_documentHighlight) then
            local highlight_augroup = vim.api.nvim_create_augroup('kickstart-lsp-highlight', { clear = false })
            vim.api.nvim_create_autocmd({ 'CursorHold', 'CursorHoldI' }, {
              buffer = event.buf,
              group = highlight_augroup,
              callback = vim.lsp.buf.document_highlight,
            })

            vim.api.nvim_create_autocmd({ 'CursorMoved', 'CursorMovedI' }, {
              buffer = event.buf,
              group = highlight_augroup,
              callback = vim.lsp.buf.clear_references,
            })

            vim.api.nvim_create_autocmd('LspDetach', {
              group = vim.api.nvim_create_augroup('kickstart-lsp-detach', { clear = true }),
              callback = function(event2)
                vim.lsp.buf.clear_references()
                vim.api.nvim_clear_autocmds { group = 'kickstart-lsp-highlight', buffer = event2.buf }
              end,
            })
          end

          -- The following code creates a keymap to toggle inlay hints in your
          -- code, if the language server you are using supports them
          -- 这段代码创建了一个快捷键来切换你的代码中的内嵌提示，如果你使用的语言服务器支持它的话。
          --
          -- This may be unwanted, since they displace some of your code
          -- 这可能是多余的，因为它会覆盖部分代码。
          if client and client.supports_method(vim.lsp.protocol.Methods.textDocument_inlayHint) then
            map('<leader>th', function()
              vim.lsp.inlay_hint.enable(not vim.lsp.inlay_hint.is_enabled { bufnr = event.buf })
            end, '[T]oggle Inlay [H]ints')
          end
        end,
      })

      -- Change diagnostic symbols in the sign column (gutter)
      -- 更改诊断符号在标志栏（gutter）中的显示方式如果你的环境支持 Nerd Font，可以启用自定义符号。
      -- if vim.g.have_nerd_font then
      --   local signs = { ERROR = '', WARN = '', INFO = '', HINT = '' }
      --   local diagnostic_signs = {}
      --   for type, icon in pairs(signs) do
      --     diagnostic_signs[vim.diagnostic.severity[type]] = icon
      --   end
      --   vim.diagnostic.config { signs = { text = diagnostic_signs } }
      -- end

      -- LSP servers and clients are able to communicate to each other what features they support.
      -- LSP 服务器和客户端可以彼此通信，告知它们支持哪些功能。
      --  By default, Neovim doesn't support everything that is in the LSP specification.
      --  默认情况下，Neovim 并不支持 LSP 规范中的所有内容。
      --  When you add nvim-cmp, luasnip, etc. Neovim now has *more* capabilities.
      --  当你添加 nvim-cmp、luasnip 等插件时，Neovim 就有了更多的能力。
      --  So, we create new capabilities with nvim cmp, and then broadcast that to the servers.
      --  因此，我们创建了一个新的能力表，然后广播给服务器。
      local capabilities = vim.lsp.protocol.make_client_capabilities()
      capabilities = vim.tbl_deep_extend('force', capabilities, require('cmp_nvim_lsp').default_capabilities())

      -- Enable the following language servers
      -- 启用以下语言服务器
      --  Feel free to add/remove any LSPs that you want here. They will automatically be installed.
      --  你可以在这里添加/删除任何你想要的 LSP，它们将会被自动安装。
      --
      --  Add any additional override configuration in the following tables. Available keys are:
      --  可以在以下表格中添加额外的配置项。可用的配置项包括：
      --  - cmd (table): Override the default command used to start the server
      --  - cmd (table): 覆盖启动服务器时使用的默认命令
      --  - filetypes (table): Override the default list of associated filetypes for the server
      --  - filetypes (table): 覆盖服务器关联的文件类型列表
      --  - capabilities (table): Override fields in capabilities. Can be used to disable certain LSP features.
      --  - capabilities (table): 覆盖能力字段。可以用来禁用某些 LSP 功能。
      --  - settings (table): Override the default settings passed when initializing the server.
      --  - settings (table): 覆盖初始化服务器时传递的默认设置。
      --        For example, to see the options for `lua_ls`, you could go to: https://luals.github.io/wiki/settings/
      --        例如，想查看 `lua_ls` 的设置，可以访问： https://luals.github.io/wiki/settings/
      local servers = {
        -- clangd = {},
        -- gopls = {},
        -- pyright = {},
        -- rust_analyzer = {},
        -- ... etc. See `:help lspconfig-all` for a list of all the pre-configured LSPs
        -- 查看 `:help lspconfig-all` 获取所有预配置的 LSP 列表
        --
        -- Some languages (like typescript) have entire language plugins that can be useful:
        -- 一些语言（如 TypeScript）有完整的语言插件，这些插件可能很有用：
        --    https://github.com/pmizio/typescript-tools.nvim
        --
        -- But for many setups, the LSP (`ts_ls`) will work just fine
        -- 但对于许多设置，LSP（`ts_ls`）就足够用了
        -- ts_ls = {},
        --

        lua_ls = {
          -- cmd = { ... },
          -- filetypes = { ... },
          -- capabilities = {},
          settings = {
            Lua = {
              completion = {
                callSnippet = 'Replace',
              },
              -- You can toggle below to ignore Lua_LS's noisy `missing-fields` warnings
              -- 你可以切换以下设置来忽略 Lua_LS 发出的 `missing-fields` 警告
              -- diagnostics = { disable = { 'missing-fields' } },
            },
          },
        },
      }

      -- Ensure the servers and tools above are installed
      -- 确保安装上述语言服务器和工具
      --
      -- To check the current status of installed tools and/or manually install
      -- other tools, you can run
      -- 要检查已安装工具的当前状态，或手动安装其他工具，可以运行
      --    :Mason
      --
      -- You can press `g?` for help in this menu.
      -- 在这个菜单中，你可以按 `g?` 获取帮助。
      --
      -- `mason` had to be setup earlier: to configure its options see the
      -- `dependencies` table for `nvim-lspconfig` above.
      -- `mason` 必须在之前设置：请参阅上面的 `nvim-lspconfig` 的 `dependencies` 表。
      --
      -- You can add other tools here that you want Mason to install
      -- for you, so that they are available from within Neovim.
      -- 你可以在此添加其他你想让 Mason 安装的工具这样它们就可以在 Neovim 中使用。
      local ensure_installed = vim.tbl_keys(servers or {})
      vim.list_extend(ensure_installed, {
        -- Used to format Lua code
        -- 用于格式化 Lua 代码
        'stylua',
      })
      require('mason-tool-installer').setup { ensure_installed = ensure_installed }

      require('mason-lspconfig').setup {
        handlers = {
          function(server_name)
            local server = servers[server_name] or {}
            -- This handles overriding only values explicitly passed
            -- by the server configuration above. Useful when disabling
            -- certain features of an LSP (for example, turning off formatting for ts_ls)
            -- 这只处理显式传递的配置值覆盖对于禁用 LSP 的某些功能很有用（例如，关闭 ts_ls 的格式化功能）
            server.capabilities = vim.tbl_deep_extend('force', {}, capabilities, server.capabilities or {})
            require('lspconfig')[server_name].setup(server)
          end,
        },
      }
    end,
  },

  { -- Autoformat
    -- 自动格式化
    'stevearc/conform.nvim',
    event = { 'BufWritePre' },
    cmd = { 'ConformInfo' },
    keys = {
      {
        '<leader>f',
        function()
          require('conform').format { async = true, lsp_format = 'fallback' }
        end,
        mode = '',
        desc = '[F]ormat buffer',
      },
    },
    opts = {
      notify_on_error = false,
      format_on_save = function(bufnr)
        -- Disable "format_on_save lsp_fallback" for languages that don't
        -- have a well standardized coding style. You can add additional
        -- languages here or re-enable it for the disabled ones.
        -- 禁用对于没有标准化编码风格的语言的 "format_on_save lsp_fallback"
        -- 你可以在这里添加其他语言，或者重新启用对被禁用语言的支持。
        local disable_filetypes = { c = true, cpp = true }
        local lsp_format_opt
        if disable_filetypes[vim.bo[bufnr].filetype] then
          lsp_format_opt = 'never'
        else
          lsp_format_opt = 'fallback'
        end
        return {
          timeout_ms = 500,
          lsp_format = lsp_format_opt,
        }
      end,
      formatters_by_ft = {
        lua = { 'stylua' },
        -- Conform can also run multiple formatters sequentially
        -- Conform 也可以顺序运行多个格式化工具
        -- python = { "isort", "black" },
        --
        -- You can use 'stop_after_first' to run the first available formatter from the list
        -- 你可以使用 'stop_after_first' 来运行列表中的第一个可用格式化工具
        -- javascript = { "prettierd", "prettier", stop_after_first = true },
      },
    },
  },

  { -- Autocompletion
    -- 自动补全
    'hrsh7th/nvim-cmp',
    event = 'InsertEnter',
    dependencies = {
      -- Snippet Engine & its associated nvim-cmp source
      -- 片段引擎及其关联的 nvim-cmp 源
      {
        'L3MON4D3/LuaSnip',
        build = (function()
          -- Build Step is needed for regex support in snippets.
          -- 构建步骤是为片段中的正则表达式支持所需的。
          -- This step is not supported in many windows environments.
          -- 这个步骤在许多 Windows 环境中不被支持。
          -- Remove the below condition to re-enable on windows.
          -- 如果你在 Windows 上使用，请删除下面的条件来重新启用它。
          if vim.fn.has 'win32' == 1 or vim.fn.executable 'make' == 0 then
            return
          end
          return 'make install_jsregexp'
        end)(),
        dependencies = {
          -- `friendly-snippets` contains a variety of premade snippets.
          -- `friendly-snippets` 包含了各种预制的片段。
          --    See the README about individual language/framework/plugin snippets:
          --    请查看 README 获取关于各语言/框架/插件的片段信息：
          --    https://github.com/rafamadriz/friendly-snippets
          -- {
          --   'rafamadriz/friendly-snippets',
          --   config = function()
          --     require('luasnip.loaders.from_vscode').lazy_load()
          --   end,
          -- },
        },
      },
      'saadparwaiz1/cmp_luasnip',

      -- Adds other completion capabilities.
      -- 增加其他补全能力。
      --  nvim-cmp does not ship with all sources by default. They are split
      --  into multiple repos for maintenance purposes.
      --  nvim-cmp 默认并不包含所有的源。它们被拆分成多个仓库以便于维护。
      'hrsh7th/cmp-nvim-lsp',
      'hrsh7th/cmp-path',
    },
    config = function()
      -- See `:help cmp`
      local cmp = require 'cmp'
      local luasnip = require 'luasnip'
      luasnip.config.setup {}

      cmp.setup {
        snippet = {
          expand = function(args)
            luasnip.lsp_expand(args.body)
          end,
        },
        completion = { completeopt = 'menu,menuone,noinsert' },

        -- For an understanding of why these mappings were
        -- chosen, you will need to read `:help ins-completion`
        -- 关于这些映射为何如此设置，你需要阅读 `:help ins-completion`
        --
        -- No, but seriously. Please read `:help ins-completion`, it is really good!
        -- 不，真的，请阅读 `:help ins-completion`，它非常有用！
        mapping = cmp.mapping.preset.insert {
          -- Select the [n]ext item
          -- 选择下一个项目
          ['<C-n>'] = cmp.mapping.select_next_item(),
          -- Select the [p]revious item
          -- 选择上一个项目
          ['<C-p>'] = cmp.mapping.select_prev_item(),

          -- Scroll the documentation window [b]ack / [f]orward
          -- 滚动文档窗口 [b]ack / [f]orward
          ['<C-b>'] = cmp.mapping.scroll_docs(-4),
          ['<C-f>'] = cmp.mapping.scroll_docs(4),

          -- Accept ([y]es) the completion.
          -- 接受 ([y]es) 补全。
          --  This will auto-import if your LSP supports it.
          --  这将在 LSP 支持的情况下自动导入。
          --  This will expand snippets if the LSP sent a snippet.
          --  这将展开 LSP 发送的片段。
          ['<C-y>'] = cmp.mapping.confirm { select = true },

          -- If you prefer more traditional completion keymaps,
          -- 如果你更喜欢传统的补全键映射，
          -- you can uncomment the following lines
          -- 可以取消注释以下几行
          --['<CR>'] = cmp.mapping.confirm { select = true },
          --['<Tab>'] = cmp.mapping.select_next_item(),
          --['<S-Tab>'] = cmp.mapping.select_prev_item(),

          -- Manually trigger a completion from nvim-cmp.
          -- 手动触发 nvim-cmp 补全。
          --  Generally you don't need this, because nvim-cmp will display
          --  completions whenever it has completion options available.
          --  通常你不需要这样做，因为 nvim-cmp 会在有补全选项时自动显示。
          ['<C-Space>'] = cmp.mapping.complete {},

          -- Think of <c-l> as moving to the right of your snippet expansion.
          -- 可以把 <c-l> 想象成是将焦点移到你的片段展开的右边。
          --  So if you have a snippet that's like:
          --  例如如果你有一个像这样的片段：
          --  function $name($args)
          --    $body
          --  end
          --
          -- <c-l> will move you to the right of each of the expansion locations.
          -- 将把你移到每个展开位置的右边。
          -- <c-h> is similar, except moving you backwards.
          -- 类似，只是将你移回去。
          ['<C-l>'] = cmp.mapping(function()
            if luasnip.expand_or_locally_jumpable() then
              luasnip.expand_or_jump()
            end
          end, { 'i', 's' }),
          ['<C-h>'] = cmp.mapping(function()
            if luasnip.locally_jumpable(-1) then
              luasnip.jump(-1)
            end
          end, { 'i', 's' }),

          -- For more advanced Luasnip keymaps (e.g. selecting choice nodes, expansion) see:
          -- 想了解更多关于 Luasnip 的高级映射（例如选择选择节点、展开等）请查看：
          --    https://github.com/L3MON4D3/LuaSnip?tab=readme-ov-file#keymaps
        },
        sources = {
          {
            name = 'lazydev',
            -- set group index to 0 to skip loading LuaLS completions as lazydev recommends it
            -- 设置组索引为 0，以跳过加载 LuaLS 的补全，因为 lazydev 推荐不加载它
            group_index = 0,
          },
          { name = 'nvim_lsp' },
          { name = 'luasnip' },
          { name = 'path' },
        },
      }
    end,
  },

  { -- You can easily change to a different colorscheme.
    -- 你可以轻松地更换颜色方案。
    -- Change the name of the colorscheme plugin below, and then
    -- change the command in the config to whatever the name of that colorscheme is.
    -- 只需要更改下面的颜色方案插件名称，然后把配置中的命令改为你想要的颜色方案名称。
    --
    -- If you want to see what colorschemes are already installed, you can use `:Telescope colorscheme`.
    -- 如果你想查看已安装的颜色方案，可以使用 `:Telescope colorscheme`。
    'folke/tokyonight.nvim',
    -- Make sure to load this before all the other start plugins.
    -- 确保这个在其他所有启动插件之前加载。
    priority = 1000,
    init = function()
      -- Load the colorscheme here.
      -- 在这里加载颜色方案。
      -- Like many other themes, this one has different styles, and you could load
      -- any other, such as 'tokyonight-storm', 'tokyonight-moon', or 'tokyonight-day'.
      -- 和许多其他主题一样，它有不同的样式，你可以加载任何其他样式，例如 'tokyonight-storm', 'tokyonight-moon' 或 'tokyonight-day'。
      vim.cmd.colorscheme 'tokyonight-night'

      -- You can configure highlights by doing something like:
      -- 你可以通过类似下面的方式配置高亮：
      vim.cmd.hi 'Comment gui=none'
    end,
  },

  -- Highlight todo, notes, etc in comments
  -- 高亮 TODO、笔记等在注释中
  { 'folke/todo-comments.nvim', event = 'VimEnter', dependencies = { 'nvim-lua/plenary.nvim' }, opts = { signs = false } },

  { -- Collection of various small independent plugins/modules
    -- 各种小型独立插件/模块的集合
    'echasnovski/mini.nvim',
    config = function()
      -- Better Around/Inside textobjects
      -- 更好的 Around/Inside 文本对象
      --
      -- Examples:
      --  - va)  - [V]isually select [A]round [)]paren
      --  - yinq - [Y]ank [I]nside [N]ext [Q]uote
      --  - ci'  - [C]hange [I]nside [']quote
      require('mini.ai').setup { n_lines = 500 }

      -- Add/delete/replace surroundings (brackets, quotes, etc.)
      --
      -- - saiw) - [S]urround [A]dd [I]nner [W]ord [)]Paren
      -- - sd'   - [S]urround [D]elete [']quotes
      -- - sr)'  - [S]urround [R]eplace [)] [']
      require('mini.surround').setup()

      -- Simple and easy statusline.
      -- 简单易用的状态栏。
      --  You could remove this setup call if you don't like it,
      --  and try some other statusline plugin
      --  如果你不喜欢这个设置，可以删除这个设置调用，并尝试其他状态栏插件
      local statusline = require 'mini.statusline'
      -- set use_icons to true if you have a Nerd Font
      -- 如果你有 Nerd Font，可以将 use_icons 设置为 true
      statusline.setup { use_icons = vim.g.have_nerd_font }

      -- You can configure sections in the statusline by overriding their
      -- default behavior. For example, here we set the section for
      -- cursor location to LINE:COLUMN
      -- 你可以通过覆盖默认行为来配置状态栏中的各个部分。例如，这里我们将光标位置部分设置为 LINE:COLUMN
      ---@diagnostic disable-next-line: duplicate-set-field
      statusline.section_location = function()
        return '%2l:%-2v'
      end

      -- ... and there is more!
      -- ... 还有更多！
      --  Check out: https://github.com/echasnovski/mini.nvim
    end,
  },
  { -- Highlight, edit, and navigate code
    -- 高亮、编辑和导航代码
    'nvim-treesitter/nvim-treesitter',
    build = ':TSUpdate',
    -- Sets main module to use for opts
    -- 设置用于配置的主模块
    main = 'nvim-treesitter.configs',
    -- [[ Configure Treesitter ]] See `:help nvim-treesitter`
    -- [[ 配置 Treesitter ]] 查看 `:help nvim-treesitter`
    opts = {
      ensure_installed = { 'bash', 'c', 'diff', 'html', 'lua', 'luadoc', 'markdown', 'markdown_inline', 'query', 'vim', 'vimdoc' },
      -- Autoinstall languages that are not installed
      -- 自动安装未安装的语言
      auto_install = true,
      highlight = {
        enable = true,
        -- Some languages depend on vim's regex highlighting system (such as Ruby) for indent rules.
        -- 一些语言依赖于 vim 的正则高亮系统（例如 Ruby）来处理缩进规则。
        --  If you are experiencing weird indenting issues, add the language to
        --  the list of additional_vim_regex_highlighting and disabled languages for indent.
        --  如果你遇到奇怪的缩进问题，可以将该语言添加到 `additional_vim_regex_highlighting` 和禁用语言列表中。
        additional_vim_regex_highlighting = { 'ruby' },
      },
      indent = { enable = true, disable = { 'ruby' } },
    },
    -- There are additional nvim-treesitter modules that you can use to interact
    -- with nvim-treesitter. You should go explore a few and see what interests you:
    -- 还有一些额外的 nvim-treesitter 模块可以用来与 nvim-treesitter 交互你应该去探索一下，看看哪些对你有兴趣：
    --
    --    - Incremental selection: Included, see `:help nvim-treesitter-incremental-selection-mod`
    --    - Show your current context: https://github.com/nvim-treesitter/nvim-treesitter-context
    --    - Treesitter + textobjects: https://github.com/nvim-treesitter/nvim-treesitter-textobjects
  },

  -- The following comments only work if you have downloaded the kickstart repo, not just copy pasted the
  -- init.lua. If you want these files, they are in the repository, so you can just download them and
  -- place them in the correct locations.
  -- 以下注释仅在你下载了 kickstart 仓库时有效，而不是只复制粘贴了 init.lua。如果你想要这些文件，它们可以在仓库中找到，你只需要下载并放在正确的位置。

  -- NOTE: Next step on your Neovim journey: Add/Configure additional plugins for Kickstart
  -- NOTE: 你 Neovim 之旅的下一步：添加/配置 Kickstart 的额外插件
  --
  --  Here are some example plugins that I've included in the Kickstart repository.
  --  Uncomment any of the lines below to enable them (you will need to restart nvim).
  --  这里是我在 Kickstart 仓库中包含的一些示例插件。取消注释下面的任意行来启用它们（你需要重新启动 nvim）。
  --
  -- require 'kickstart.plugins.debug',
  -- require 'kickstart.plugins.indent_line',
  -- require 'kickstart.plugins.lint',
  -- require 'kickstart.plugins.autopairs',
  -- require 'kickstart.plugins.neo-tree',
  -- require 'kickstart.plugins.gitsigns', -- adds gitsigns recommend keymaps

  -- NOTE: The import below can automatically add your own plugins, configuration, etc from `lua/custom/plugins/*.lua`
  -- NOTE: 注意：以下导入可以自动添加你自己的插件、配置等来自 `lua/custom/plugins/*.lua`
  --    This is the easiest way to modularize your config.
  --    这是模块化配置的最简单方法。
  --
  --  Uncomment the following line and add your plugins to `lua/custom/plugins/*.lua` to get going.
  --  取消注释以下行并将你的插件添加到 `lua/custom/plugins/*.lua` 中开始使用。
  --    For additional information, see `:help lazy.nvim-lazy.nvim-structuring-your-plugins`
  { import = 'custom.plugins' },
}, {
  ui = {
    -- If you are using a Nerd Font: set icons to an empty table which will use the
    -- default lazy.nvim defined Nerd Font icons, otherwise define a unicode icons table
    -- 如果你正在使用 Nerd Font：将 icons 设置为空表，这样会使用默认的 lazy.nvim 定义的 Nerd Font 图标，
    -- 否则定义一个 Unicode 图标表
    icons = vim.g.have_nerd_font and {} or {
      cmd = '⌘',
      config = '🛠',
      event = '📅',
      ft = '📂',
      init = '⚙',
      keys = '🗝',
      plugin = '🔌',
      runtime = '💻',
      require = '🌙',
      source = '📄',
      start = '🚀',
      task = '📌',
      lazy = '💤 ',
    },
  },
})

-- The line beneath this is called `modeline`. See `:help modeline`
-- 下面这一行被称为 `modeline`。查看 `:help modeline`
-- vim: ts=2 sts=2 sw=2 et
```

## 自定义插件

### Tab 页签

```lua
-- tab 页签
return { 'akinsho/bufferline.nvim', version = '*', dependencies = 'nvim-tree/nvim-web-devicons', opts = {} }
```

### 中文格式化

```lua
-- 中文格式化，中英文之间添加空格
-- NOTE: 使用 `:PanguAll` 进行格式化
return { 'hotoo/pangu.vim', ft = { 'markdown' } }
```

### 文件树

```lua
-- Neo-tree is a Neovim plugin to browse the file system
-- Neo-Tree 是一个浏览文件系统的 Neovim 插件
-- https://github.com/nvim-neo-tree/neo-tree.nvim

-- leader [T]oggle [F]ileTree : 开关文件树
-- 文件树内部 `?` 查看帮助

return {
  'nvim-neo-tree/neo-tree.nvim',
  version = '*',
  dependencies = {
    'nvim-lua/plenary.nvim', -- 一个 Neovim 的 Lua 工具库，NeoTree 依赖它提供一些实用函数。
    'nvim-tree/nvim-web-devicons', -- 为文件和文件夹提供图标，虽然不是必需的，但推荐安装以增强界面。
    'MunifTanjim/nui.nvim', -- 一个用于构建用户界面的 Lua 库，NeoTree 用它来创建其界面组件。
  },
  cmd = 'Neotree', -- 将在执行 :Neotree 命令时加载
  keys = {
    { '\\', ':Neotree reveal<CR>', desc = 'NeoTree reveal', silent = true },
  },
  opts = {
    filesystem = {
      window = {
        mappings = {
          ['\\'] = 'close_window',
        },
      },
    },
  },
}
```

### Git 操作

```lua
-- Adds git related signs to the gutter, as well as utilities for managing changes
-- 在 Neovim 中显示 Git 相关的符号（比如行变动、删除、添加等），以及提供多种 Git 操作的快捷方式
-- NOTE: gitsigns is already included in init.lua but contains only the base
-- config. This will add also the recommended keymaps.
-- NOTE: gitsigns 已包含在 init.lua 中，但仅包含基础配置。这还将添加推荐的 keymaps。

return {
  {
    'lewis6991/gitsigns.nvim',
    opts = {
      on_attach = function(bufnr)
        local gitsigns = require 'gitsigns'

        local function map(mode, l, r, opts)
          opts = opts or {}
          opts.buffer = bufnr
          vim.keymap.set(mode, l, r, opts)
        end

        -- Navigation
        -- 跳转到下个更改
        map('n', ']c', function()
          if vim.wo.diff then
            vim.cmd.normal { ']c', bang = true }
          else
            gitsigns.nav_hunk 'next'
          end
        end, { desc = 'Jump to next git [c]hange' })

        -- 跳转到上个更改
        map('n', '[c', function()
          if vim.wo.diff then
            vim.cmd.normal { '[c', bang = true }
          else
            gitsigns.nav_hunk 'prev'
          end
        end, { desc = 'Jump to previous git [c]hange' })

        -- Actions
        -- visual mode
        -- 暂存选中更改
        map('v', '<leader>hs', function()
          gitsigns.stage_hunk { vim.fn.line '.', vim.fn.line 'v' }
        end, { desc = 'git [s]tage hunk' })
        -- 重置选中更改
        map('v', '<leader>hr', function()
          gitsigns.reset_hunk { vim.fn.line '.', vim.fn.line 'v' }
        end, { desc = 'git [r]eset hunk' })

        -- normal mode
        -- 暂存当前更改
        map('n', '<leader>hs', gitsigns.stage_hunk, { desc = 'git [s]tage hunk' })
        -- 重置当前更改
        map('n', '<leader>hr', gitsigns.reset_hunk, { desc = 'git [r]eset hunk' })
        -- 暂存缓存区更改
        map('n', '<leader>hS', gitsigns.stage_buffer, { desc = 'git [S]tage buffer' })
        map('n', '<leader>hu', gitsigns.undo_stage_hunk, { desc = 'git [u]ndo stage hunk' })
        -- 重置缓冲区更改
        map('n', '<leader>hR', gitsigns.reset_buffer, { desc = 'git [R]eset buffer' })
        -- 预览当前更改
        map('n', '<leader>hp', gitsigns.preview_hunk, { desc = 'git [p]review hunk' })
        -- 查看某一行的 Git blame 信息
        map('n', '<leader>hb', gitsigns.blame_line, { desc = 'git [b]lame line' })
        -- 查看文件与索引的差异
        map('n', '<leader>hd', gitsigns.diffthis, { desc = 'git [d]iff against index' })
        -- 查看文件与最后提交的差异
        map('n', '<leader>hD', function()
          gitsigns.diffthis '@'
        end, { desc = 'git [D]iff against last commit' })

        -- Toggles
        -- 切换显示当前行的 blame 信息。
        map('n', '<leader>tb', gitsigns.toggle_current_line_blame, { desc = '[T]oggle git show [b]lame line' })
        -- 切换显示已删除的行。
        map('n', '<leader>tD', gitsigns.toggle_deleted, { desc = '[T]oggle git show [D]eleted' })
      end,
    },
  },
}
```

### 跳转

```lua
-- 快速跳转
-- 按下 `s` 然后输入需要跳转到的位置的单词
return {
  'folke/flash.nvim',
  event = 'VeryLazy',
  ---@type Flash.Config
  opts = {},
  -- stylua: ignore
  keys = {
    { "s", mode = { "n", "x", "o" }, function() require("flash").jump() end, desc = "Flash" },
    { "S", mode = { "n", "x", "o" }, function() require("flash").treesitter() end, desc = "Flash Treesitter" },
    { "r", mode = "o", function() require("flash").remote() end, desc = "Remote Flash" },
    { "R", mode = { "o", "x" }, function() require("flash").treesitter_search() end, desc = "Treesitter Search" },
    { "<c-s>", mode = { "c" }, function() require("flash").toggle() end, desc = "Toggle Flash Search" },
  },
}
```

### Markdown 预览

```lua
-- Markdown 预览
-- :MarkdownPreview
return {
  'iamcco/markdown-preview.nvim',
  build = 'cd app && npm install',
  ft = 'markdown',
  config = function()
    vim.g.mkdp_auto_start = 1
  end,
}
```

### 消息提示

```lua
-- 更好的消息提示，命令输入框
-- 取代 messages, cmdline 和 popupmenu
return {
  'folke/noice.nvim',
  event = 'VeryLazy',
  opts = {
    -- add any options here
  },
  dependencies = {
    -- if you lazy-load any plugin below, make sure to add proper `module="..."` entries
    'MunifTanjim/nui.nvim',
    -- OPTIONAL:
    --   `nvim-notify` is only needed, if you want to use the notification view.
    --   If not available, we use `mini` as the fallback
    -- 'rcarriga/nvim-notify',
  },
}
```

### 状态栏

```lua
-- 更好状态栏
return {
  'nvim-lualine/lualine.nvim',
  dependencies = { 'nvim-tree/nvim-web-devicons' },
  opts = {
    options = {
      theme = 'palenight',
      component_separators = '',
      section_separators = { left = '', right = '' },
    },
    sections = {
      lualine_a = { { 'mode', separator = { left = '' }, right_padding = 2 } },
      lualine_z = {
        { 'location', separator = { right = '' }, left_padding = 2 },
      },
    },
  },
}
```

### 文本替换

```lua
-- 文本替换
-- :Spectre
return {
  'nvim-pack/nvim-spectre',
  event = 'BufRead',
  opts = {},
}

-- vim: ts=2 sts=2 sw=2 et
```

### 翻译

```lua
-- 翻译
-- 选中内容后，leader [T]ranslate
-- NOTE: 弹出窗中 `g?` 查看操作帮助
return {
  'potamides/pantran.nvim',
  config = function()
    local pantran = require 'pantran'
    pantran.setup {
      default_engine = 'google',
      engines = {
        google = {
          fallback = {
            default_source = 'auto',
            default_target = 'zh',
          },
        },
      },
    }

    vim.keymap.set('x', '<leader>t', pantran.motion_translate, { noremap = true, silent = true, expr = true, desc = '[T]ranslate' })
  end,
}
```

### Mini 全家桶

```lua
-- Mini 全家桶
return {
  'echasnovski/mini.nvim',
  config = function()
    -- 可视化显示缩进范围
    require('mini.indentscope').setup()

    -- 自动配对
    require('mini.pairs').setup()

    -- 简单的启动界面
    require('mini.starter').setup()

    -- 小地图
    local map = require 'mini.map'

    map.setup {
      integrations = {
        map.gen_integration.builtin_search(),
        map.gen_integration.gitsigns(),
        map.gen_integration.diagnostic(),
      },
      symbols = {
        encode = map.gen_encode_symbols.dot '4x2',
      },
    }

    -- Leader [T]oggle [M]ap 开关小地图
    vim.keymap.set('n', '<Leader>tm', map.toggle, { desc = '[T]oggle [M]ap' })

    -- 从 mini 的启动页面进入时自动打开小地图
    vim.cmd [[autocmd User MiniStarterOpened
    \ lua vim.keymap.set(
    \   'n',
    \   '<CR>',
    \   '<Cmd>lua MiniStarter.eval_current_item(); MiniMap.open()<CR>',
    \   { buffer = true }
    \ )]]
  end,
}
```

## 其他自定义配置

### 键位

```lua
-- 使用 Shift + j/k 代替 Ctrl + d/u

vim.keymap.set('n', '<S-j>', '<C-d>')
vim.keymap.set('n', '<S-k>', '<C-u>')

return {}
```
