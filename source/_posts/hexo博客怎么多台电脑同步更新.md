---
title: hexo博客怎么多台电脑同步更新
abbrlink: 63977
categories:
  - Notes
  - hexo
tags: hexo
description: hexo博客怎么多设备同步更新
date: 2022-04-19 21:44:39
password:
abstract:
message:
---
此方案用于多设备同步以及备份
#### 旧电脑

##### 创建新分支

这里我们创建一个名为`backup`的分支

![](hexo博客怎么多台电脑同步更新/update%20(1).png)

##### 把新分支设为默认分支

![](hexo博客怎么多台电脑同步更新/update%20(2).png)

##### 将分支克隆到本地

![](hexo博客怎么多台电脑同步更新/update%20(4).png)

##### 删掉除`.git`文件夹以为外的所有文件

![](hexo博客怎么多台电脑同步更新/update%20(5).png)

##### 复制到原本的博客文件夹

![](hexo博客怎么多台电脑同步更新/update%20(6).png)

##### 将文件添加到暂存区

```git add –A```

##### 提交到本地仓库

```git commit -m "backup"```

##### 推送到`backup`分支

```git push origin backup```

#### 新电脑

##### 将分支克隆到本地

```git clone 仓库地址```

##### 安装依赖

```npm install```

#### 所有电脑每次更新

##### 都要执行以下指令

```
git pull
git add -A
git commit -m "backup"
git push origin backup
hexo cl
hexo g
hexo d
```