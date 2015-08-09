---
layout: post
title: Mac OS上安装配置MongoDB
description: "在Mac OS上安装配置MongoDB，过程还是比较简单的"
modified: 2015-08-08
share: false
tags: [MongoDB]
image:
  feature: abstract-3.jpg
---

之前没事的时候玩了玩MongoDB，最近换了系统，于是在Mac下又配置了一遍 <br>
在Mac OS上安装mongoDB实际上很简单，官网上有详细的步骤照着做就好了。下面说一说我的步骤以及配置方式。 <br>

我的Mac OS的版本是10.9.5，使用的工具有终端、emacs <br>

1、去MongoDB官网[下载](http://www.mongodb.org/downloads)mongoDB包 <br>

2、下载之后解压缩到任意一个目录下解压缩后可以发现有一个“bin”目录，这个目录放置mongoDB的命令的目录

3、使用命令“mkdir -p /data/db”，在“/”下创建data/db目录，这个是放置mongoDB数据的目录，我试了不创建这个目录就启动mongoDB，结果报“exception in initAndListen: 10296 dbpath (/data/db/) does not exist, terminating”，这个目录不仅是必须的而且不会自动创建，不知道能不能换个目录放置数据 <br>

4、进入"bin"目录，使用命令“./mongod”启动mongoDB server，启动后注意不要关闭终端 <br>

5、另外打开一个终端窗口，同样为了方便起见，进入"bin"目录，运行命令"./mongo"，这时可以看到mongoDB的控制台在终端上出现了，这时就可以使用任意mongoDB的命令操作mongoDB数据了，就和使用mysql命令行操作mysql一样  <br>

6、为了方便起见，把mongoDB的bin目录加入到环境变量中，具体的方法是编辑"~"下的.bash_profile文件（如果没有找到，则自己创建一个）<br>
PATH="/../mongodb/bin: ..." <br>
export PATH 