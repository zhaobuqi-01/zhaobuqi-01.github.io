---
title: map
date: 2020-10-24 20:41:02
tags:
categories: go
copyright:
---

# map

## map 的基本介绍

`var map变量名 map[keeytype]valuetype`

keytype 不可以是`slice map function` ，因为不可以用`==`进行判断

`make用来分配空间`

**注意**

1. 使用前需要使用make对map进行空间的分配
2. map的key是不可以重复的