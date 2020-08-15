---
title: 开始学习c++
date: 2020-08-03 20:02:00
tags:
categories: C++
copyright:
---

# 开始学习c++

注释使用//,C++对大小写敏感，也就是说区分大写字符和小写字符
注意在linux中c++的文件扩展名为cxx，windows中文件扩展名为cpp

## c++的输入与输出

### main函数

```c++
int main()
{
    statements;
    return 0;
}
```

这几行表明有一个名为main的函数，并描述了该函数的行为。

这几行代码构成了函数定义(function definition)。

>函数定义由两部分组成：函数头，函数体。
>
>```c++
>int main()//第一行 int mian() 叫函数头
>{
>    statements;
>    return 0;
>}//花括号({和})中包括的部分叫函数体。
>```

