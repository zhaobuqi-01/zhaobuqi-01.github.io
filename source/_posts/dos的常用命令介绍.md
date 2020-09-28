---
title: dos的常用命令介绍
date: 2020-09-12 21:26:47
tags:
categories: go
copyright:
---

## dos的常用命令介绍

1. 查看当前目录是什么 

**dir** 

```dos
D:\demo>dir
 驱动器 D 中的卷是 Data
 卷的序列号是 543D-EB9C

 D:\demo 的目录

2020/09/12  19:35    <DIR>          .
2020/09/12  19:35    <DIR>          ..
2020/09/12  19:35         2,141,184 myhello.exe
2020/09/11  20:11         2,141,184 test.exe
2020/09/11  20:09                91 test.go
               3 个文件      4,282,459 字节
               2 个目录 392,539,840,512 可用字节
```

2. 切换到其他盘符

**cd /d f:** 

```dos
D:\demo>cd /d e:

E:\>
```

3. 切换目录

**cd d:\demo** 

```dos
E:\>cd e:\Doweload

e:\Doweload>
```

4. 切换到根目录

**cd \ ** 

```dos
e:\Doweload>cd \

e:\>

```

5. 新建目录

**md** 

``` 
e:\>md test

e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  21:13    <DIR>          Doweload
2020/09/12  22:13    <DIR>          test
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               0 个文件              0 字节
               6 个目录 983,124,643,840 可用字节

```

6. 删除目录

**rd**

rd /q 不询问

rd /s 当目录里有文件时使用这个

``` 
e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  21:13    <DIR>          Doweload
2020/09/12  22:13    <DIR>          test
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               0 个文件              0 字节
               6 个目录 983,124,643,840 可用字节

e:\>rd test

e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  21:13    <DIR>          Doweload
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               0 个文件              0 字节
               5 个目录 983,124,643,840 可用字节
```

7. echo指令

```
e:\>echo hello > Doweload\test.txt

e:\>dir Doweload
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\Doweload 的目录

2020/09/12  22:21    <DIR>          .
2020/09/12  22:21    <DIR>          ..
2020/09/11  13:21       113,897,472 boinc_7.16.11_windows_x86_64_vbox.exe
2020/09/11  13:23    <DIR>          briblo_103
2020/09/11  13:18         3,807,157 briblo_103.zip
2020/09/12  19:12         1,550,147 C 学习笔记.pdf
2020/09/11  13:16    <DIR>          fliqlo_133
2020/09/11  13:16         3,804,811 fliqlo_133.zip
2020/09/12  19:14         1,014,280 Go 1.5 源码剖析 （书签版）.pdf
2020/09/12  19:12         1,365,184 Go 学习笔记 第四版.pdf
2020/09/11  13:17         4,339,940 Hubble3D_PCScreensaver.exe
2020/09/12  21:13    <DIR>          MLofAndrew-Ng-master
2020/09/11  13:52        36,728,520 Qv2ray.v2.6.3.linux-x64 (1).AppImage
2020/09/11  13:51        36,728,520 Qv2ray.v2.6.3.linux-x64.AppImage
2020/09/10  19:23    <DIR>          TeamViewerPortable
2020/09/10  19:22        27,316,451 TeamViewerPortable.rar
2020/09/10  19:21        28,032,224 TeamViewer_Setup.exe
2020/09/12  22:21                 8 test.txt
2020/09/11  00:22       579,181,704 VMware-workstation-full-15.5.6-16341506.exe
2020/09/11  00:18             1,617 vmwarepro_16025.zip
2020/09/12  19:12           235,516 下载.png
              15 个文件    838,003,551 字节
               6 个目录 983,124,643,840 可用字节
```

8. 复制文件

**copy**  

```
e:\>copy Doweload\test.txt e\
系统找不到指定的路径。
已复制         0 个文件。

e:\>copy Doweload\test.txt e:\
已复制         1 个文件。

e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  22:21    <DIR>          Doweload
2020/09/12  22:21                 8 test.txt
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               1 个文件              8 字节
               5 个目录 983,124,643,840 可用字节

e:\>copy Doweload\test.txt e:\hello.txt
已复制         1 个文件。

e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  22:21    <DIR>          Doweload
2020/09/12  22:21                 8 hello.txt
2020/09/12  22:21                 8 test.txt
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               2 个文件             16 字节
               5 个目录 983,124,643,840 可用字节
```



9. 删除文件

**del** 文件名

del * 删除全部文件

del *.txt

``` 
e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  22:21    <DIR>          Doweload
2020/09/12  22:21                 8 hello.txt
2020/09/12  22:21                 8 test.txt
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               2 个文件             16 字节
               5 个目录 983,124,643,840 可用字节

e:\>del test.txt

e:\>dir
 驱动器 E 中的卷是 新加卷
 卷的序列号是 30EC-F122

 e:\ 的目录

2020/09/10  18:53    <DIR>          dingchunhui
2020/09/12  22:21    <DIR>          Doweload
2020/09/12  22:21                 8 hello.txt
2020/09/11  19:53    <DIR>          ubutun20.04
2020/09/11  00:23    <DIR>          VM
2020/09/11  00:35    <DIR>          新建文件夹
               1 个文件              8 字节
               5 个目录 983,124,643,840 可用字节
```

10. 清屏

**cls** 

11. 推出dos

**exit** 