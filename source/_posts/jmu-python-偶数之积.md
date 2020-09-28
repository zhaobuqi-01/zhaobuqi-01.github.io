---
title: jmu-python-偶数之积
date: 2020-09-28 23:18:39
tags:
categories: python
copyright:
---

# 7-4 jmu-python-偶数之积 (10分)

求1到n中所有偶数的积。

### 输入格式:

输入整数n。

### 输出格式:

1到n中偶数积。

### 输入样例:

```in
5
```

### 输出样例:

```out
8
```

```python
n = int(input())
sum = 1
for i in range(1,n+1) :
    if i%2 ==0 :
        sum=i*sum
    i+=1
print(sum)
```

