---
layout : post
category : lessons
tags : [VPN, Lubuntu]
title : 如何在Lubuntu上安装使用VPN
---

先在网上搜索，说，在“网络连接”->“添加”中可以“增加vpn连接”，我发现在“选择连接类型”中找不到“添加vpn连接”，无意中发现了命令

    #sudo apt-get install network-manager-pptp

执行后，就可以找到“添加vpn连接”了。由于我这里已经有了一份vpn的配置文件（×.vpn），所以，想直接导入,于是就在“选择连接类型”中选择了“导入vpn配置”，发现不能识别这个vpn后缀的文件。那我就自己建立连接吧，我在“选择连接类型”中，选择“点到点隧道协议（PPTP）”。需要填写基本的信息：网关、用户名、密码。而我手中的数据没有网关ip，只有域名，这条路走不通；

Lubuntu中安装了VirtualBox，有个xp系统。运维给出的vpn使用说明就是针对windows的。于是我就下载vpn-client-2.2.2-release.exe 和 我的 vpn配置文件。在xp中安装客户端并重启后，导入我的配置文件，点击后，让我填写用户名和密码，填完后软件窗口如图：

<img src="/assets/img/VPN01.jpg" alt="替代文本" />

提示内容为：

    config loaded for site 'SM-VPN-Zhangxp.vpn'
    attached to key daemon ...
    peer configured
    iskamp proposal configured
    esp proposal configured
    client configured
    local id configured
    remote id configured
    pre-shared key configured
    bringing up tunnel ...

Network中的内容如图：

<img src="/assets/img/VPN02.jpg" alt="替代文本" />

然后我就开始访问公司内网，发现不能访问。光甫提议使用linux中的vpn客户端“SHREW SOFT VPN CLIENT”，然后我就开始在linux中摸索，下面步入本文正题。

找到[网址](http://shrew-soft-vpn-client.updatestar.com/en)，进而找到下载的[链接](https://www.shrew.net/download/ike)，然后选择了2.2.1的tgz包：ike-2.2.1-release.tgz

解压啦

    #tar zxvf ike-2.2.1-release.tgz
    
产生了一个ike目录。进去ike目录后发现没有configure，于是想办法，说,可以使用apt-get install试试，后来我发现没有相关的软件。于是继续搜“linux SHREW SOFT VPN CLIENT”，然后找到了这个[链接](http://www.gta.com/downloads/external/54/General/ShrewSoftVPN_LinuxInstall.pdf)，发现了安装方法，这样说。

    $>cd    ~/Downloads/ike
    $>cmake –DQTGUI=YES –DETCDIR=/etc   –DNATT=YES
    $>cmake -DNATT=YES
    $>make
    $>make  install

当我看到了cmake，猛然想到我在ike目录中找执行文件时，曾点开 README.TXT ，里面出现过cmake，当时我不认为（不知道是安装命令）是安装命令，就无视。看来在安装软件时还是先看看readme啊！我在readme中复制cmake这行命令，然后执行：

    #cmake -DCMAKE_INSTALL_PREFIX=/usr -DQTGUI=YES -DETCDIR=/etc -DNATT=YES

说，cmake没有安装，就装呗：

    #sudo apt-get install cmake
    
继续执行cmake命令，出现错误说：

    CMake Error at CMakeLists.txt:265 (message)
    Unable to locate openssl crypto include files

然后就搜索这个错误，找到了这个[链接A](http://ubuntuforums.org/showthread.php?t=2078420)，链接中正好有人和我出现了同样的错误，针对这个问题有人建议：

    #sudo apt-get install libssl-dev libssl0.9.7
    
然后提示错误：（不是我机器上的提示，不过表达的是一个意思）

    Reading package lists... Done
    Building dependency tree 
    Reading state information... Done
    E: Unable to locate package libssl10.9.7
    E: Couldn't find any package by regex 'libssl10.9.7'
    
针对这个问题，有人建议：

    #sudo apt-get install libssl0.9.7

还是出错：（不是我机器上的提示，不过表达的是一个意思）
    
    Reading package lists... Done
    Building dependency tree 
    Reading state information... Done
    E: Unable to locate package libssl0.9.7
    E: Couldn't find any package by regex 'libssl0.9.7'
    
有人又说：

    #sudo apt-get install opensll
    
程序说已经安装过了。有人又说，可能已经修好了，再执行一下cmake命令，我执行了发现还是不成功。这时，有人站出来说，你试试这个：

    #sudo apt-get install libssl-dev libssl0.9.8 libssl1.0.0
    
这下子，安装 libssl-dev 通过了，于是接着执行cmake命令，又出错：

    Unable to locate libedit include files
    
受启发，我就开始安装 liedit

    #sudo apt-get install libedit-dev （可能还安装了libedit2,这点忘记了）

接着，继续执行cmake命令，发现出现这个错误：

    CMake Error at CMakeLists.txt:347 (message):
    Unable to locate required binary : flex

针对这个问题，说要执行如下命令：

    #sudo apt-get install flex bison
    
然后我继续cmake，又出现问题了，其中一条提示是：

    qmake: could not find a Qt installation of ''
    
google之，发现了这个[链接](http://stackoverflow.com/questions/17918142/qmake-could-not-find-a-qt-installation-of-setting-up-qmake)，说执行：

    #sudo apt-get install qt5-default
    
然后我再执行cmake，发现还是原来的错误，就又删掉了qt5,在[链接A](http://ubuntuforums.org/showthread.php?t=2078420)中，找到了说法，要安装qt4,于是就执行

     #sudo apt-get install qt4-default
     
安装后，继续cmake，got it，按照安装文档上的说法，接着执行make、make install命令，均ok。接着就是打开界面了，需要执行 

    #sudo iked start
    #qikea

当我在执行第一句时，总是提示：

    invalid option start specified
    
于是继续搜，发现了这篇[文章](http://stackoverflow.com/questions/13175823/how-can-i-install-shrew-soft-vpn-client-under-ubuntu-12-10)，里面讲到：

    #sudo iked
    #sudo qikea
    
执行后终于弹出了软件窗口，我就将配置文件导入。导入成功后，开始链接，发现没有让我填写用户名、密码，点击链接，就直接提示如图

<img src="/assets/img/VPN03.png" alt="替代文本" />

因为我在虚拟机中也曾导入过配置文件，我把那个配置文件弄到linux中，导入配置，点击链接，弹出的界面有用户名、密码框，我输入内容如图:

<img src="/assets/img/VPN04.png" alt="替代文本" />

另一个选项卡如图:

<img src="/assets/img/VPN05.png" alt="替代文本" />

显然和我在winxp下的图形一样。我也不能访问公司内网。

等找到问题后，继续写这篇文章。