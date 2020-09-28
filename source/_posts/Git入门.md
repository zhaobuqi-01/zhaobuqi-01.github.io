---
title: Git入门
date: 2020-09-26 15:13:56
tags:
categories: git
copyright:
---

# Git的下载与安装

## linux

`sudo apt-get install git`

![image.png](https://i.loli.net/2020/09/26/xOepViyLMdUDm5o.png) 

## windows

### 下载

[Git下载地址](https://git-scm.com/downloads)

根据自己电脑选择合适的版本

### 组件的选择

选择自己需要组件，由于所有必需的组件都已经默认勾选，可以直接进入下一步。

### 环境变量的设置

在安装选项选择添加到Path中

# 初始化设置

# 设置姓名与邮箱地址

```git
git config --global user.name "name"
git config --global user.email "your email"
```

![image.png](https://i.loli.net/2020/09/26/uzldxYp6Vj3gGiq.png) 

会在“~./gitconfig”中输出以下信息

![image.png](https://i.loli.net/2020/09/26/nKVxs5lJmYD1p79.png) 

# 使用前的准备

## 创建GitHub账号

[github地址](https://github.com/) 

![image.png](https://i.loli.net/2020/09/26/Mw32Ok69WpfmogS.png) 

## 设置SSH Key

` ssh-keygen -t rsa -C "youremail"` 

![image.png](https://i.loli.net/2020/09/26/xTDW84mnobksra7.png) 

## 添加公开密钥

![image.png](https://i.loli.net/2020/09/26/V9mBXrUSl4s6fM3.png) 

ssh在`~/.ssh/`中

![image.png](https://i.loli.net/2020/09/26/YVCMeiaJ1UcAQd3.png)

![image.png](https://i.loli.net/2020/09/26/G5K4p7ekisq8SEh.png) 

## 创建仓库

![image.png](https://i.loli.net/2020/09/26/onWGjAUSRmheBai.png) 

# 基本操作

## git init 初始化仓库

![image.png](https://i.loli.net/2020/09/26/M4OyI2Ar9QmRs5G.png) 

```
zhaobuqi@zhaobuqi:~$ cd  git_study/
zhaobuqi@zhaobuqi:~/git_study$ git init
已初始化空的 Git 仓库于 /home/zhaobuqi/git_study/.git/
```

## git status 查看仓库状态

```git 
zhaobuqi@zhaobuqi:~/git_study$ git status 
位于分支 master

尚无提交

无文件要提交（创建/拷贝文件并使用 "git add" 建立跟踪）

```

```git 
zhaobuqi@zhaobuqi:~/git_study$ touch readme.md
zhaobuqi@zhaobuqi:~/git_study$ git status 
位于分支 master

尚无提交

未跟踪的文件:
  （使用 "git add <文件>..." 以包含要提交的内容）
	readme.md

提交为空，但是存在尚未跟踪的文件（使用 "git add" 建立跟踪）
```



## git add 向暂存区添加文件

```git 
zhaobuqi@zhaobuqi:~/git_study$ git add readme.md
zhaobuqi@zhaobuqi:~/git_study$ git status 
位于分支 master

尚无提交

要提交的变更：
  （使用 "git rm --cached <文件>..." 以取消暂存）
	新文件：   readme.md

```

## git commit 保存仓库的历史记录

```git
zhaobuqi@zhaobuqi:~/git_study$ git commit readme.md 
[master （根提交） 53ff5c9] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 readme.md
zhaobuqi@zhaobuqi:~/git_study$ git status 
位于分支 master
无文件要提交，干净的工作区

```

`git commit .` 提交全部文件

## git log 查看提交日志

```git
zhaobuqi@zhaobuqi:~/git_study$ git log 
commit 53ff5c9fabd62b3d81371efe28b2538a72c31cdb (HEAD -> master)
Author: zhaobuqi <1138883954@qq.com>
Date:   Sat Sep 26 16:18:17 2020 +0800

    first commit

```

## git diff 查看更改前后的差别

```git
zhaobuqi@zhaobuqi:~/git_study$ git diff
diff --git a/readme.md b/readme.md
index e69de29..f86f2b5 100644
--- a/readme.md
+++ b/readme.md
@@ -0,0 +1 @@
+git教程

zhaobuqi@zhaobuqi:~/git_study$ git diff HEAD
diff --git a/readme.md b/readme.md
index e69de29..f86f2b5 100644
--- a/readme.md
+++ b/readme.md
@@ -0,0 +1 @@
+git教程
zhaobuqi@zhaobuqi:~/git_study$ git commit readme.md 
[master 1f79ce9] 2 commit
 1 file changed, 1 insertion(+)

```

# 分支操作

## git branch 显示全部分支

```git
zhaobuqi@zhaobuqi:~/git_study$ git branch 
* master

```

## git checkout -b 创建，切换分支

```git
zhaobuqi@zhaobuqi:~/git_study$ git checkout -b git_study1
切换到一个新分支 'git_study1'
zhaobuqi@zhaobuqi:~/git_study$ git branch 
* git_study1
  master

```

## git merge 合并分支

```git 
zhaobuqi@zhaobuqi:~/git_study$ git checkout master 
切换到分支 'master'
zhaobuqi@zhaobuqi:~/git_study$ git merge --no-ff git_study1 
Merge made by the 'recursive' strategy.
 README.md | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

```

## git log --graph 以图表形式查看分支

```git 
zhaobuqi@zhaobuqi:~/git_study$ git log --graph 
*   commit 4d25e84f96d67cdc13f3c4e6896f430c2de1a9df (HEAD -> master)
|\  Merge: 1f79ce9 a9bfccb
| | Author: zhaobuqi <1138883954@qq.com>
| | Date:   Sat Sep 26 16:40:49 2020 +0800
| | 
| |     Merge branch 'git_study1'
| | 
| * commit a9bfccb265010fd2b1f55c70877d77f382fb847c (git_study1)
|/  Author: zhaobuqi <1138883954@qq.com>
|   Date:   Sat Sep 26 16:39:59 2020 +0800
|   
|       git_study commit
| 
* commit 1f79ce90c8eeb18514b15ed5af1828d4e6e5fa10
| Author: zhaobuqi <1138883954@qq.com>
| Date:   Sat Sep 26 16:32:09 2020 +0800
| 
|     2 commit
| 
* commit 53ff5c9fabd62b3d81371efe28b2538a72c31cdb
  Author: zhaobuqi <1138883954@qq.com>
  Date:   Sat Sep 26 16:18:17 2020 +0800
  
      first commit

```

#  更改提交

##  git reset   回溯历史版本

```git
zhaobuqi@zhaobuqi:~/git_study$ git reset --hard 1f79ce90c8eeb18514b15ed5af1828d4e6e5fa10
HEAD 现在位于 1f79ce9 2 commit

```

# 推送远程仓库

## git  remote add 添加远程仓库

```git
zhaobuqi@zhaobuqi:~/git_study$ git remote add origin git@github.com:zhaobuqi-01/test.git
```

## git push 推送到远程仓库

```git
zhaobuqi@zhaobuqi:~/git_study$ git push -u origin  master
```

## git clone 获取远程仓库

```git 
zhaobuqi@zhaobuqi:~/test$ git clone git@github.com:zhaobuqi-01/zhaobuqi-01.github.io
```

## git pull 获得最新的远程仓库分支

```git
git  pull origin master
```

