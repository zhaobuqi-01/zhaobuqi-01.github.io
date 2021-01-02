---
title: python复习
date: 2021-01-02 15:34:32
tags:
categories: python
copyright: 
---

# python输入输出

## 输入

### 单输入 

`input("")`默认为字符串，可以使用强制转换为为需要的类型

`eval()`可以将`" " ' '`中的数组最短转化为整型`int`

### 多输入int

```python
a,b,c=input('三个字符串:').split(',')
a,b,c=input('三个字符串:').split()
a,b,c=eval(input('三个数字:'))
a,b,c=map(eval,input('三个数字:').split())#a，b,c接收的是int
```



## 输出

### 格式化输出

1.`format`

`print("{}".format(a),end="")`

`print("{:.2f}".fomat(a),end=" ")`

2.`print("%.2d"%da)`   `print("%.2d%.2d"%(a,b))`

`print("")`默认换行，加`end="参数"`可以改变默认换行

### 去掉列表中的`[]` 

```python
#例一
list = eval(input(""))
list1 = []#初始化一个空列表
for i in list:
    if i not in list1:
        list1.append(i)
print(*list1)#*将列表进行拆解
#例二
nums1=list(input().split())
nums2=list(input().split())
out=[]
for x in nums1:
    if x not in nums2 and x not in out:
        out.append(x)
for x in nums2:
    if x not in nums1 and x not in out:  
        out.append(x)   
print(' '.join(out))#使用字符串连接函数
#字符串连接函数是将列表，元组中的元素一指定的字符(分隔符)连接起来生成一个新的字符
#串,使用join()方法实现,其一般形式为
#sep.join(sequence)
#其中，sep表示分隔符，可以为空;sequence是要连接的元素序列。功能是以sep作为分隔
#符，将sequence所有的元素合并成一个新的字符串斌返回该字符串
#例
s4=["beijing","xian","tianjin","chongqing"]
sep="-->"
str=sep.join(s4)
```



