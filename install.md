# Java学习笔记
---
## 基本概念
- JVM:java虚拟机，就是一个java程序运行的虚拟机，这也是java语言跨平台特性的一个重要保障。
- JRE:java程序运行所需的核心部件,没有JRE，java程序将无法运行,所以JRE一定包含JVM,如果只想运行java程序不需要开发的话，一个JRE就够了，但是你想开发java软件的时候，就需要下面这个玩意了
- JDK:java开发工具包,包含java的开发环境和运行环境

---
## 安装JDK
所以我们学习Java就要下载一个JDK，一下是JDK下载安装所需的
[JDK官方下载连接](https://www.oracle.com/java/technologies/javase-downloads.html)
如果官方网站不能下载的话，可以参考一下[链接](https://www.java.com/zh_CN/download/win10.jsp)
[JDK安装教程](https://blog.csdn.net/konggu_youlan/article/details/79942800)
关于安装过程中需要注意的是环境变量部分。如果安装成功完成之后，在cmd中输入`jave -version`或者`javac`，如果有对应的输出则说明安装成功

---
## 安装IDEA
IDEA全称IntelliJ IDEA，被称为最好用的java开发环境，这个软件是JetBrains开发的，大家用的Pycharm也是这个公司的产品。当然也可以选择其他的IDE
首先从[JetBrains官网下载](https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows&code=IIC),这里是免费的社区版，另一个[链接](https://mp.weixin.qq.com/s/Gh7oVK2K7X2WY6nKACGXiQ?client=tim&ADUIN=2847218411&ADSESSION=1582334285&ADTAG=CLIENT.QQ.5603_.0&ADPUBNO=26933)是软件安装管家提供的一种破解方法，亲测有效，其中最后一步为实现这个软件的汉化，不喜欢的同学可以跳过，不影响使用。关于上述破解方法每次打开都会有一个弹窗的解决办法，就是找到那个`jetbrains-agent.jar`中找到那个`important.txt`文件，然后放到C盘的根目录下.(如果agent没放在c盘的话，那个`important.txt`文件应和其在一个目录下)

---
## IDEA基本配置
IDEA配置可以参考这个[链接](https://blog.csdn.net/zxwu_1993/article/details/88632993)

---
通过以上步骤，我们就已经完成了java环境的基本配置，在下一篇将开始介绍如何执行实现HelloWord程序。