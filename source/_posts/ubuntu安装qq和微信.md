---
title: ubutun安装qq和微信
date: 2020-05-31 22:28:33pin
tags: deepin
categories: linux
copyright:
---

## 1.安装deepin

**1.使用git将deepin克隆到本地**

> git  clone  https://gitee.com/wszqkzqk/deepin-wine-for-ubuntu

**2.进入克隆到本地的deepin文件夹**

>cd  deepin-wine-for-ubuntu

**3.安装** 

>./install.sh

## 2.安装qq,微信

>wget -qO- https://deepin-wine.i-m.dev/setup.sh | sudo sh
>
>`#安装qq`
>
>sudo apt-get install deepin.com.wechat
>
>`#安装微信` 
>
>sudo apt-get install deepin.com.qq.im

