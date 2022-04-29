---
title: hexo怎么多台电脑同步更新(傻瓜式)
abbrlink: 63977
categories:
  - Notes
  - hexo
tags: hexo
description: 博客怎么多设备同步更新
date: 2022-04-19 21:44:39
password:
abstract:
message:
---
大家都知道我们的hexo博客配置文件以及都在本地,如果我们手头没有平时写博客的那台电脑,我们就没办法在其他电脑上更新博客,那么百度也是有解决方案,比如在github创建分支/云环境等等,操作都挺繁琐的,我们其实可以通过云盘来实现多设备同步更新.
此方案也可以有效防止硬盘暴毙,相当深刻的教训
---

>环境都以经安装完成,[安装方法](https://imgod.me/posts/39317.html)
**[nodejs](https://nodejs.org/zh-cn/)** **[git](https://git-scm.com/)** **[hexo](https://hexo.io/zh-cn/)**

#### 选择云盘

没有特别的要求,能够挂载到本地同步文件就可以,我最开始用的华为云空间,软件问题蛮多的,所以我改用OneDrive,只要有微软账户我们就可以免费用5g的空间,对于博客来说完全够用.

#### hexo初始化
1. 登录网盘账户
![](https://s2.loli.net/2022/04/19/fhUF85ng9Wzquxb.png)

2. 设置OneDrive文件夹,这里我直接设置为d盘
![](https://s2.loli.net/2022/04/19/ATsoR7v5xdDOwtf.png)

3. 在OneDrive文件夹下新建一个博客文件夹,随意命名,并右键设置属性为<code>始终保留在此设备上</code>
![](https://s2.loli.net/2022/04/19/WX6eLudv7Y5bK2p.png)

4. 进入文件夹并初始化hexo
![](https://s2.loli.net/2022/04/19/JpvdaIz5rwGm1bj.png)
    >这里容易报错,如果提示"npm install",就去<code>C:\Users\你的windows用户名</code>文件夹下删掉 **.npmrc** 文件,重新初始化
    ![](https://s2.loli.net/2022/04/19/zNvTWcLFpwJBgf4.png)

5. 安装 hexo-deplayer-git 依赖
```
npm install hexo-deployer-git --save
```

5. 将旧blog文件夹下的文件复制过来
   ![](https://s2.loli.net/2022/04/19/3YcBG8htJrbFNPg.png)

6. 重新安装插件(本来图片插件是需要修改才能用的,意外的发现,安装以后可以直接使用了,不会再出现路径问题)
   ![](https://s2.loli.net/2022/04/19/vdqwrQlbG2XEZeJ.png)

**到这就已经安装完成**
如果需要在其他设备上安装只需要安装hexo环境,在云盘文件夹下初始化,替换文件即可(初始化请先把文件导出然后再覆盖)
更新博客就直接更新,OneDrive会自动同步云端
