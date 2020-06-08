---
title: linux_帮助命令
date: 2020-06-03 15:25:45
tags:
categories: linux
copyright:
---

# 帮助命令

* man
* help
* info

命令用法演示

`man ls`

```shell
NAME
       ls - list directory contents

SYNOPSIS
       ls [OPTION]... [FILE]...

DESCRIPTION
       List  information  about  the FILEs (the current directory by default).
       Sort entries alphabetically if none of -cftuvSUX nor --sort  is  speci‐
       fied.

       Mandatory  arguments  to  long  options are mandatory for short options
       too.

       -a, --all
              do not ignore entries starting with .

       -A, --almost-all
              do not list implied . and ..
 省略......
```

`help help`或 `help --help`

>help [-dms] [模式 ...]
>    显示内建命令的相关信息。
>    
>
>```shell
>显示内建命令的简略信息。如果指定了 PATTERN 模式，
>给出所有匹配 PATTERN 模式的命令的详细帮助，否则打
>印一个帮助主题列表
>
>选项：
>  -d	输出每个主题的简短描述
>  -m	以伪 man 手册的格式显示使用方法
>  -s	为每一个匹配 PATTERN 模式的主题仅显示一个用法
>	简介
>
>参数：
>  PATTERN	指定帮助主题的模式
>
>退出状态：
>返回成功，除非未找到 PATTERN 模式没有找到或者使用了无效选项。
>```
>

`info ls`

> ext: dir invocation,  Up: Directory listing
>
> 10.1 ‘ls’: List directory contents
> ==================================
>
> The ‘ls’ program lists information about files (of any type, including
> directories).  Options and file arguments can be intermixed arbitrarily,
> as usual.
>
>    For non-option command-line arguments that are directories, by
> default ‘ls’ lists the contents of directories, not recursively, and
> omitting files with names beginning with ‘.’.  For other non-option
> arguments, by default ‘ls’ lists just the file name.  If no non-option
> argument is specified, ‘ls’ operates on the current directory, acting as
> if it had been invoked with a single argument of ‘.’.
>
>    By default, the output is sorted alphabetically, according to the
> locale settings in effect.(1)  If standard output is a terminal, the
> output is in columns (sorted vertically) and control characters are
> output as question marks; otherwise, the output is listed one per line
> and control characters are output as-is.
>
> 省略...

