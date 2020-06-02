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
gti diff #查看当前工作树和暂存区
git diff HEAD #查看工作树和最新提交的差别
```

**版本回退** 

+ 查看提交日志

``` git
git log #查看提交日志/显示从最近到最远的提交日志   [回退历史版本]
git relog [回退未来的版本]
```

>**git log 的参数** 
>
>​	-- pretty=short   只显示提交信息的第一行
>
>​	-p	显示文件的改动（查看提交带来的改动）
>
>`git log <filename>` 	只显示指定的目录，文件的日志

* 回溯历史版本

在Git用`HEAD` 表示当前版本，也就是最新的提交，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当往上的版本太多时使用`HEAD~数字`。 

`git reset` 

​	--hard

# 撤销修改

`git checkout --<filename>`	 把文件在工作区的修改全部撤销，让文件回到最近一次`git commit `或`git add` 时的状态。

`git reset HEAD <file>` 	 撤销暂存区的修改

`git reset HEAD`	既可以回退版本，也可以把暂存区的修改回退到工作区。

1. 想修改工作区里的文件	`git checkout --file`
2. 想修改暂存区里文件   `git reset HEAD <flie>`
3. 想撤销本次提交  `git reset^`

#  文件删除与恢复

+ 从版本库里删除文件	先在目录里删除文件`rm <file`再在版本库里删除对应的文件`git rm`
+ 从版本库里恢复文件    `git checkout --<file>`

无论你删除或恢复一个文件以后进行提交，git都会为你保存一个版本，你都可以通过版本回退来找到自己需要的版本。

# 添加远程仓库

`git remote add origin git@github.com:用户名/仓库名.git`

origin可以修改，origin是远程仓库的标识符

# 推送到远程仓库

``` 
git push -u origin master #-u参数可以在推送的时候，将origin仓库的master分支设置为本地分支当前分支的upstream（上游）。添加了这个参数，将来在 git pull 的时候可以直接从origin的master分支获取最新的内容而不用添加其他参数。
```

```
git push -u origin <分知名>
```

# 获取远程仓库

```
git clone git@github.com:用户名/仓库名.git
#默认处于远程仓库的默认分支下，同时系统会自动将origin设置为该远程仓库的标识符
```

## 获取远程仓库的其他分支

```
git checkout -b other origin/others
# -b参数后是本地新建分支的名称，新建分支后面的是获取来源的分支名称
git fetch origin other:others
# origin后面的分别是本地分支和远程仓库分支
```

**注意获取其他分支需要与远程仓库相关联** 