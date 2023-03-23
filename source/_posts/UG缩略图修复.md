---
title: UG缩略图修复
date: 2023-03-23 11:33:45
tags:
---
#### 起因
Creo真活脱脱的一个流氓软件，在安装Creo之后，UG文件的缩略图都变成了Creo的图标，看着膈应。

<!--more-->

#### 1、[方法一](https://www.ugsnx.com/thread-284773-1-1.html)
~~~
新建记事本
复制代码regsvr32 "D:\Program Files\Siemens\NX1899\NXBIN\ugshext.dll"粘贴到记事本
更换成自己的路径，保存文档
更改.txt后缀名为.bat
以管理员身份运行，重启电脑
~~~
#### 2、[方法二](https://www.ugsnx.com/thread-301964-1-1.html)
~~~
打开Windows系统设置
选择应用
选择默认应用
选择按文件类型指定默认应用
找到.prt文件类型，选择默认打开方式为NX
~~~
#### 3、[方法三](https://www.ugsnx.com/thread-251847-1-1.html)
~~~
先把C:\Windows\System32目录下的cmd.exe拷贝到D:\Program Files\Siemens\NX\NXBIN目录下（安装目录）。
用管理员身份运行cmd.exe，然后输入regsvr32 ugshext.dll按回车就可。
~~~



