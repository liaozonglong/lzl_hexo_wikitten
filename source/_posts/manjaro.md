---
title: manjaro
urlname: ci5hpm
date: '2022-01-06 09:23:28 +0800'
<br />title: manjaro
tags:
  - manjaro
  - 系统
categories:
  - 计算机
  - 系统
  - Linux
  - manjaro
---

安装后配置：

1. 更换国内源：

sudo pacman-mirrors -c China

---

2. 添加 archlinuxcn 仓库

定义： Arch Linux 中文社区仓库 是由 Arch Linux 中文社区驱动的非官方用户仓库。包含中文用户常用软件、工具、字体/美化包等。
​

命令：sudo vi /etc/pacman.conf

```
在文件下追加
[archlinuxcn]
 SigLevel = Optional TrustedOnly
 Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

参考：

---

3. 更新系统

sudo pacman -Syyu

---

4. 安装 archlinuxcn-keyring

定义： 导入 GPG key  。如果不导入安装某些软件可能会导致 gpg 签名错误损坏等
sudo pacman -S archlinuxcn-keyring

---

5. 安装中文输入法
6. 安装 fcitx（ 小企鹅输入法  ）框架，以及可视化设置

定义： 一个以 GPL 方式发布的输入法框架， 编写它的目是为桌面环境提供一个灵活的输入方案

```
sudo pacman -S fcitx-im #默认全部安装
sudo pacman -S fcitx-configtool
```

2. 安装中文输入法

sudo pacman -S fcitx-googlepinyin
PS: 搜狗拼音在在最新的 manjaro 版本中有很多问题经常崩溃不建议使用，这里推荐使用 fcitx-googlepinyin,你也可以选择 fcitx-sunpinyin
​

3. 新建~/.xprofile 文件，加入如下内容 -- 为 fcitx 添加 X 会话的环境变量

```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS="@im=fcitx"
```

---

6. 更换中文文件夹为英文文件夹

LC*ALL=C xdg-user-dirs-update --force
参考：[XDG user directories (简体中文)](https://wiki.archlinux.org/title/XDG_user_directories*(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
