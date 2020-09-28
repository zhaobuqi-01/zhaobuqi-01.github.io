---
title: go数据类型的默认值及转换
date: 2020-09-20 21:39:59
tags:
categories: go
copyright:
---

# go语言的数据类型的零值

```go
package main
import "fmt"
func main(){
	var a int
	var b float32
	var c float64
	var is bool
	var name string
	fmt.Printf("a=%d,b=%d,c=%d,is=%v,name=%v",a,b,c,is,name)
}
```

| 数据类型 | 默认值 |
| -------- | ------ |
| 整型     | 0      |
| 浮点型   | 0      |
| 字符串   | 空串   |
| 指针 | nil |


# go语言数据类型转化

go语言没有自动转化，需要显性转化



```go 
package main
import fmt
func main{
    var i int = 100
    //i->float32
    var n1 float32 = float32(i)
    var n2 int64 = int64(i)
    fmt.printf("i=%d,n1=%v",i,n1)//%v使用默认格式输出
}
```

# go 数据类型转化的细节

* 被转化的是变量存储的数据（即值），变量本身是没有转变的
* 如果转化的数据由大到小可能会发生数据溢出，如int64强制转化为int8，编译不会报错，但是数据会发生数据溢出，按二进制进行溢出

```go
var n1 int32 = 12
var n2 int64 
var n3 int 8
n2 = n1 + 20  //int32-->int 64
n2 = int64(n1) + 20 //正确
n2 = int8(n1) +127 //编译通过，但是数据溢出
n2 = int8(n1) + 128//编译不通过，128超出int8的范围
```



