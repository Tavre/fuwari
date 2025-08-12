---
title: 使用腾讯CNB构建属于你的AI绘画
published: 2025-08-12
description: '使用cnb平台构建AI绘画 纯白嫖'
image: 'https://img.alicdn.com/imgextra/i1/O1CN01EkVkR91kxYOYdWMvL_!!2215879134750-0-fleamarket.jpg'
tags: [AI绘画,教程,cnb,免费云计算,H100]
category: '教程'
draft: false 
lang: ''
---

# 介绍

**腾讯云 CNB（Cloud Native Build，云原生构建）** 是一款由腾讯云推出的云原生开发平台，旨在为开发者提供一站式的开发环境。通过 CNB，开发者无需安装繁琐的软件配置，仅需一个浏览器即可完成从代码编写到应用构建的全过程。

CNB 基于 **Docker 生态**，对环境、缓存和插件进行了抽象，采用声明式语法，帮助开发者以更高效的方式构建软件。它支持代码托管、云原生构建、云原生开发、AI 代码助手以及制品库等功能

# 准备工具

1. 一个聪明的脑子

2. 一台能打开浏览器的电脑

3. 一个微信号

# 教程开始

## CNB平台部署

打开[https://cnb.cool](https://cnb.cool)

首次访问未登录 点击右上角 登录

![](https://img.alicdn.com/imgextra/i2/O1CN01rkj1Ew1kxYOX3w7Hp_!!2215879134750-49-fleamarket.webp)



登录之后 点击下方仓库链接

[CNB仓库](https://cnb.cool/beilinmo/SD-WebUI_ForgeUI-EasyJoy)

点击"Fork"按钮

![](https://img.alicdn.com/imgextra/i2/O1CN01B5qA7H1kxYOX3tyGK_!!2215879134750-49-fleamarket.webp)

此时会弹出对话框 新用户不会有“所属组织” 你自己创建一个即可

![](https://img.alicdn.com/imgextra/i2/O1CN01BjSqPy1kxYOZlXlvc_!!2215879134750-49-fleamarket.webp)

继续点击“Fork”按钮

此时会跳转到我们fork下来的仓库 点击右上角“启动”

![](https://img.alicdn.com/imgextra/i3/O1CN01RRcygn1kxYOZAn5Gn_!!2215879134750-49-fleamarket.webp)

等待即可 等构建完成会出现以下图片内容

![](https://img.alicdn.com/imgextra/i4/O1CN01L4hBVF1kxYOSi2OyW_!!2215879134750-49-fleamarket.webp)

点击使用WebIDE打开

首次进入会在终端加载命令 等待加载成功

输入下方的命令

```
bash /workspace/res/启动Forge.sh
```

等待一会 会在终端出现以下内容

![](https://img.alicdn.com/imgextra/i2/O1CN012zTtbR1kxYOZlZ75O_!!2215879134750-49-fleamarket.webp)

此时点击哪一个 都可以进入webui 这样我们就可以开始作图了！



## 模型下载

在终端点击右上角的“+”号

![](https://img.alicdn.com/imgextra/i3/O1CN0166A4mj1kxYOSi0K4B_!!2215879134750-49-fleamarket.webp)

输入以下命令

```
cd /workspace/models/Stable-diffusion
```

使用wget命令下载模型即可

例如在终端输入：

```
wget https://liblibai-online.liblib.cloud/web/model/d2e30dc822bb4359b74f93cb5e455e32/95878f817cc37c557013662341ca02b991e4ff04ae33719345fd09cb1d22923a.safetensors?auth_key=1755001041-48f1855bde32408b8f44b20903dd46c2-0-50588881ea7c9dd48e9fdd47fa8dd4ac&attname=potion%20pot%E4%B8%A8%E7%81%B5%E8%8D%AF%E9%94%85_3.0.safetensors
```



下载完成后 在webui的右上角 模型选择的右边 点击刷新 再进行模型选择即可显示你下载的模型



# 声明

仅供学习交流，严禁用于商业用途，严禁违规违法犯罪行为，自行承担责任



如有版权问题 请联系tavre@qq.com 我将在收到邮件后第一时间删除该文章
