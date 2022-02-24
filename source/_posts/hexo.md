---
title: hexo
urlname: tqem87
date: '2022-02-18 13:16:39 +0800'
tags:
  - ​
categories:
  - 计算机
  - 服务
  - 框架
  - hexo
---

1. install nodejs npm Git yay

```shell
pacman -S yay
yay -S nodejs npm
npm install -g hexo-cli
```

2. station construction

```shell
hexo init
git clone https://github.com/zthxxx/hexo-theme-Wikitten.git themes/Wikitten

##overwrite default page
cp -rf themes/Wikitten/_source/* source/
cp -rf themes/Wikitten/_scaffolds/* scaffolds/

##set profile
cp -f themes/Wikitten/_config.yml.example themes/Wikitten/_config.yml
vim themes/Wikitten/_config.yml
```

3. yuque

```shell
YUQUE_TOKEN="$YUQUE_TOKEN" yuque-hexo sync
```

​

​
