---
title: jmu-python-回文数判断
date: 2020-09-28 23:38:33
tags:
categories: python
copyright:
---

###  7-2 jmu-python-回文数判断（5位数字） (10分)

本题目要求输入一个5位自然数n，如果n的各位数字反向排列所得的自然数与n相等，则输出‘yes’，否则输出‘no’。

### 输入格式:

13531

### 输出格式:

yes

### 输入样例1:

```in
13531
```

### 输出样例1:

```out
yes
```

### 输入样例2:

```in
13530
```

### 输出样例2:

```out
no
```

```python
num = input()
if num[0] == num[-1]and num[1]==num[-2]:
    print("yes")
else:
    print("no")

```

