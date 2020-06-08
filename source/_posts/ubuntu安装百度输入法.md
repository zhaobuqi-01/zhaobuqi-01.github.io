---
title: ubuntu安装百度输入法
date: 2020-06-02 21:44:05
tags:
categories:
copyright:
---

# 解决依赖

```
# 通过命令行安装 aptitude
sudo apt-get install aptitude -y
```
使用aptitude解决安装依赖的问题
#  安装fcitx

```
# 通过命令行利用 aptitude 安装 fcitx 和 qt 等
sudo aptitude install fcitx-bin fcitx-table fcitx-config-gtk fcitx-config-gtk2 fcitx-frontend-all
```

# 安装qt5

**注意：不安装qt5,百度输入法无法正常使用**

```
sudo aptitude install qt5-default qtcreator qml-module-qtquick-controls2
```

# 安装百度输入法

到官网下载百度输入法的压宿包，然后解压，在解压的目录执行以下命令

`sudo dpkg –i fcitx-baidupinyin.deb`

**注意安装完重启即可，重启以后按照提示进行**

[百度输入法下载](https://srf.baidu.com/site/guanwang_linux/index.html)

# 卸载百度输入法

`sudo dpkg --purge remove fcitx-baidupinyin:amd64` 