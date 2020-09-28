---
title: jmu-python-汇率兑换
date: 2020-09-28 23:37:24
tags:
categories: python
copyright:
---

###  7-1 jmu-python-汇率兑换 (10分)

按照1美元=6人民币的汇率编写一个美元和人民币的双向兑换程序

### 输入格式:

输入人民币或美元的金额，人民币格式如：R100，美元格式如：$100

### 输出格式:

输出经过汇率计算的美元或人民币的金额，格式与输入一样，币种在前，金额在后，结果保留两位小数

### 输入样例1:

```in
R60
```

### 输出样例1:

```out
$10.00
```

### 输入样例2:

```in
$5
```

### 输出样例2:

```out
R30.00
```

```python
money=input()
unit = money[0]
if money[0] == 'R':
    U=eval(money[1:])/6
    print("$%.2f" % U)
elif money[0] == '$':
    R=6*eval(money[1:])
    print("R%.2f" %R)
```

