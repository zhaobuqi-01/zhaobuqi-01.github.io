---
title: jmu-python-凯撒密码加密算法
date: 2020-09-28 23:33:24
tags:
categories: python
copyright:
---

#  7-1 jmu-python-凯撒密码加密算法 (10分)

编写一个凯撒密码加密程序，接收用户输入的文本和密钥k，对明文中的字母a-z和字母A-Z替换为其后第k个字母。

### 输入格式:

接收两行输入，第一行为待加密的明文，第二行为密钥k。

### 输出格式:

输出加密后的密文。

### 输入样例:

在这里给出一组输入。例如：

```in
Hello World!
3
```

### 输出样例:

在这里给出相应的输出。例如：

```out
Khoor Zruog!
```

```python
s1 = ['a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z']
s2 = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z']
s = input()
k = int(input())
for i in range(len(s)):
    if 'a' <= s[i] <= 'z':
        for j in range(26):
            if s1[j] == s[i]:
                print("{}".format(s1[(j + k) % 26]), end="")
    elif 'A' <= s[i] <= 'Z':
        for j in range(26):
            if s2[j] == s[i]:
                print("{}".format(s2[(j + k) % 26]), end="")
    else:
        print("{}".format(s[i]),end="")
```



