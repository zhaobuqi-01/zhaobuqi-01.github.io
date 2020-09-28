---
title: jmu-python-统计成绩
date: 2020-09-28 23:30:21
tags:
categories: python
copyright:
---

#  7-3 jmu-python-统计成绩 (15分)

输入一批学生成绩，计算平均成绩，并统计不及格学生人数。

### 输入格式:

每行输入一个数据，输入数据为`负数`结束输入

### 输出格式:

```
平均分=XX,不及格人数=XX`,其中`XX`表示对应数据。如果没有学生数据，输出`没有学生
```

### 输入样例:

```in
30
50
70
80
90
20
-1
```

### 输出样例:

```out
平均分=56.67,不及格人数=3
```

```python
x = int(input())
num = 0
count = 0
sum =0 
if(x<0):
    print("没有学生")
    exit(0)
while x >= 0:
    count = count+1
    if x < 60:
        num = num+1
    sum = sum + x
    x = eval(input())
ave = sum/count
if(count > 0):
    print("平均分=%.2f,不及格人数=%d" % (ave, num))
if(num==0):
    print("没有学生")
    exit(0)

```

