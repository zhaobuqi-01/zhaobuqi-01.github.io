---
title: jmu-python-分段函数
date: 2020-09-28 23:39:38
tags:
categories: python
copyright:
---

# 7-3 jmu-python-分段函数 (10分)

本题目要求计算下列分段函数f(x)的值（x为从键盘输入的一个任意实数）：

![分段函数.jpg](https://images.ptausercontent.com/625099ce-3e8d-4a2f-a719-99929e1e027e.jpg)

### 输入格式:

输入在一行中给出实数 x。

### 输出格式:

在一行中按“f(x)=result”的格式输出，其中**x与result都保留两位小数**。

### 输入样例:

```in
0.76
```

### 输出样例:

```out
f(0.76)=1.20
```

```python
x = eval(input())
if x<3 :
    print("f(%.2f)=%.2f" %(x,1.2))
elif x==3 :
    print("f(%.2f)=%.2f" %(x,10))
elif x>3 :
    num = 2*x + 1
    print("f(%.2f)=%.2f" %(x,num))
```

