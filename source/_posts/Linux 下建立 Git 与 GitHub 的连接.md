---
title: Linux 下建立 Git 与 GitHub 的连接
urlname: qag4zx
date: '2022-01-07 09:44:46 +0800'
tags:
  - linux
  - github
  - git
categories:
  - 计算机
  - 服务
  - Linux
---

1. 安装 git
1. 配置 Git 用户信息：

```
 git config --global user.name "woider"
 git config --global user.email "woider@gmail.com"
```

3. 生成 SSH KEY

```
ssh-keygen -t rsa -C "woider@gmail.com"
```

4. 查看 SSH KEY

```
 root@localhost:~# cd /root/.ssh
 root@localhost:~/.ssh# ls -a
```

5. 复制 SSH KEY 至 GitHub

打开 id_rsa.pub 文件并复制-> 登录 GitHub->打开 Personal settings 页面->选择 SSH and GPG keys 选项->创建并粘贴进去
​

6. 测试 git 连接

```
ssh -T git@github.com                                                    ✔
The authenticity of host 'github.com (20.205.243.166)' can't be established.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes

出现这个提示输入yes
```

1. 安装 hexo

```
sudo npm install hexo-cli -g
sudo npm install --save hexo-deployer-git
sudo npm install
```

2. 安装语雀（可选）

```
npm -g install yuque-hexo
```

3. 克隆或创建项目

```
git clone repo  #复制远程仓库
git init   #初始化本地仓库
```

4. 上传更改

```
git add .  #增加修改内容
git commit -m "<description>"  #对提交的说明
git push origin master   #上传改动
```
