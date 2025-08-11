---

title: 使用百度飞浆 部署你的在线AI绘画
published: 2025-08-04
description: '自建一个云端无限制的SD WebUI 小白也能轻松上手'
image: 'https://v1-cp.ssrcdn.com/ksc2/Jez7ZRzPJxUBTHe0_AZBXpX9tJQTe7p8Mizj95paEj7LQSD_dL0za912x0d-VZH3rN4FdyxcKkyqyERUnEJD1OTONhvS8CQ5QOLnvcyEm-5UiAJU3XZcu7CHuSxVyCl4.webp?pkey=AAU6C2jvCnMKVJIpf-mWKpFIt_cdxIAtZFl2_L2imUqDuRSPm-3aw1b-T1ty9M4OZYnmuMJXcQw_9KC5cbwUAG9XwHGO1e24C0cPjvrzld_I5xH4o1hs2CbHtqvzDrhn9QY'
tags: [AI绘画, 白嫖, 云算力,飞浆, 教程,免费]
category: '教程'
draft: false 
lang: ''

---

# 使用百度飞浆 部署你的在线AI绘画

<code>下午打完游戏 仔细想了想我的AI绘画 有近乎一半的时间都在报错 不如我发一篇个人部署的教程 还节省我的成本</code>

## 视频教程：[【AI云端绘画部署】]( https://www.bilibili.com/video/BV1Xvhpz1EVL/?share_source=copy_web&vd_source=19b7567484d13fc8d2b31e49c75bf934)

## 文字教程开始

