---
title: AMS云服务
urlname: trliow
date: '2021-10-09 12:00:00 +0800'
tags:
  - AMS云服务
  - 服务
  - 计算机
categories:
  - 计算机
  - 服务
  - 云服务
---

如果您希望使用命令行，请参阅 *AWS Command Line Interface 用户指南*中的以下教程：[通过 AWS CLI 使用 Amazon EC2](https://docs.aws.amazon.com/cli/latest/userguide/cli-using-ec2.html)。

### 密钥对

AWS 使用公有密钥密码术来保护实例的登录信息。Linux 实例没有密码；您可以使用密钥对安全地登录您的实例。使用 SSH 登录时，您在启动实例时指定密钥对的名称，然后提供私有密钥。  
​

## 连接到您的实例

**如果您的本地计算机操作系统是 Linux 或 macOS X**

- [SSH 客户端](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)
- [EC2 Instance Connect](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/Connect-using-EC2-Instance-Connect.html)
- [AWS Systems Manager 会话管理器](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)

**如果您的本地计算机操作系统是 Windows**

- [PuTTY](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/putty.html)
  - **转换你的私有密钥**

PuTTY 自身并不支持适用于 SSH 密钥的私有密钥格式。PuTTY 提供一种名为 PuTTYgen 的工具，该工具可以将密钥转换为 PuTTY 所需的格式。您必须如下所示将私有密钥（.pem 文件）转换为此格式（.ppk 文件），以便使用 PuTTY 连接到您的实例。

1.  从 **Start (开始)** 菜单中，依次选择 **All Programs (所有程序)**、**PuTTY**、**PuTTYgen**。
1.  在 **Type of key to generate** 下，选择 ** RSA**。如果您的 PuTTYgen 版本不包含此选项，请选择 **SSH-2 RSA**。
1.  Load-选择.ppk 密钥文件打开。
1.  如要保存，选择**Save private key 进行保存**

- **连接到您的 Linux 实例**
  - 选项（必选）
    - 连接方式：ssh
    - 端口：22
    - 选择密钥：Connection-->SSH-->Auth-->Browse-->选择并打开-->OPEN（打开连接）
  - 选项（可选）
    - 保持连接：Connection-->Seconds between keepadlives(0 to tum off)输入间隔多久发送一次保持活动数据。
  - 在**主机名**框中，执行以下操作之一：
    1.  （公有 DNS）要使用实例的公有 DNS 名称进行连接，请输入 my-instance-user-name@my-instance-public-dns-name。
    1.  (IPv6) 或者，如果实例具有 IPv6 地址，要使用实例的 IPv6 地址进行连接，请输入 my-instance-user-name@my-instance-IPv6-address
- [SSH 客户端](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)
- [AWS Systems Manager 会话管理器](https://docs.aws.amazon.com/systems-manager/latest/userguide/session-manager.html)
- ​[适用于 Linux 的 Windows 子系统](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/WSL.html)
