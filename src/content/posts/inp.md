---
title: 零成本内网穿透建站
published: 2025-08-04
description: '使用openfrp进行内网穿透 通过eo反代实现建站'
image: 'https://opreviews.anime-pictures.net/edc/edc9fab3827349e4abc2ace9b27334d5_lp.avif'
tags: [免费,内网穿透,建站]
category: '教程'
draft: false 
lang: ''
---

## 准备工具

- openfrp 链接：[https://console.openfrp.net/](https://console.openfrp.net/)

- 拥有edgeone资格的账户

## 教程开始

### 下载openfrp的桌面应用

登录账户之后 点击：软件下载

根据你的系统 下载专属的系统版本

![](https://cdn.jsdelivr.net/gh/TenKavr/test_gi@main/images/2025-08-04-11-02-42-image.png)

如果你使用的是win版本 我建议使用“CPL跨平台启动器‘

下载后打开安装即可



### 链接本地

首次启动openfrp时 会提示登录 请先登录

接着启动你在本地的项目

然后再次打开openfrp 点击新建隧道

选择中国香港地区 根据你是否开通vip选择适合你的隧道

![](https://youke1.picui.cn/s1/2025/08/04/689025acd1048.png)



隧道名称：随机即可

隧道类型：选择TCP

本地地址：默认即可

本地端口：根据你项目的启动端口填写

远程端口：随机即可

![](https://youke1.picui.cn/s1/2025/08/04/6890263f0fb5d.png)

比如我这里 本地端口为8000

那么我就在openfrp中填写8000



创建过后 点击“管理隧道” 启动你刚才创建的隧道

此时会弹出一个链接 复制它并在浏览器打开 即可见到你在本地部署的网站

现在你可以将链接+端口分享给其他人 他们也可以打开

### 使用EdgeOne反代（主要目的为了绑定域名）

打开eo的域名管理界面点击"添加域名"

![](https://youke1.picui.cn/s1/2025/08/04/689029142f64a.png)

域名配置中正常填写

回源配置中 在源站配置中填写内网穿透后给的域名

回源协议选择HTTP

在回源端口中 填写内网穿透后的域名后面的端口（即远程端口）



点击下一步

根据给出的CNAME 记录正常解析即可



待同步之后 点击HTTPS配置——申请免费证书

后续用户即可通过https协议访问你的网站



## EdgeOne的域名优选

这里我使用的是edgeone.182682.xyz

我这里还推荐二叉树树up的eo.072103.xyz

都是很不错的选择