打开[飞桨AI Studio星河社区-人工智能学习与实训社区](https://aistudio.baidu.com/index)

点击右上角“登录”按钮

![](https://v1-cp.ssrcdn.com/ksc2/9rTPQX6q61YRTVdneZsu6a_rizp0cn9Lgf4LECIiS_e6b4WWt9vIt6kO3AAF4oR6eCH7140kFn3TOCxcMC5zL6MlrMzOjDqLMn6naPwtAPAAboqp36wEm_AW7ZxICsEh.png?pkey=AAUFaFgpB9H-86EuwFQZe2cRiEHRpXaNfpgQkBGUyMVJ7sqRVEcdccU97rqqCBcKbsmvOWs9AKFqpqiV05G8DSLqDIfcpgNaJxDvpYd5IE5jvMyVfoVedOt2KIQVBEkCIg8)

使用百度账户登录即可 然后我们点击下方链接

[Stable Diffusion WebUI 在线体验 - 飞桨AI Studio星河社区](https://aistudio.baidu.com/projectdetail/7640442?channel=0&channelType=0&sUid=16990041&shared=1&ts=1754043924938)

 紧接着点击右上角“运行一下”

![](https://v1-cp.ssrcdn.com/ksc2/t3Kfoid4zOZNNGRPY8j_mS4EqBx2rWXjNld-B-fd6hKbKfEa8xiT2Y1AbuCn1tqNOnTgzm4zckAovq0hE-Nbqo8VRAgaMudrltzL_JPM2ZBllxIL6chAOjz7V76kkB24.png?pkey=AAWO0E1vzf9-N0W-Sb33acquxLr5tjtgaqTF-6npKJPITjNc8YX3V6hzCt1_EkW4QWF1ykTWHbr0QgfVVnBtib-TLFF5_tZXPWl6S4W5Tz4WrvMiQUAcQFKbaKYU6J4iniU)

紧接着点击“创建”

![](https://v1-cp.ssrcdn.com/ksc2/wCL7r3pUGJhZ-B32Ko53rJfA-eftLsYIO9nknQmmGNYXhnxWkWaWS5CXJhYX7HRJ94vqunUzpGCxnxgkJ4Gj8BWPG_2JjPACOdJMmmAQ0W7vwTyGiHy6ByCAxORESPov.png?pkey=AAVuL_V3Br718Q2ABMlC8QtxUkt5ErP7CxWUZS2PXZJon88X6yStZa4ScDAg6cySLimD4TO2Rh6SbTlPsufoh-LxAaT7WeAnhwqw16j5Cl4hBjPF-R9AZuDjuX4MmQpTFnA)

然后再次点击右上角“专业开发”

![](https://v1-cp.ssrcdn.com/ksc2/5MnoIArWNkm6riPWHTPNUgUhWtnfX6QIHDUiqupcqH2swQ1VlLg7aUC5WY-aBJ6qEOoIJum7cHWfOhVDcnyxTSdi99_8Q4E9uQFoFNMzBL34kvlf6wkM3euKz66SJ2bM.png?pkey=AAVZZYnKRVQsFiJUG9W5bowut63vZxkSFEPOjOeL8XZZCzQE_VV4h2JvwJh9bcQK8bbn9tV0-F3zSNOTDzmUsTcA-KKytPt9yQlMlzjUAUsHjLDHSeJ5Z6UipcVTZaZpgg4)

![](https://v1-cp.ssrcdn.com/ksc2/65jgORVtqS-g301MZycZolLXaxc9kbGTiRz_j7cNF-Ugv2CRa6ILgyUwU3isI3GoQxNsfR3umlYK7LdHqU2AYfQArIdkYBkwpctBtWlFO_6mfZy3gJrgnUx6IcYriqTK.png?pkey=AAVSAYRW5Cju7OiNu5wIvGu0z7rarXFg14dIPwnAiGon4S22jcsUtu04Fs60LAfj2RD05eie2pWH-VLpBTDwz_icCMIEsoAUZe2eA3kr68xKhb-BP6qMwFM5IEkHt6Dadj0)

这里的配置 选择V100的16G或32G **不要使用CPU（即基础版）**！ 否则你可能会遇到各种奇奇怪怪的问题

> 点数怎么获取呢 完善个人资料 会赠送你一些点数 然后通过一些任务 也会赠送你一些点数
> 
> 或者直接金钱解决问题 (呜呜呜 我恨有钱人）

进入到页面之后 根据图片提示双击文件![](https://v1-cp.ssrcdn.com/ksc2/xyGX_lMqgS44crlavjbAc5Nkr9SwzGjgJF5HKj3Rw0l8wfaqal-648Dnvq7XgAifBLLoBkc0xDhdq-VbJ9d5-bTRDqUWU_Hv9TJ6U-esw63vwTJCP1GPo7cQ2m24CKVu.png?pkey=AAUELu98UQTrRQuVlRXuPXGsI0jp9Re3d0cLrDTYrVhLj7dDx8P4-kASVldOYUkTj_3CRsdRnZOlC50BF-BSa_ltQFIeIgO13LOeOUHRI4tYuTiEQnBy6Cv-SVhjfk8Ohvo)

这里右边加载会等待5分钟左右 请耐心等待

接下来根据图片提示 按步骤操作

![](https://v2-cp.ssscdn.com/ksc2/p7rp-YzT2oERKdfh1wVcRxl-RRhqc0xbct5e-6gzE-weUAwbVWkXaitZcBeN2J0WDkScR6IA0mY0m3gfELPP7jAfVFdDq4HoLl-YXc6hFDCmOkXUltn4zPpqmeHxnTYo.png?pkey=AAVFXRaZAUy_gusD-itXrsRuk5TkJpYwX1Y51MRcgsW86o1jHE85AEuAG6BeOeWh7ZtL9Ut16DuCsoy34UiBL-fuZmf4N9UGhQxtdUlLrjZ03ROfwZgeO7DOk8hu8jZo44Y)

![](https://v1-cp.ssrcdn.com/ksc2/TydWT_ww2WhU0cu9bQgbnvPIAZqjTCJDHG3JhAZUxEIMCYCfw2se3UigtJljHvgqPwYmr6HPyh56alX89yjBD8B70vZRtfRb0TjDEIQmFgqbL7GyiEKhRNYJosg8SvBd.png?pkey=AAUr9fyH-WTInHqq_V9SR1LbWDQ3jIMPm2wdolNu-OIIszVKGpQRjPhVlHXztBLZfSKp8Df30GHeY81mAC9PpvJX64p3ZiBzlFBv5KPHsAI4KiDEC_Cg5GzrNhMnZEGeTks)

点击“激活端口” 然后复制命令 再点击中上区域的“+”

紧接着 选择“终端”

![](https://v2-cp.ssscdn.com/ksc2/NmbNCIU3aL_lrUNWi_QFmTtMk0_p2Md9H2GUfobGRqaTZbN8SzMsFDG1LxoN0QAdCK4qMbrLlHexAQiVFSyBplpioqHOGPFmE6Y4m9TwjEkE99I0GoiqOUY7ZmyW8MUY.png?pkey=AAVqfCFrjtSfQOUTtPlMfos-AGAL7X7gDxHyvfj2YnycOGT0wSnWp3z-UUlyU2H0nW6sApcRDVjcQi53iPYfJPO5aB85uOtdiXznfolPecflfPYkflwyq-DkUkvonOHuD9s)

将我们复制的命令粘贴进去 不一会 即可在终端中看到外部链接

![](https://v1-cp.ssrcdn.com/ksc2/AVKgAiWDnwJXRhENjPXBR4BOtKmw-8TzycXJd9MQn7QoArJmnljlP7hqxHynnUxDeevA4WbPOkbJicpX4YNbDoKmZw7fkNw69NE1qm7emZrKv1TB2hjmSHKGWUoe1UaG.png?pkey=AAXCRjCa_VfzQ2cGoBOVrPvI5_Yt4HzET4jzyHqxR-F_2EkyjN74DOelzS6Vv0jBcFd41_nffprTWGylgXrw8yZN_dZeeGc52TOXU8GcFi0ZONvicz1RLjrHccy_G-i_jJc)

我们访问 即使sd webui画面 现在就可以开始你的创作了！

![](https://v1-cp.ssrcdn.com/ksc2/s9hoGPy6ClwmOuNbjQdqS6PNpxbVwhy-PF_e8lFTpirpT1m-otPLlwH8DzDBTSpjc-5XA8NdgR_GrkswCwfqRi0-H4gYEsCJ4pz6IbFYXB82KVPhC6EptNEh0NQBN4XJ.png?pkey=AAXDG_S1INCzevs2PWtAVj2IRzKdmEcCgLT-2M151hgzkDqNbSnCc33n2G2Mme6Sp5Z_FhAGOI_9YVoyxPRlHz-QWS1QzpizCtvBecjHqRmdWJ2i5zE_mz_ZJvNZ--fDHAo)

## 自定义模型

回到我们启动webui的页面

![](https://v1-cp.ssrcdn.com/ksc2/NiZ41Hw46MqbSkJTpm8k_xq50GZrdKGV_Hq_GZZZs0uX-Y7cZjiQCQs9KbO1icvTc7-CTuRgPQ49lTg4wwaWypQI6aAFHZvCLb66rC3C3AoGMJggCDy5kYA_8JgabJ-E.png?pkey=AAUnpGVio7xTU-6sIENpPR-b86mCmLW3iZoRCQFFQuuiErSnn4DlyAUM_XrpAHNEAr1TVDN1XlsyUrsb3UPWPUnw-QFXUGkQl2B_UyqOJdqjZBcoPONvLMGKmzONweLuQ50)

根据图片提示 点击对应的对话框

在下载链接内填入C站模型下载链接 点击“开始下载” 即可下载并使用模型

C站链接：[civitai—国外知名大模型平台](https://civitai.com/)

## 声明

本项目作者——[旭_1994](https://aistudio.baidu.com/personalcenter/thirdview/9044961)\
项目地址——[Stable Diffusion WebUI 在线体验](https://aistudio.baidu.com/projectdetail/7640442)

本教程仅供学习和研究使用 任何风险都由用户承担