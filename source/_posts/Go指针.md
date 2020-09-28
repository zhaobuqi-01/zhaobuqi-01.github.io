---
title: Go指针
date: 2020-09-22 23:05:14
tags:
categories: go
copyright:
---

# 与指针相关的运算符

>地址运算符：&
>
>一般注解：
>
>后跟一个变量名时，&给出该变量的地址
>
>示例：
>
>&nurse表示变量nurse的地址
>
>地址运算符：*
>
>一般注释：
>
>后跟一个指针或地址时，*给出存储在指针指向地址上的值
>
>示例：
>
>nurse = 22
>
>ptr = &nurse
>
>val = *ptr
>
>执行以上3条语句的 最终结果是把22赋给val

![image.png](https://i.loli.net/2020/09/24/XaPpvLAWZIEMsxi.png)

# 变量：名称，地址和值



