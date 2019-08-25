# 编译好的HTML文件

编译好的HTML文件（.chm）通常作为微软的HTML帮助系统的一部分发布。CHM文件是HTML、图片、脚本或者其他web相关的编程语言（VBA、JScript、Java、ActiveX）压缩编译而成的。CHM的内容是有HTML帮助执行程序（hh.exe）利用IE渲染展示的。

攻击者可能利用这种技术隐藏恶意代码。通过自定义的CHM文件嵌入payload的方式，可以将payload传送到用户机器上，然后通过用户执行手段触发。CHM文件执行手法可能会绕过应用程序白名单在一些老的、没有打补丁的不需要通过hh.exe执行二进制程序的系统上。



