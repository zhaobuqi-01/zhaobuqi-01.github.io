---
title: 程序流程控制
date: 2020-10-08 18:06:12
tags:
categories: go
copyright:
---

# 顺序结构

程序从上到下逐次地执行，中间没有任何判断与跳转。

# 分支控制

分支控制就是让程序有选择的执行

## 单分支

```go
#语法
if 条件表达式{
    执行代码块
}
```

```go
#示例
package main
import(
    "fmt"
)
func main(){
    var age int
    fmt.Scanln(&age)
    if age>18{
        fmt.Println("你年龄大了，要对自己负责")
    }
}
```

![image.png](https://i.loli.net/2020/10/05/GKxXaRDOu7jncHV.png) 

## 双分支

```go
#语法
if 条件表达式{
    执行代码块1
}
else{
    执行代码块2
}
```

![image.png](https://i.loli.net/2020/10/05/DsKeyX4QdOlVnvJ.png) 

## 多分支

```go
#语法
if 条件表达式1{
    执行代码块1
}
else if 条件表达式2{
    执行代码块2
}
......
else{
    执行代码块n
}
#else 可有可无
#多分支只能有一个执行入口或者一个执行入口都没有【没有else】
#
```

## 嵌套分支

```go
#语法
if 条件表达式{
    if 条件表达式{
	}
}
#控制在3层以内
```

## switch分支结构

```go
#语法
#switch用与基于不同条件执行不同的代码
#switch匹配项后面不需要再加break
switch 表达式1{
    case 表达式1,表达式2,...:
    	语句块1
    case 表达式3,表达式4,...:
    	语句块2
    default:
    	语句块
}

```

**switch细节** 

+ switch的条件表达式可以是**常量，变量，有返回值的函数等都可以** 
+ case与switch的数据类型要保持一致
+ case后面可以跟多个表达式，使用逗号进行分隔
+ case后面的表达式如果是常量（字面量），则要求不能重复
+ case不需要带break
+ default不是必需的
+ switch后面可以不用带表达式，类似**if  elsse** 的使用

```go
switch{ 
    case age ==10 :
    	fmt.Println("age==10")
    case age ==20 :
    	fmt.Println("age==20")
    default:
    	fmt.Println("没有匹配到")
}
```

* switch后也可以直接定义一个变量并用分号隔开

```go
switch age:=10; { 
    case age ==10 :
    	fmt.Println("age==10")
    case age ==20 :
    	fmt.Println("age==20")
    default:
    	fmt.Println("没有匹配到")
}
```



* switch的穿透**fallthrough** 

```go 
switch age:=10; { 
    case age ==10 :
    	fmt.Println("age==10")
    	fallthrough#穿透
    case age ==20 :
    	fmt.Println("age==20")
    default:
    	fmt.Println("没有匹配到")
}
#输出
#age==10 age==20
#默认穿透一层
#
```

* Type Switch :switch语句还可以与type-switch来判断某个interface变量中实际指向的变量类型

## switch与if else 的区别

1. 如果判断的具体的数值不多，而且符合整数，浮点数，字符，字符串，使用switch
2. 对于区间判断和结果为布尔值的情况使用**if else ** 

# for 循环控制

```go
#语法 
/**************1.********************/
for 循环变量的初始化;循环条件;循环变量迭代{
    循环操作(语句)
}
/**************2.********************/
j:=1//循环变量初始化
for 循环判断条件{
    循环体
    j++//循环变量迭代
}
/**************3.********************/
for{
    循环体
}#死循环，需要配合break语句使用
/*********************************/
#循环四要素
#1.循环变量初始化
#2.循环条件
#3.循环操作(语句)，循环体
#4.循环变量迭代
```

**for循环执行的顺序说明** 

1. 执行循环变量初始化
2. 执行循环条件
3. 如果条件为真，则执行循环体
4. 执行循环变量迭代
5. 继续执行2，3，4，直到循环条件为假(false)，退出for循环

**for循环的细节与注意事项** 

 ```go
   //for-range遍历字符串，数组
   /***************传统方法********************/
   var str string = "hello,world!"
   for i:=0;i<len(str);i++;{
       fmt.printf("%c\n",str[i])
   }
   //当出现汉字是会出现乱码，汉字在utf-8里占3个字节，而读取则是一个字节
   /****************4.for-range*****************/
   str = "hello,world!"
   for index,val := range str {
       fmt.printf("index=%d,val=%c\n",index,val)
   }
   //当存在汉字时，不会出现乱码
   //for-range遍历使用的是字符的方式遍历
 ```



## while与do while的实现

**Golang里没有while和do while语法** 

**while循环的实现** 

```go
//语法
循环变量初始化
for{
    if 循环条件表达式{
        break//跳出for循环
    }
    循环体
    循环变量迭代
}
```

**do while 循环的实现** 

```go
//语法
循环变量初始化
for{
    循环体
    循环变量迭代
    if 循环条件表达式{
        break //跳出for循环【结束for循环】
    }
}
//至少执行一次
```

# 跳转语句

 ## break跳转语句

```go
//语法
//break语句用于终止某个语句块的执行，用于中断当前for循环或跳出switch语句。
{
    ......
    break
    ......
}
```

1. break默认跳出最近的for循环
2. break后面可以指定标签，跳出标签对应的for循环【可以配合标签使用】

## continue跳转语句

1. continue语句用于结束本次循环，继续执行下一次循环。
2. continue可以使用标签跳出

```go
//语法
{
    ......
    continue
    ......
}
```

## goto跳转语句 

跳转到标签所在代码处，不再执行goto后面的代码

```GO
//语法
goto label
......
label:statement
```

## return跳转语句

跳出所在的方法或者函数