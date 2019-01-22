---
layout:     post
title:      利用Github Pages和jekyll创建个人博客
subtitle:   博客创建过程中踩过的坑与个人心得
date:       2019-01-21
author:     春风化雨
header-img: img/post-19-01-21.jpg
catalog: true
tags:
    - github 
    - jekyll
    - blog
---



> 不积跬步，无以至千里
>
> 不积小流，无以成江海 



# 前言

***



博主今年大三，现就读于西安一所211高校，是一个对未来迷茫的考验党。

之前也折腾过一个博客，那时是用wordpress搭建的，还花了钱买了服务器（腾讯云学生价120/年），但是一直没动手写文章，因为觉得麻烦，不如去学点新东西，新技术（比如近些年来的，机器学习深度学习之类的），古人说的好：**术业有专攻**，盲目追求技术的后果就是**什么都会一点，什么都不会**，于是索性就想着再弄一个**不花钱**的博客，来记录自己的学习历程和心得，毕竟没有过目不忘的脑子，只能靠多巩固来弥补技术间隙性的遗忘。



***

# 正文

---

*本篇文章采用Github Pages+jekyll快速搭建个人博客*

### 1.注册+登录你的github

首先，你得拥有一个github账号，如果没有，赶紧去注册一个吧!  [Github](http://github.com/)

[![kPtvJ1.md.png](https://s2.ax1x.com/2019/01/21/kPtvJ1.md.png)](https://imgchr.com/i/kPtvJ1)

​      **sign up** 注册一个账号

​      **sign in**  登录你的账号

### 2.Fork(拉取)我的博客模板

登录github账号后，进入[我的仓库](https://github.com/cfhyxxj/cfhyxxj.github.io/)中,点击Fork，就可拉取到我的博客模板到自己的仓库中

[![kPNsYR.md.png](https://s2.ax1x.com/2019/01/21/kPNsYR.md.png)](https://imgchr.com/i/kPNsYR)



### 3.修改repository(仓库)名

在第2步的基础上，点击setting



[![kPNTfI.md.png](https://s2.ax1x.com/2019/01/21/kPNTfI.md.png)](https://imgchr.com/i/kPNTfI)



修改repository name 为:         你的github名.github.io 

例如我的github账号是：cfhyxxj，则我的这个repository name 应改为： cfhyxxj.github.io

接着点击Rename即可

[![kPUCpq.md.png](https://s2.ax1x.com/2019/01/21/kPUCpq.md.png)](https://imgchr.com/i/kPUCpq)



### 4.检查上述步骤是否成功

在浏览器上输入网址：你的github名.github.io

会出现如下图所示的博客界面，不过还得修改下，才能改成你自己的博客

[![kPcB7t.md.png](https://s2.ax1x.com/2019/01/21/kPcB7t.md.png)](https://imgchr.com/i/kPcB7t)



##  整个网站的架构

```
├── _config.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.textile
|   └── on-simplicity-in-technology.markdown
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.textile
|   └── 2009-04-26-barcamp-boston-4-roundup.textile
├── _data
|   └── members.yml
├── _site
├── img
└── index.html
```

其中重要的就是这几个文件：

* _config.yml   全局配置文件
* _posts 存放博客文章的文件夹
* img  存放个人博客网站上少量的图片(博客文章里插入的是图片外链，图片放置在图床，加快了博客加载速度，后面还会提到)



## 修改全局配置

在你的仓库里，找到_config.yml文件，双击打开

然后对此文件进行修改(可对照下面设置和网站页面改)

[![kP2hF0.md.png](https://s2.ax1x.com/2019/01/21/kP2hF0.md.png)](https://imgchr.com/i/kP2hF0)



### 网站设置

```
# Site settings
title: charryglomc   #这个标题会显示在左上角(返回主页)和header图片中间字体
SEOTitle: 春风化雨的博客  #这个标题显示在浏览器标签页上
header-img: img/post-bg-desk.jpg  #主页上部图片
email: 798577670@qq.com  
description: ""
keyword: "春风化雨的博客, cfhyxxj"
url: "http://cfhyxxj.github.io"          # your host, for absolute URL
baseurl: ""      # for example, '/blog' if your blog hosted on 'host/blog'
github_repo: "https://github.com/cfhyxxj/cfhyxxj.github.io.git" # you code repository

```



### 侧边栏

```
# Sidebar settings
sidebar: true                           # true为有侧边栏
sidebar-about-description: "花开堪折直须折,莫待无花空折枝"  #侧边栏描述
sidebar-avatar: /img/zz.png      #本领想用二柱子头像的，但是觉得并不合适
```



### 社交账号

![](http://upload-images.jianshu.io/upload_images/2178672-ec775a22f76e2f40.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
# SNS settings
RSS: false
# weibo_username:     
#zhihu_username:     
github_username:    cfhyxxj   #不填就注释掉，博主只想要star，hhh
#facebook_username:  
#jianshu_username:   
#twitter_username:  
```

### 评论系统

我推荐用**gitalk**评论插件，**gitalk**是由github账号登录，接下来改一下下面的参数就好了

```
# Gitalk
gitalk:
  enable: true    #是否开启Gitalk评论
  clientID:  xxxxxxxxxxxxxxx                  #生成的clientID
  clientSecret:  xxxxxxxxxxxxxx              #生成的clientSecret
  repo: cfhyxxj.github.io    #改为自己的仓库名称
  owner: cfhyxxj    #改为自己的github用户名
  admin: cfhyxxj    #同上
  distractionFreeMode: true #是否启用类似FB的阴影遮罩

```

#### 获取clientID和clientSecret

首先申请一个[Github Application](https://github.com/settings/applications/new)，如下照着改为自己的就行了

![kPWM8K.png](https://s2.ax1x.com/2019/01/21/kPWM8K.png)

登录后，往下滑，就可看到自己的**clientID**和**clientSecret**

### 网站统计

集成了 [Baidu Analytics](http://tongji.baidu.com/web/welcome/login) 和 [Google Analytics](http://www.google.cn/analytics/)，到各个网站注册拿到**track_id**替换下面的就可以了

```
# Analytics settings
# Baidu Analytics
ba_track_id: xxxxxxxxxxxxxxxxxxxxxxxx

# Google Analytics
ga_track_id: 'xxxxxxxxx'            # Format: UA-xxxxxx-xx
ga_domain: auto
```

### 好友

```
friends: [
    {
        title: "简书·BY",
        href: "http://www.jianshu.com/u/e71990ada2fd"
    },{
        title: "Apple",
        href: "https://apple.com"
    },{
        title: "Apple Developer",
        href: "https://developer.apple.com/"
    }
]     #如不想用可用#注释掉，但要一行一行注释
```

### 标签

```
# Featured Tags
featured-tags: true                     # 是否使用首页标签
featured-condition-size: 0              # 相同标签数量大于这个数，才会出现在首页

```

### 提交保存

将网页拉到底部，提交所有的修改

[![kPWXRK.md.png](https://s2.ax1x.com/2019/01/21/kPWXRK.md.png)](https://imgchr.com/i/kPWXRK)



### 购买域名

很幸运还是学生，买域名有优惠，跑题了，hhh

我买的阿里的域名.top，一年9RMB，是不是觉得特别便宜呢？

可用淘宝或支付宝登录，然后搜索栏搜索**域名**，输入你想设定的域名，看有没有，然后购买

买了之后要进行***域名解析***

### ping  ip

在这之前要在cmd命令行里ping一下 你的github账号.github.io的ip地址

例如我的：

ping  cfhyxxj.github.io  

(可能有不同，最好自己ping一下，这个ip地址应该是最新美国Github Pages服务器的地址)

[![kPfKds.md.png](https://s2.ax1x.com/2019/01/21/kPfKds.md.png)](https://imgchr.com/i/kPfKds)



### 域名解析

进入阿里云控制台，双击域名，进入域名控制台，双击解析

[![kPfUeJ.md.png](https://s2.ax1x.com/2019/01/21/kPfUeJ.md.png)](https://imgchr.com/i/kPfUeJ)



添加两条记录解析

记录类型两条都为A

主机记录一个为@，一个为www

记录值为刚才ping的ip地址

![mark](http://plnzlwv2k.bkt.clouddn.com/blog/20190121/NsJuozcyMOs0.png?imageslim)



![mark](http://plnzlwv2k.bkt.clouddn.com/blog/20190121/HP4bjbTVE8Lb.png?imageslim)

### 修改CNAME

修改仓库下的CNAME文件内容，改为自己刚注册的域名

![mark](http://plnzlwv2k.bkt.clouddn.com/blog/20190122/9kVWbW747h9K.png?imageslim)

### 测试

在浏览器输入域名，直接成功跳转到自己的博客，大功告成！

### 写文章

要写文章首先要学习一下**markdown语法**，可以看下[markdown基本语法](http://cfhyxxj.top/2019/01/22/markdown基本语法/)

另外安利一个mardown神器：typora，界面简洁，写下即可渲染。 [typora下载链接](https://www.typora.io/#windows)

博客文章最后是以.md文件的形式保存，.md标题是由下图框框内的yaml自动决定的，也就是你写博客前面要照着如下写

title，subtitle，date，author，header-img，tags全部由自己设定，最后传文章显示到博客上

![mark](http://plnzlwv2k.bkt.clouddn.com/blog/20190122/WdkrEYR9W5yF.png?imageslim)

### 传文章

将文章上传到自己的博客，可以下载[github-desktop](https://desktop.github.com/),也可以通过git命令的方式传，

这里我采用github-desktop传文章

