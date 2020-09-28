---
title: jmu-python-找字符
date: 2020-09-28 23:17:14
tags:
categories: python
copyright:
---

# 7-5 jmu-python-找字符 (15分)

输入一个字符串及字符，输出第一次出现该字符的位置。

### 输入格式:

- 行1：输入字符串
- 行2：输入一个字符

### 输出格式:

- 找到，输出对应位置，格式`index=X`的， `X`表示查找到位置
- 找不到，输出`can't find letter X`, `X`表示查找字符

### 输入样例:

```in
python
t
```

### 输出样例:

```out
index=3
```

### 输入样例:

```in
python
l
```

### 输出样例:

```out
can't find letter l
```

```python
s = input()
key = input()
count = 0
num =0
for i in range(len(s)):
    num=num+1
    if key == s[i] :
        print("index=%d"%num)
        count = 1
        break
    i=i+1
if count==0:
    print("can't find letter %s"%key)
```

