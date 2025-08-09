---
title: 使用浏览器脚本 半自动刷课
published: 2025-08-08
description: '通过浏览器脚本 实现升学e网通半自动刷课 挂机即可'
image: 'http://cn-qz-plc-1.ofalias.net:50910/images/689775704f882_1754756464.webp'
tags: [升学e网通,挂机,脚本,油猴]
category: '教程'
draft: false 
lang: ''
---

# 声明

仅供学习交流，严禁用于商业用途，一切风险皆由用户承担



# 前言

老子也是没得喷 nm放个假还得被这78升学e网通硬控两个小时

一整天有事 晚上回来一看天塌了 一节课没听 78老师和组长还在群里发完播率

经过我大晚上不断的调试 也是成功写出浏览器脚本 只要打开视频界面 然后挂机即可



# 介绍

## 脚本名称：Fuck for ewt

## 脚本功能：自动切换视频、自动打开二倍速、自动点击随机检查

<code>Tips：部分课程会有选择题 不管即可 1分钟后自动跳过 视频结束后也算已完成</code>



# 源代码

```javascript
// ==UserScript==
// @name         fuck for ewt
// @namespace    http://tampermonkey.net/
// @version      1.2.0
// @description  支持视频自动切换、自动确认随机弹出的检测点、自动2倍速播放
// @author       Tavre
// @match        https://*.ewt360.com/*
// @license      MIT
// @icon         https://th.bing.com/th?id=ODLS.8f71fab6-d8fc-43f3-a56d-53f87a14d5c8&amp;w=32&amp;h=32&amp;qlt=90&amp;pcl=fffffa&amp;o=6&amp;pid=1.2
// @grant        none
// ==/UserScript==

(function() {
    'use strict';
    const MaxTryNum = 3;

    let modal = null;
    let titleBar = null;
    let messageList = null;

    let DraggableModalTitle = "fuck for ewt"

    function Wait(ms)
    {
        return new Promise(resolve => setTimeout(resolve, ms));
    }

    function GetCheckButton()
    {
        let button = document.querySelector('span[class="btn-3LStS"]');
        return button;
    }


    function GetTitle()
    {
        let titleText = document.querySelector('div[class="title-1dNOi"]');
        //return new String(titleDiv.textContent);

        let text = '';
        // 遍历元素的所有子节点
        Array.from(titleText.childNodes).forEach(node => {
        // 检查节点类型
            if (node.nodeType === Node.TEXT_NODE) {
                text += node.textContent.trim();
            }
        });
        return text;

    }

    async function GetVideoList()
    {
        addMessage("开始获取视频列表!");
        let divVideoList = document.querySelector('div[class="listCon-N9Rlm"]');
        for(let cnt = 1;divVideoList == null && cnt <= MaxTryNum; cnt++)
        {
             divVideoList = document.querySelector('div[class="listCon-N9Rlm"]');
             addMessage("尝试获取失败,重试中!");
            await Wait(1000);
        }

        let videoList = divVideoList.children;

        if(videoList != null)
        {
            addMessage("获取视频列表成功！");
            return videoList;
        }
        else
        {
            addMessage("获取视频列表失败！");
            return null;
        }
    }

    async function CatchVideo()
    {
        let video = document.querySelector('video[class="vjs-tech"]');
        //let video = document.querySelector('video[id="vjs_video_3_html5_api"]');
        for(let cnt = 1;video == null && cnt <= MaxTryNum; cnt++)
        {
            video = document.querySelector('video[class="vjs-tech"]');
            //video = document.querySelector('video[id="vjs_video_3_html5_api"]');
            addMessage("尝试获取video失败,重试中!");

            await Wait(1000);
        }

        if(video != null)
        {
            addMessage("获取video成功!");

            // 设置视频播放速度为2倍速
            try {
                video.playbackRate = 2.0;
                addMessage("已设置视频为2倍速播放!");
            } catch (error) {
                addMessage("设置2倍速失败: " + error.message);
            }
        }
        else
        {
            addMessage("获取video失败!");
        }

        return video;
    }

     async function Next(title)
    {
        await Wait(3000);

        let videoList = await GetVideoList();

        addMessage(title);
        for(let i = 0; i < videoList.length - 1; i++)
        {
            let div = videoList[i];
            let divTitle = div.querySelector('div[class="lessontitle-x9B-7"]').textContent;
            addMessage(divTitle);
            if(divTitle == title)
            {
                if(i >= videoList.length - 2)
                {
                    addMessage("已经到结尾!");
                    return;
                }
                addMessage("切换到下一个视频");
                videoList[i + 1].click();
            }
        }

    }

    async function Loading()
    {
        await Wait(2000);
        //let videoList = await GetVideoList();
        let title = "hello_world";
        // 使用函数来显示悬浮窗
        createDraggableModal();
        addMessage("加载中!");

        while(1)
        {
            await Wait(1000);

            // 通过通过实时获取标题来检测视频是否切换!
            let newTitle = GetTitle();
            if(title !== newTitle)
            {
                addMessage("检测到视频切换!");
                title = newTitle;

                await Wait(1000);
                let video = await CatchVideo();

                // 监听视频播放事件，确保2倍速设置生效
                video.addEventListener('play', () => {
                    setTimeout(() => {
                        if(video.playbackRate !== 2.0) {
                            video.playbackRate = 2.0;
                            addMessage("重新设置视频为2倍速播放!");
                        }
                    }, 500); // 延迟500ms确保视频开始播放
                });

                video.addEventListener('ended', async () => {
                    addMessage(" 准备切换视频!");
                    await Next(title);
                });
            }

            let checkButton = GetCheckButton();
            if(checkButton != null)
            {
                addMessage("找到检测按钮！");
                checkButton.click();
            }

        }

    }


        // 创建一个函数来生成悬浮窗
    function createDraggableModal()
    {
        // 模态框容器
        modal = document.createElement('div');
        modal.id = 'draggableModal';
        modal.style.position = 'fixed';
        modal.style.top = '50px'; // 初始位置
        modal.style.left = '50px';
        modal.style.width = '350px';
        modal.style.height = '350px';
        modal.style.backgroundColor = '#fff';
        modal.style.border = '1px solid #ccc';
        modal.style.boxShadow = '0 2px 10px rgba(0, 0, 0, 0.1)';
        modal.style.zIndex = '1000';
        modal.style.overflow = 'hidden'; // 隐藏溢出内容
        modal.style.resize = 'both'; // 允许调整大小（可选，但此处为演示目的）
        modal.style.userSelect = 'none'; // 禁止文本选择'
        modal.style.resize = 'none';

        // 消息列表容器
        messageList = document.createElement('div');
        messageList.style.height = '300px'; // 固定高度
        messageList.style.overflowY = 'auto'; // 垂直滚动条
        messageList.style.padding = '10px';
        messageList.style.borderBottom = '1px solid #ccc'; // 底部边框分隔

        // 标题栏（用于拖动）
        titleBar = document.createElement('div');
        titleBar.style.backgroundColor = '#f0f0f0';
        titleBar.style.padding = '10px';
        titleBar.style.cursor = 'move';
        titleBar.textContent = DraggableModalTitle;

        // 将元素组合起来
        modal.appendChild(titleBar);
        modal.appendChild(messageList);

        // 将模态框添加到body元素的末尾
        document.body.appendChild(modal);

        // 拖动逻辑
        var isDragging = false;
        var offsetX, offsetY;

        titleBar.addEventListener('mousedown', function(e) {
            isDragging = true;
            offsetX = e.clientX - modal.offsetLeft;
            offsetY = e.clientY - modal.offsetTop;
            document.addEventListener('mousemove', onMouseMove);
            document.addEventListener('mouseup', onMouseUp);
        });

        function onMouseMove(e) {
            if (isDragging) {
                modal.style.left = (e.clientX - offsetX) + 'px';
                modal.style.top = (e.clientY - offsetY) + 'px';
            }
        }

        function onMouseUp() {
            isDragging = false;
            document.removeEventListener('mousemove', onMouseMove);
            document.removeEventListener('mouseup', onMouseUp);
        }
    }

    function addMessage(msg)
    {
        var message = document.createElement('div');
        message.textContent = msg;
        message.style.marginBottom = '5px';
        messageList.appendChild(message);
    }

    window.onload = Loading;

})();
```

# 使用方法

## 下载油猴

打开官网：[点我跳转](https://www.tampermonkey.net/)

根据提示进行安装



## 安装插件

点击油猴插件

![](http://cn-qz-plc-1.ofalias.net:50910/images/6897748c1b91a_1754756236.webp)

点击添加新脚本

再将博客上方的源代码复制粘贴到新建脚本中（提前将默认脚本的代码删除）

在油猴中启用即可

## 升学e网通流程

登录升学e网通 打开视频界面

当出现弹窗时 则证明程序已启动

![](http://cn-qz-plc-1.ofalias.net:50910/images/6897748c3dc50_1754756236.webp)

那你就可以愉快的挂机了！！！



# 结尾

多提一嘴 nmd放假还上网课 有鸡毛用 全校有50个人认真听就不错了
