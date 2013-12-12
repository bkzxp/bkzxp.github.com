---
layout : post
category : lessons
tags : [lamp, Lubuntu]
title : 在lubuntu上安装配置LAMP的注意点
---


最近在lubuntu上配置开发环境，使用lamp；我比较喜欢使用apt-get方式安装，简单方便；但是apache和php在使用这种方式安装后，我居然没有找到httpd.conf文件和php.ini文件。于是放弃了这种，自己编译安装；
编译安装的详细流程我没有记下了，因为是几天前安装的，一些错误信息以及我的查询记录都没有保留下来（通常我都是在刚刚弄完后马上写分享，链接呀，错误信息呀什么的都能保留下来），现在也回忆不起来了，只保留了安装过程中需要注意的几点：

    httpd.conf 中的执行用户需要和代码的所属用户一致（服务是我自己用的，所以所属者应该时我的用户名，而非root）

    我最初不知道将自定义的域名信息放在哪里，原来这个位置和windows里面是一样的，也是在/etc/hosts,于是直接编辑hosts

    需要允许列出目录的权限 在allow 和 deny 那里添加
    
    虚拟目录中的log error的地址要与apache2的地址一致
    