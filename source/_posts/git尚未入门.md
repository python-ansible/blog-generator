---
title: 'git尚未入门'
date: 2019-01-02 17:25:55
tags: '版本控制'
---
本文介绍了**git init**,**git add**,**git commit -v**三个git命令的用法
## git init
git init命令用于在当前目录生成一个新的代码库，执行完之后我们会发现当前目录多出了一个.git目录，用于跟踪当前目录文件的修改。
![git init命令图片示例](/assets/gitInit.png)

## git add
git add命令用于添加指定的文件或目录到缓存区，便于之后使用git commit命令提交暂存区的文件到仓库区
![git add命令图片示例](/assets/gitAdd.png)

## git commit -v
git commit -v命令用于将暂存区文件提交到仓库区，同时显示diff信息，但git通常在执行commit操作时必须填入提交信息，所以我们需要在vim中编辑提交信息

执行git commit -v
![执行git commit -v](/assets/gitCommit1.png)

填写提交信息
![填写提交信息](/assets/gitCommit2.png)

提交成功
![提交成功](/assets/gitCommit3.png)