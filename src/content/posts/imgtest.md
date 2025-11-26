---
title: 图床测试
published: 2025-10-20
description: '本篇用于测试我的图床接口图片链接是否设置防盗链'
image: 'https://tiebapic.baidu.com/tieba/pic/item/810a19d8bc3eb135f01d27ace01ea8d3fc1f44cb.jpg?tbpicau=2025-10-22-05_b7c5a745e1cc72fd90817239cc14f1d9'
tags: [图床,技术,大厂]
category: '技术'
draft: false 
lang: ''
---

# T-XY图床

一个收集各大厂的图片接口的图床 用于全球加速的cdn 让您的图片快人一步加载！

GITHUB地址：[Tavre/goofish_img: 一个使用“闲鱼创作者平台”接口 编写的自用图床](https://github.com/Tavre/goofish_img)

## 百度接口

废

## 闲鱼接口

![](https://img.alicdn.com/imgextra/i4/O1CN01kaT5Sc1kxYPWnA9FR_!!2215879134750-0-fleamarket.jpg)

![](https://img.alicdn.com/imgextra/i4/O1CN01xtaJLj1kxYPVvJ2qB_!!2215879134750-0-fleamarket.jpg)

![](https://img.alicdn.com/imgextra/i4/O1CN016MZ1fP1kxYPWnDuKd_!!2215879134750-2-fleamarket.png)

## 葫芦侠图床

葫芦侠有防盗链  解决办法：

在</head>上添加一行这个代码: <meta name="referrer" content="never">

<head>
<meta name="referrer" content="never">
</head>
<body>
<img src="http://cdn.u1.huluxia.com/g4/M02/05/32/rBAAdmknItuAF3AZAAGbHpyMYBA982.jpg">
<img src="http://cdn.u1.huluxia.com/g4/M02/05/32/rBAAdmknItuAd_bsAALfS8nCFm8327.jpg">
<img src="http://cdn.u1.huluxia.com/g4/M02/05/32/rBAAdmknItqAO2CTAAmLDD9UA48650.jpg">
</body>
