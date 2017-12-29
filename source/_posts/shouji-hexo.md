---
title: 手机搭建Hexo博客环境
tags: Termux
keywords:
  - 安卓
  - 手机搭建hexo
  - termux
toc: true
thumbnail: https://wx2.sinaimg.cn/mw690/7095c8fbgy1fbutkeeucbj20et07xq3u.jpg

date: 2016-01-16 16:21:22
---
![](https://wx2.sinaimg.cn/mw690/7095c8fbgy1fbutkeeucbj20et07xq3u.jpg)
#### **介绍** :
Termux是比较简单的Linux终端，提供简单的开发环境，用来Hexo发布很方便，
缺点是终端不支持中文，作者也没有提供多语言。
<!--more-->

#### **开始**：
打开termux 
输入以下代码

```
apt update && apt upgrade  //升级到最新版本  
apt install coreutils      //安装一些基本的工具  
apt install git            //安装Git  
apt install nodejs         //安装Node.js 
```
#### **安装Hexo**：
在termux运行以下代码

``` 
    npm install hexo-cli -g       //全局安装hexo
    hexo init blog                      //生成blog以及主题什么什么文件
    cd blog                                //进入到blog目录
    [忽略]npm install                          //安装npm
```
#### **本地渲染hexo & 本地测试：**
继续在termux运行以下代码

``` 
     cd blog   //进入blog目录
     hexo g   //渲染命令
	     hexo s   //本地测试命令
```
然后打开浏览器 输入 120.0.0.1:4000 看看是不是有了博客
如果没有请检查哪里错了！

```
git config --global user.email "xxxx@xx.com" //邮箱 

 git config --global user.name "xxxx" //用户名 

 ssh-keygen -t rsa -C "xxxx@xx.com" //生成配对的公私钥

```

会提示你安装 openssh 安装就行

其他操作跟电脑搭建一模一样