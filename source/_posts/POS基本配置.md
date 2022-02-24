---
title: POS基本配置
urlname: vsb3z7
date: '2021-11-17 12:15:52 +0800'
tags:
  - POS基本配置
  - 基本设置
categories:
  - 计算机
  - 软件
  - 丽晶
---

本文涉及工具：
必用

- ​

可不用

- [IP 地址查询工具](https://www.lanzouw.com/iugikv7i9za)——br7p
- [IP 地址扫描 2.0](https://www.lanzouw.com/imP1Wwm9j6d)—— 6hqk

---

正文：

## 第一节：确认需要使用的 IP 地址

### 1. 查询电脑网关地址（等会用于 POS 机设置）

#### 1.1 使用工具

下载[IP 地址查询工具](https://www.lanzouw.com/iugikv7i9za)（密码：br7p）双击运行，即可看到网关地址（以你本机的为准）
![](https://i.loli.net/2021/11/17/AtejbR9PzLFWIhC.png#crop=0&crop=0&crop=1&crop=1&id=hTKhe&originHeight=97&originWidth=324&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)

#### ~~1.2 手动查询~~

---

### 2. 打开“Enhancement”文件夹

在桌面对丽晶程序进行鼠标“**右键**”，单击“**打开文件夹所在的位置**”，找到名为“**Enhancement**”的文件夹，双击打开
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672468570-b6cd6816-da6d-4c23-a9ac-b591725740f6.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=439&id=YDIZ1&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=439&originWidth=1220&originalType=binary∶=1&rotation=0&showTitle=false&size=76860&status=done&style=shadow&taskId=ud2ecb37f-8e23-4392-9155-b303beae6a4&title=&width=1220)

---

### 3. 打开 Pos.lni 文件

在“**Enhancement**” 目录下找到“**Pos.lni**”文件，双击打开

## ![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672478015-2b699769-f52f-43e5-b48b-b4d38d009331.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=281&id=ErQ1p&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=281&originWidth=575&originalType=binary∶=1&rotation=0&showTitle=false&size=28907&status=done&style=none&taskId=u0fe46928-1f91-44c9-aaac-26f6fc8083e&title=&width=575)

---

### 4. 查看 IP 地址（等会用于 POS 机设置）

**分两种情况，请阅读详细\_根据情况执行其中一种**

#### 4.1 情况一：你的电脑以前一直在使用 POS 机

**（适用于机器故障更换新的 POS 机，机器调换等情况）**
​

打开 Pos.lni 文件后，会看到 WIFI 配置段下面有一个 IP=x.x.x.x(**该地址以你本机的为准**)
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633931141310-99f58339-eb58-487a-9008-4ce4ce13f776.png#clientId=u703a5497-4e2d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=537&id=u4217b7a5&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=537&originWidth=504&originalType=binary∶=1&rotation=0&showTitle=false&size=23500&status=done&style=none&taskId=u6a39b657-73b2-423e-902f-7f3b1b246cc&title=&width=504)

#### 4.2 情况二：你的电脑以前从未使用过 POS 机

现可以通过[IP 地址扫描 2.0](https://www.lanzouw.com/imP1Wwm9j6d)（密码：6hqk）来查询可用地址 。

> 程序双击运行，默认敲三次回车，即可出现信息
> 该批处理自行读取网关地址，默认扫描 200-210 的尾数。可自行修改

![](https://i.loli.net/2021/11/18/f2zED6Pda9ouxLk.png#crop=0&crop=0&crop=1&crop=1&id=Rngwf&originHeight=275&originWidth=529&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=)
**丢失 100%即是可用地址，其他均不可用**
​

##### 例：

1.我在我的机器通过查询工具已知 192.168.26.202 为 100%丢失
![](https://i.loli.net/2021/11/18/f2zED6Pda9ouxLk.png#crop=0&crop=0&crop=1&crop=1&id=xwrbE&originHeight=275&originWidth=529&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=none&title=) 3.因此在 Pos.lni 中修改地址为 192.168.26.202（右图）
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633931141310-99f58339-eb58-487a-9008-4ce4ce13f776.png#clientId=u703a5497-4e2d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=361&id=ZOxdB&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=537&originWidth=504&originalType=binary∶=1&rotation=0&showTitle=false&size=23500&status=done&style=none&taskId=u6a39b657-73b2-423e-902f-7f3b1b246cc&title=&width=339)![](https://i.loli.net/2021/11/18/OcxQ13XhP5jM7eV.png#crop=0&crop=0&crop=1&crop=1&height=362&id=h5tmV&originHeight=586&originWidth=561&originalType=binary∶=1&rotation=0&showTitle=false&status=done&style=stroke&title=&width=347)

---

## 第二节：POS 机设置

### 1. 打开设置

1.1 到主界面，通过左滑或右滑切换界面，找到名为“**其他**”的文件夹
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672365443-246114cb-fe7a-49af-b5e4-879401f134e3.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=710&id=TAkD0&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=710&originWidth=434&originalType=binary∶=1&rotation=0&showTitle=false&size=519779&status=done&style=none&taskId=ud38d67fc-ea15-4ab6-8950-fd813019f0e&title=&width=434)
1.2 点开“**设置**”
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672381696-e6313320-ab2d-43e5-8bc5-a4f21081057e.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=716&id=IFGAc&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=716&originWidth=436&originalType=binary∶=1&rotation=0&showTitle=false&size=505593&status=done&style=none&taskId=u696ee2aa-e876-4422-bb61-536732d549a&title=&width=436)

### 2.关闭 WLAN

2.1 点击”**WLAN**”
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672394933-85505bd8-9432-4f8e-b07c-4625a8be1a5f.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=698&id=nj6Ww&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=698&originWidth=422&originalType=binary∶=1&rotation=0&showTitle=false&size=606443&status=done&style=none&taskId=u2c2c0837-aaff-46a5-8b97-d78502276eb&title=&width=422)
2.2 点击**"红框所示意位置"**关闭 WIFI
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672404828-fa64bdc2-7584-4fb4-b3cc-344150b8e335.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=734&id=oscNU&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=734&originWidth=830&originalType=binary∶=1&rotation=0&showTitle=false&size=1022261&status=done&style=none&taskId=u1e13c967-6bab-4ec2-8651-14356cf324a&title=&width=830)

### 3.配置 POS 机 IP 地址

3.1 点击"**有线网络设置"**（红框示意）进入
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672414643-f136a221-289f-413d-adda-cc9f27978885.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=690&id=Y4ZR3&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=690&originWidth=440&originalType=binary∶=1&rotation=0&showTitle=false&size=645550&status=done&style=none&taskId=ucf1b3d54-21a8-4d36-bfdb-186ab695702&title=&width=440)
3.2 点击"**有线网络设置"**（红框）

![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672441759-e9bb04e5-d416-443e-a65e-b8e21a6c7777.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=702&id=rL7bH&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=702&originWidth=411&originalType=binary∶=1&rotation=0&showTitle=false&size=491877&status=done&style=none&taskId=ub4601623-b834-493a-9fc5-b4adf717b6d&title=&width=411)

#### 3.3 IP 配置

3.3.1 选择“**静态 IP**”（红框 1）
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672452634-308e9634-c689-4b86-acce-d93726b298db.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=688&id=bLRRR&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=688&originWidth=435&originalType=binary∶=1&rotation=0&showTitle=false&size=566192&status=done&style=none&taskId=u9730e0ef-32dc-4f53-85c9-1900301b540&title=&width=435)

