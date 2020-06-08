---
title: linux_ls
date: 2020-06-03 16:15:49
tags:
categories: linux
copyright:
---

# ls与pwd

## pwd

**pwd** 	--显示当前所在的目录

演示

```shell
zhaobuqi@zhaobuqi:~$ pwd
/home/zhaobuqi
```

> 名称
>        pwd - 显示出当前/活动目录的名称
>
> 概述
>        pwd [选项]...
>
> 描述
>        输出当前工作目录的完整名称。
>
> ```shell
>    -L, --logical
>           使用环境变量中的 PWD，即使其中包含符号链接
> 
>    -P, --physical
>           避免所有符号链接
> 
>    --help 显示此帮助信息并退出
> 
>    --version
>           显示版本信息并退出
> 
>    如果没有指定任何选项，默认使用 -P。
> ```

## ls

**ls** 	查看指定目录的内容

> ls [选项] [文件名...]

**常用ls的参数** 

* **-l** 


 ``` shell
-l, --format=long, --format=verbose
              除每个文件名外，增加显示文件类型、权限、硬链接数、所  有者名、组
              名、大小（  byte  ）、及时间信息（如未指明是  其它时间即指修改时
              间）。对于6个月以上的文件或超出未来 1 小时的文件，时间信息中的时
              分将被年代取代。
 ```
 ```
zhaobuqi@zhaobuqi:~$ ls -l
总用量 76
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 6月   2 20:48  公共的
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 5月  30 18:52  模板
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 6月   2 20:48  视频
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 5月  31 21:45  图片
drwxr-xr-x 4 zhaobuqi zhaobuqi  4096 5月  29 13:29  文档
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 6月   2 21:07  下载
drwxr-xr-x 3 zhaobuqi zhaobuqi  4096 5月  29 12:54  音乐
drwxr-xr-x 2 zhaobuqi zhaobuqi  4096 5月  29 13:18  桌面
drwxrwxr-x 5 zhaobuqi zhaobuqi  4096 5月  29 13:29  baidunetdisk
drwxrwxr-x 3 zhaobuqi zhaobuqi  4096 6月   3 15:03  go
drwxrwxr-x 3 zhaobuqi zhaobuqi  4096 6月   3 15:02  go_code
-rw-r--r-- 1 zhaobuqi zhaobuqi 10013 6月   3 15:40 '- list directory contents'
drwxrwxr-x 4 zhaobuqi zhaobuqi  4096 5月  30 17:58  my_app
drwxr-xr-x 3 zhaobuqi zhaobuqi  4096 5月  28 19:46  snap
-rw-r--r-- 1 zhaobuqi zhaobuqi 10013 6月   3 15:40 't  information  about  the FILEs (the current directory by default).
 ```

* **-a** 

```shell
 -a, --all
              列出目录中所有文件，包括以“.”开头的文件。

```

```shell
zhaobuqi@zhaobuqi:~$ ls -a
 .
 ..
 公共的
 模板
 视频
 图片
 文档
 下载
 音乐
 桌面
 .accelerate
 baidunetdisk
 .bash_history
 .bash_logout
 .bashrc
 .cache
 .config
 .dbus
 .deepinwine
 .designer
 .gitconfig
 .gnupg
 go
 go_code
 .kingsoft
'- list directory contents'
 .local
 .mono
 .mozilla
 my_app
 .node_repl_history
 .npm
 .npmrc
 .nv
 .pam_environment
 .pki
 .presage
 .profile
 snap
 .ssh
 .sudo_as_admin_successful
't  information  about  the FILEs (the current directory by default).'
 .viminfo
 .vscode
 .wine
 .xinputrc
```

