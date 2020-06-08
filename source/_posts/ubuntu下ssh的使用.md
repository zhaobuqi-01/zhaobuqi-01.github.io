---
title: ubuntu下ssh的使用
date: 2020-06-02 21:59:06
tags: ssh
categories: linux
copyright:
---

# 安装ssh

```shell
sudo apt install openssh
```
# ssh登录远程服务器

>ssh -l username  ip

>ssh username@ip

输入**exit** 退出连接

# ssh上传文件

`scp <file> username@ip:dir`

# ssh下载文件

`scp usernmae@ip:file dir`

# 生成ssh密钥

`ssh-keygen`



