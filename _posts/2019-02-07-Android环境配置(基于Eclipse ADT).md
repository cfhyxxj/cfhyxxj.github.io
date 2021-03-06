---





layout:     post
title:      Android环境配置(基于Eclipse ADT)
subtitle:  
date:       2019-02-07
author:     春风化雨
header-img: img/and.jpg
catalog: true
tags:
    - android 
    - java
---

>  前两个步骤是java开发环境配置

## 1. 在windows中下载和安装jdk

> JDK(Java Development Kit) 是 Java 语言的软件开发工具包([SDK](https://baike.baidu.com/item/SDK))。
>
> SE(JavaSE)，standard edition，标准版，是我们通常用的一个版本，从JDK 5.0开始，改名为Java SE。
>
> EE(JavaEE)，enterprise edition，企业版，使用这种JDK开发J2EE应用程序，从JDK 5.0开始，改名为Java EE。从2018年2月26日开始，J2EE改名为Jakarta EE [1-2]  。
>
> ME(J2ME)，micro edition，主要用于移动设备、嵌入式设备上的java应用程序，从JDK 5.0开始，改名为Java ME。
>
> 没有JDK的话，无法编译Java程序（指java源码.java文件），如果想只运行Java程序（指class或jar或其它归档文件），要确保已安装相应的JRE。

先进入[Oracle的官网](https://www.oracle.com)

百度百科关于**Oracle**的介绍

[![2019-02-23_233505.png](https://i.loli.net/2019/02/23/5c71684595e54.png)](https://i.loli.net/2019/02/23/5c71684595e54.png)

下拉到java，点击

[![2.png](https://i.loli.net/2019/02/23/5c716792eccef.png)](https://i.loli.net/2019/02/23/5c716792eccef.png)

下载

[![3.png](https://i.loli.net/2019/02/23/5c7167930debb.png)](https://i.loli.net/2019/02/23/5c7167930debb.png)

## 2. 配置jdk上的变量环境

选择我的电脑，右键属性，点击搞基系统设置

[![1.png](https://i.loli.net/2019/02/23/5c71691250dba.png)](https://i.loli.net/2019/02/23/5c71691250dba.png)

点击环境变量



[![2.png](https://i.loli.net/2019/02/23/5c71691244f4d.png)](https://i.loli.net/2019/02/23/5c71691244f4d.png)

设置三个系统变量

**JAVA_HOME**

例如在我的电脑上，jdk的安装路径为：C:\Program Files\Java\jdk1.8.0_191，所以**JAVA_HOME**的变量值应设置为：C:\Program Files\Java\jdk1.8.0_191   

[![3.png](https://i.loli.net/2019/02/23/5c7169123aaf0.png)](https://i.loli.net/2019/02/23/5c7169123aaf0.png)

创建好后可用%JAVA_HOME%作为jdk目录的统一引用路径

**Path**

如果Path变量不存在，则要新建一个，如若存在，则可直接编辑

例如我的Path已存在，点击进去



[![4.png](https://i.loli.net/2019/02/23/5c7169124d63b.png)](https://i.loli.net/2019/02/23/5c7169124d63b.png)

为Path变量添加两个变量值

%JAVA_HOME%\bin

%JAVA_HOME%\jre\bin 

如果两个变量值加在一起了，它们之间之间要加;

[![5.png](https://i.loli.net/2019/02/23/5c7169125750e.png)](https://i.loli.net/2019/02/23/5c7169125750e.png)

**CLASSPATH** 

变量值为：.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar 

变量值字符串前面的‘.’表示当前目录，设置CLASSPATH的目的是告诉Java环境在哪可以找到执行Java程序所需要的类或包

[![6.png](https://i.loli.net/2019/02/23/5c7169124f345.png)](https://i.loli.net/2019/02/23/5c7169124f345.png)



## 3. **下载安装Eclipse**

> Eclipse为Java应用程序及Android开发的IDE（集成开发环境）

[Eclipse下载](https://www.eclipse.org/downloads/)



## 4. **下载安装Android SDK**

> Android SDK提供了开发Android应用程序所需的API库和构建、测试和调试Android应用程序所需的开发工具
>
> Android Studio是Android集成开发工具，基于IntelliJ IDEA，类似Eclipse ADT，本篇文章是基于Eclipse ADT开发环境的配置，如果想用Android Studio，可不下Eclipse。Android Studio是近几年Google推出的，适用于原生开发，并且Google宣布不再支持对Eclipse升级，Android Studio已是未来大势所趋

进入[Android SDK下载网站](https://www.androiddevtools.cn/)（这里给的是不是官网，下载速度快）

进入后下拉到底部下载对应版本

[![1.png](https://i.loli.net/2019/02/23/5c716a7744b93.png)](https://i.loli.net/2019/02/23/5c716a7744b93.png)

下载后解压到除系统盘外其他文件夹(这个下载文件特别大，占用很多空间)，打开文件夹里**SDK Manager**

[![2.png](https://i.loli.net/2019/02/23/5c716a7736cdb.png)](https://i.loli.net/2019/02/23/5c716a7736cdb.png)

Android SDK Manager是一个**软件开发工具管理器**，从远程服务器下载开发工具到本地

而AVD Manager是一个**Android虚拟驱动管理器**，主要用来创建Android模拟器(手机模拟器)

然后根据如下图片自行安装

[![2019-02-23_234729.png](https://i.loli.net/2019/02/23/5c716b4646091.png)](https://i.loli.net/2019/02/23/5c716b4646091.png)

**Android SDK环境配置** 

设置三个系统变量

**ANDROID_SDK_HOME**

变量值为SDK的安装路径，例如我的为：F:\android-sdk_r24.4.1-windows\android-sdk-windows

[![4.png](https://i.loli.net/2019/02/23/5c716a7742f55.png)](https://i.loli.net/2019/02/23/5c716a7742f55.png)

**Path**

一个变量值为：%ANDROID_SDK_HOME%\platform-tools

另一个变量值为：%ANDROID_SDK_HOME%\tools

亲试网上各种教程，用;写在一起后没有配置成功，分开写配置成功

[![5.png](https://i.loli.net/2019/02/23/5c716a774b2cf.png)](https://i.loli.net/2019/02/23/5c716a774b2cf.png)

然后在命令行(win+r输入cmd进入），输入adb，出现如下界面

[![6.png](https://i.loli.net/2019/02/23/5c716a7767e29.png)](https://i.loli.net/2019/02/23/5c716a7767e29.png)

输入android，会出现Android SDK Manager

[![7.png](https://i.loli.net/2019/02/23/5c716a775eb41.png)](https://i.loli.net/2019/02/23/5c716a775eb41.png)

到这一步，SDK已配置成功了！



## 5. **为Eclipse安装ADT插件**

启动Eclipse，点击 Help菜单 -> Install New Software… ，点击弹出对话框中的Add… 按钮

Location：http://dl-ssl.google.com/android/eclipse/

[![8.png](https://i.loli.net/2019/02/23/5c716a77404ca.png)](https://i.loli.net/2019/02/23/5c716a77404ca.png)

[![9.png](https://i.loli.net/2019/02/23/5c716a7769b04.png)](https://i.loli.net/2019/02/23/5c716a7769b04.png)



安装完成后，会提示重启，然后Eclipse会根据目录的位置智能地和它相同目录下Android sdk进行关联

到这里，我们在windows上的Android上的开发环境搭建就完成了，这时候，你用Eclipse的File—>New—>Project...新建一个项目的时候，就会看到建立Android项目的选项了

[![10.png](https://i.loli.net/2019/02/23/5c716a775c412.png)](https://i.loli.net/2019/02/23/5c716a775c412.png)