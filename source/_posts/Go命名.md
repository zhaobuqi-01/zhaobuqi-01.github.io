---
title: Go命名
date: 2020-09-15 19:45:54
tags:
categories: go
copyright:
---

# 2.1命名

**命名规则：**

一个名字必须以一个字母（Unicode字母）或下划线开头，后面可以跟任意数量的字母、数字或下划线。

**注意事项：** 

1. 大写字母和小写字母是不同的：heapSort和Heapsort是两个不同的名字

2. 关键字不能用于自定义名字，只能在特定语法结构中使用。

**关键字** 

>break		default	 	func		 interface		 select
>case 	 	defer 			go  			map    			struct
>chan 		else 				goto 		package 		switch
>const 		fallthrough 	if 			range 			type
>continue 	for 				import 	return 		 var

**预定义的名字** ，主要对应内建的常量，类型和函数

这些预定义的名字并不是关键字，你可以在定义中重新使用它们。在一些特殊的场景中重新定义它们也是有意义的，但是也要注意避免过度而引起语义混乱。

>内建常量: 	true	 false 	iota 	nil
>内建类型: int 	int8 	int16 	int32 	int64
>				uint 	uint8 uint16 	uint32 uint64 	uintptr
>				float32 	float64 	complex128 	complex64
>				bool 	byte 	rune 	string 	error
>内建函数: 	make 	len 	cap 	new 	append 	copy 	close 	delete
>					complex 	real	 imag
>					panic 	recover

3. 如果它的就一个名字在函数内部定义，那么它的就只在函数内部有效。如果在函数外部定义，那么将在当前包的所有文件中都可以访问。
4. **名字的开头字母的大小写决定了名字在包外的可见性。包本身的名字一般总是用消息字母** 如果一个名字是大写字母开头的(注：必须是在函数外部定义的包级名字；包级函数名本身也是包级名字)，那么他将是导出的，也就是可以被外部的包访问，**例如 fmt 包的Printf就是导出的，可以在fmt包外部访问** 

5. **名字的长度没有逻辑限制** ，但是Go语言的风格是尽量使用短小的名字，对于局部变量尤其是
   这样；你会经常看到i之类的短名字，而不是冗长的theLoopIndex命名。通常来说，如果一个
   名字的作用域比较大，生命周期也比较长，那么用长的名字将会更有意义。