##### 3.3.2 输入 IP 地址至 POS 机（红框 2）。

PS: IP 地址为本文第一节第 2 段，所涉及的 Pos.lni 文件中的 IP 地址，将其输入至 POS 机中**（红框 2）（以你的机器的配置文件为准，图仅供参考）**
![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633931141310-99f58339-eb58-487a-9008-4ce4ce13f776.png#clientId=u703a5497-4e2d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=320&id=ZXUwN&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=537&originWidth=504&originalType=binary∶=1&rotation=0&showTitle=false&size=23500&status=done&style=none&taskId=u6a39b657-73b2-423e-902f-7f3b1b246cc&title=&width=300)![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672452634-308e9634-c689-4b86-acce-d93726b298db.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=392&id=svdCe&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=688&originWidth=435&originalType=binary∶=1&rotation=0&showTitle=false&size=566192&status=done&style=none&taskId=u9730e0ef-32dc-4f53-85c9-1900301b540&title=&width=248)

##### 3.3.3 设置网关与 DNS

在“设置有线网络”的界面继续下滑，看到 DNS 与网关的数字，对应输入（**以你得机器的地址为准，图仅供参考**）

###### PS: 网关的查询在第一节第 4 段

![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633931400626-a645b84e-ee07-4d0d-8a2a-4ce1fd744abc.png#clientId=u703a5497-4e2d-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=97&id=dCpSE&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=97&originWidth=324&originalType=binary∶=1&rotation=0&showTitle=false&size=2682&status=done&style=none&taskId=u8a4ba0e8-f53c-45be-87b1-52a576828a3&title=&width=324)![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633941987817-e3445e7a-93e7-406e-a79a-73f114c89d12.png#clientId=u89b6bd2e-d322-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=312&id=u775a654d&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=312&originWidth=248&originalType=binary∶=1&rotation=0&showTitle=false&size=168531&status=done&style=none&taskId=ub03014ab-79f1-4ac7-bda1-a3fe821a21d&title=&width=248)

##### 3.4 返回至桌面，通过左右滑动找到银商 MIS，点击进入，并将银商 MIS 保持全部关闭状态

![图片.png](https://cdn.nlark.com/yuque/0/2021/png/22295732/1633672531309-adf54ac4-4e65-4935-b3bc-e4ad8f4e85f7.png#clientId=uffecab00-a1a0-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=656&id=u971b3d27&margin=%5Bobject%20Object%5D&name=%E5%9B%BE%E7%89%87.png&originHeight=656&originWidth=388&originalType=binary∶=1&rotation=0&showTitle=false&size=402017&status=done&style=none&taskId=ubb0b018b-cb34-455d-a10b-51344d5e34b&title=&width=388)

---

至此设置完成，请自行进行签到测试
