---
title: git学习
date: 2020-06-01 22:22:37
tags:
categories: git
copyright:
---

# 初始化设置

```git
git config --global user.name "your name"
git config --global user.email "your email"
```

# 设置ssh key

```git
ssh-keygen -t rsa -C "your email"
```

# 初始化仓库

初始化仓库以后**git** 才可以对目录里的文件进行跟踪

```git
git init
```

**添加文件到仓库**

```
git add <filename>  #添加文件到暂存区
git commit -m "提交描述" #将当前暂存区的文件保存到仓库的历史提交中（就像创建了一个快照，在特定的时期可以将仓库李所有文件回复到一个之前的状态）
```

# 历史记录

```
git status #显示Git仓库的状态 
```

**查看仓库状态** 

```
$ git status
On branch hexo
Your branch is up to date with 'origin/hexo'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "source/_posts/git\345\255\246\344\271\240.md"

nothing added to commit but untracked files present (use "git add" to track)
# 显示未跟踪的文件有 source/_posts/git\345\255\246\344\271\240.md ,没有加入暂存区的文件也没有提交的文件
```

**查看修改的内容** 

```
gti diff <filename> #查看更改前后的差别/查看修改的内容（可以查看工作树，暂存区最新提交之间的差别）
```

**版本回退** 

``` 
git log #查看提交日志
```



