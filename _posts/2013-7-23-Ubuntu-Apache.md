---
layout : post
category : lessons
tags : [Ubuntu, Apache, 服务安装]
title : Ubuntu安装Apache
---

*注：本文是记录性文章，不是整理性文章（13.7.14 plan-13.7.21 begin-13.7.23 done）*

 1. 下载&解压

        tpbk@tpbk-T420:/usr/local/work$ sudo wget http://mirrors.sohu.com/apache/httpd-2.4.4.tar.gz [注释：sudo wget url -P catalog（下载到指定目录）]
        tpbk@tpbk-T420:/usr/local/work$ sudo tar zxvf httpd-2.4.4.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ sudo mkdir /usr/local/apache2
        
 2. 配置编译安装

        tpbk@tpbk-T420:/usr/local/work$ cd httpd-2.4.4
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo ./configure --prefix=/usr/local/apache2 --enable-module=shared
        
这里却报错了
        configure: error: APR not found .  Please read the documentation
查资料知道是缺少了APR，于是下载APR
        
        tpbk@tpbk-T420:/usr/local/work$ sudo wget http://labs.mop.com/apache-mirror//apr/apr-1.4.5.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ sudo tar -zxvf apr-1.4.5.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ cd apr-1.4.5
        tpbk@tpbk-T420:/usr/local/work/apr-1.4.5$ sudo ./configure
        tpbk@tpbk-T420:/usr/local/work/apr-1.4.5$ sudo make
        tpbk@tpbk-T420:/usr/local/work/apr-1.4.5$ sudo make install
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo ./configure --prefix=/usr/local/apache2 --enable-module=shared [再次执行]
        
这里又报错了
        configure:error: APR-util not found .  Please read the documentation.
查资料知道是缺少APR-util，于是下载APR-util

        tpbk@tpbk-T420:/usr/local/work$ sudo wget http://labs.mop.com/apache-mirror//apr/apr-util-1.3.12.tar.gz 
        tpbk@tpbk-T420:/usr/local/work$ sudo tar -zxvf apr-util-1.3.12.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ cd apr-util-1.3.12
        tpbk@tpbk-T420:/usr/local/work/apr-util-1.3.12$ sudo ./configure
        tpbk@tpbk-T420:/usr/local/work/apr-util-1.3.12$ sudo make
        tpbk@tpbk-T420:/usr/local/work/apr-util-1.3.12$ sudo make install
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo ./configure --prefix=/usr/local/apache2 --enable-module=shared [又执行]
        
仍提示APR-util not found，在于不知apr-util的路径，增加--with-apr=/usr/local/apr --with-apr-util=/usr/local/apr-util参数输入

        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo ./configure --prefix=/usr/local/apache2 --enable-module=shared　--with-apr=/usr/local/apr --with-apr-util=/usr/local/apr-util
        
又出现问题了：configure: error: pcre-config for libpcre not found. PCREis required and  available from http://pcre.org 这是因为没有安装pcre的原因。

        tpbk@tpbk-T420:/usr/local/work$ sudo wget http://sourceforge.net/projects/pcre/files/pcre/8.33/pcre-8.33.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ sudo tar -zxvf pcre-8.33.tar.gz
        tpbk@tpbk-T420:/usr/local/work$ cd pcre-8.33
        tpbk@tpbk-T420:/usr/local/work/pcre-8.33$ sudo ./configure --prefix=/usr/local/pcre
        tpbk@tpbk-T420:/usr/local/work/pcre-8.33$ sudo make
        tpbk@tpbk-T420:/usr/local/work/pcre-8.33$ sudo make install
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo ./configure --prefix=/usr/local/apache2 --enable-module=shared  --with-apr=/usr/local/apr/ --with-apr-util=/usr/local/apr-util/ --with-pcre=/usr/local/pcre
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo make
        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo make install

OK 安装完成！真是不容易啊！

        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo apachectl start
        
提示命令 apachectl 找不到

        tpbk@tpbk-T420:/usr/local/work/httpd-2.4.4$ sudo apt-get install apache2.2-common

又出错啦！Permission denied: AH00072: make_sock: could not bind to address 0.0.0.0:80no listening sockets available 使用 netstat -lnp | grep 80 然后kill [pid]后重新启动apache即可。
        
同时还会出现错误：AH00558: httpd: Could not reliably determine the server's fully qualified do ，解决办法：编辑httpd.conf文件，搜索"#ServerName"，添加ServerName localhost:80 重启apache；
        
现在的命令：开启 apache 服务，我使用的是：

        tpbk@tpbk-T420:/usr/local/apache2/bin$ sudo ./apachectl start
        
打开浏览器，输入localhost后，显示：It Works! 说明成功了。
