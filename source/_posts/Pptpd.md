---
title: PPTPD
urlname: ngr8zv
date: '2022-01-26 17:30:18 +0800'
tags:
  - Pptpd
  - 服务
  - 计算机
categories:
  - 计算机
  - 服务
  - Linux
---

**安装 PPTP**
sudo apt-get update
sudo apt-get install pptpd
**配置 PPTP**
sudo vim /etc/pptpd.conf——取消掉 connention 行的注释，并根据需要修改内网网关以及地址池
sudo vim /etc/ppp/chap-secrets

```shell
client server secret IPaddresses ---标题
name pptpd password *
用户名 连接方式 密码 指定IP(*即无指定)
```

**设置 DNS 解析**
sudo vim /etc/ppp/pptpd-options
取消掉 ms-dns 行的注释，dns 修改成 8.8.8.8 8.8.4.4
**开启转发功能（必须，否则无法连接外网）**
sudo vim /etc/sysctl.conf————取消掉【net.ipv4.ip_forward=1】的注释
**更新配置**
sudo sysctl -p
**开启 gre 协议并打开服务器 47,1723 号端口**
sudo iptables -A INPUT -p gre -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 1723 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 47 -j ACCEPT
**开启 NAT 转发**
sudo iptables -t nat -A POSTROUTING -s 192.168.88.1/24 -o eno1 -j MASQUERADE
iptables 永久生效
sudo iptables-save
**重启服务生效**
service pptpd restart
