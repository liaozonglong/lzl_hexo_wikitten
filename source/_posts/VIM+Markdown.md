---
title: VIM
urlname: swahiv
date: '2022-01-06 11:00:36 +0800'
tags:
  - VIM
  - Markdown
  - 计算机
  - 计算机语言
categories:
  - 计算机
  - 计算机语言
  - VIM
---

1. 安装 vim 的**插件管理器 vundle**
   Vundle 是 Vim 的插件管理器，官方 Github 地址是：[Vundle](https://link.jianshu.com?t=https://github.com/VundleVim/Vundle.vim)

git clone [https://github.com/VundleVim/Vundle.vim.git](https://github.com/VundleVim/Vundle.vim.git) ~/.vim/bundle/Vundle.vim

2. 编写 vimrc   文件(vundle 配置文件)

路径：~/.vimrc (若无，自行创建)

```
set nocompatible    " be iMproved, required
filetype off " required

" 启用vundle来管理vim插件
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" 安装插件写在这之后

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" 安装插件写在这之前
call vundle#end() " required
filetype plugin on

" required" 常用命令
" :PluginList - 查看已经安装的插件
" :PluginInstall - 安装插件
" :PluginUpdate - 更新插件
" :PluginSearch - 搜索插件，例如 :PluginSearch xml就能搜到xml相关的插件
" :PluginClean - 删除插件，把安装插件对应行删除，然后执行这个命令即可

" h: vundle - 获取帮助
```

保存退出，使用 sudo vim。
再使用“:PluginInstall”安装插件。出现“done”即安装完成，按 q 退出

3. 安装 vim-markdown 插件

```
该代码输入至vimrc 文件中的"安装插件写在这之后"和安“装插件写在这之前”之间。并再次运行“:PluginInstall”安装插件
Plugin 'godlygeek/tabular'
Plugin 'plasticboy/vim-markdown'
```

4. 安装 node.js

```
pacman -S yay
yay nodejs-lts   #选择最新的
yay -S npm
```

5. 实时预览插件:vim-instant-markdown

sudo npm -g install instant-markdown-d

6. 添加插件至 vimrc 文件 ，然后保存并安装插件

Plugin 'suan/vim-instant-markdown'

7. 重启之后，编写 md 文件，即自动跳出浏览器实时预览
