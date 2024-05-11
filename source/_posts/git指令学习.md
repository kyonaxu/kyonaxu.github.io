---
title: git指令学习
tags: []
categories: []
# poster:
#   topic: 标题上方的小字
#   headline: 大标题
#   caption: 标题下方的小字
#   color: 标题颜色
date: 2024-05-11 09:14:20
description:
cover: /images/wallhaven-kx6yqm.png
banner: /images/wallhaven-kx6yqm.png
sticky:
mermaid:
katex:
mathjax:
topic:
author:
references:
comments:
indexing:
breadcrumb:
leftbar: 
rightbar: 
h1:
type:
---
<center><small><small> 
  <i><font color="grey">
    图源网络，侵删
  </font></i>
</small></small></center>   

---
简单记录下自己学习遇到的常用git指令，不定时更新  

---
### 创建项目
```bash
git init
```
把当前目录当成git的文件夹
```bash
git init file_name
```
当前目录下创建一个名字叫file_name的git文件   

---
### 分支操作
```bash
git branch
```
查看本地分支，当前分支会标出来

```bash
git branch -a
```
查看本地和远程分支

```bash
git branch -m old_branch_name new_branch_name
```
修改本地分支名

```bash
git branch -d branch_name
```
删除本地分支

```bash
git checkout branch_name
```
切换分支

```bash
git checkout -b branch_name
```
基于本分支创建新分支，自动切换到新分支

```bash
git checkout -b branch_name remote_name/remote_branch_name
```
基于远程分支创建新分支，远程分支要先fetch或pull过（git branch -a要能看到对应的远程分支），自动切换到新分支

```bash
git fetch remote_name remote_branch_name:branch_name
```
基于远程分支创建新分支，需要用`git checkout branch_name`切换到新分支

```bash
git branch --set-upstream-to remote_name/remote_branch_name
```
将当前分支与远程分支相关联

```bash
git push remote_name -d remote_branch-name
```
删除远程分支


---
### 远程库/远程分支相关
```bash
git remote
```
查看远程库

```bash
git remote -v
```
查看远程库和库的url

```bash
git remote add remote_name remote_url
```
添加远程库

```bash
git remote set-url remote_name remote_url
```
修改远程库的url

---
### 拉取推送合并等
```bash
git add file
```
将文件file加入暂存区

```bash
git commit -m "注释"
```
提交暂存区的文件

```bash
git commit --amend
```
修改注释，i是插入模式，esc推出插入模式，:wq保存退出

```bash
git fetch remote_name
```
将远程库的全部更新取到本地

```bash
git fetch remote_name remote_branch_name
```
将远程库的某个分支的更新取到本地

```bash
git merge branch_name
```
本分支与branch_name分支合并

```bash
git pull remote_name remote_branch_name:branch_name
```
将远程库的某个分支的更新取回，并合并到本地分支，合并到本分支的话branch_name可省略  

```bash
git push remote_name remote_branch_name
```
将本地分支提交到远程分支，并合并  

```bash
git cherry-pick commit_id
```
不合并分支，只是将某个分支的某次提交与本分支合并

---
### 其他
```bash
git status
```
查看文件状态，显示未暂存的修改和未跟踪的修改

```bash
git log
```
查看提交的版本历史（回退的不记录）  

```bash
git reflog
```
查看所有操作的历史记录，包括回退等  

```bash
git reset --hard commit_id
```
回退到某个版本  

---
### 常见参数解释
```
--abort: 终止操作

--continue：继续操作

-d
--delete：删除 

-D
--delete --force的快捷键

-f
--force：强制

-m
--move：移动或重命名

-M
--move --force的快捷键

-r
--remote：远程

-a
--all：所有
```


