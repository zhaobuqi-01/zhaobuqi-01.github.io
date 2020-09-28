---
title: 字符串类型
date: 2020-09-20 21:14:04
tags:
categories: go
copyright:
---

# 字符串的基本使用

```go
package main
import "fmt"
func main(){
	var address string = "中国"
	fmt.Println(address)
}
```

## 注意事项

1. go语言使用UTF-8编码
2. go语言中的字符串是不可变，字符串一旦被赋值就无法修改
3. 字符串的两种表现方式

* 双引号【""】，会识别转义字符
* 反引号【``】，可以以字符串的原生形式输出

```go 
package main
import "fmt"
func main(){
	var address string = "中国"
	fmt.Println(address)
	str2 := `nihao \n\r djskjsdvh
	dvsjdvlsdv
	dvksv`
	fmt.Println(str2)
}

```

4. 字符串的拼接方式

```go
package main
import "fmt"
func main(){
	var str = "hello" + "world" 
	str += "世界"
	fmt.Println(str)
    //当一个拼接很长的时候，可以分行写，但加号需要在保留上一行
}
```



