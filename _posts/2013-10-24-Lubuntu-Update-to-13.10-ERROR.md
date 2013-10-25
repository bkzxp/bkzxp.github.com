---
layout : post
category : lessons
tags : [Lubuntu]
title : Lubuntu 升级到 13.10（成功安装32位的过程）
---





前天将系统从 13.04 升级到了 13.10。当时我正在为 sublime2 摆弄中文输入的问题，采取的方案是安装了inputhelp插件[详见这篇文章(还没有写)]()。正在尝试那种略有不爽的中文输入时，系统弹出了升级提示，我稍微看了一下（其实没看懂多少）就坐等升级。

滚动条慢慢前进。弹出了选项，貌似让选择是否保留（我选择了保留，两次）。然后就看看多了哪些软件管理之类的，然后就看看原来装的软件还能不能用。
我意外的发现 sublime2 里面居然能够输入中文啦，
果不其然，WPS和Scrivener两个不能用，他们使用的都有32位的库。于是我从命令行中运行，发现32位的某库缺少/找不到，然后就尝试安装

    sudo apt-get install ia32-libs
    #有错误显示:找不到/不能安装，可是下列软件包取代了它：lib32z1 lib32ncurses5 lib32bz2-1.0

然后就用“可是下列软件包取代了它：lib32z1 lib32ncurses5 lib32bz2-1.0”google，发现了[这篇文章](http://lancehan.iteye.com/blog/1956785)，给出的建议是执行下行命令：

    sudo apt-get install g++-multilib
    sudo apt-get install ia32-libs
    #有错误显示:找不到/不能安装，可是下列软件包取代了它：lib32z1 lib32ncurses5 lib32bz2-1.0
    
我很无语，我准备放弃了，已经想好出路了，要么重新安装一个 13.04 版本,要么直接安装 ubuntu，就在今天早上，我重新搜索“lubuntu 13.10安装32位库”，找到了[一篇文章](http://forum.ubuntu.org.cn/viewtopic.php?t=447489),里面有人说：

    “ ia32_libs is deleted from 13.10. I don't know why and you don't have to ask. 
    Solution:
    1. try to install lsb, lsb-core. some 32 bits software need it. 
    2. if you can think about which software or libraries need by that software, install the i386 version:
    For example: you need package 'openjdk-6-jre', then try to install like this 'sudo apt-get install openjdk-6-jre:i386'.
    Hope it is helpful. ”
    
同时，我又看到了这个发言，说：

    Ubunt13.10 64bit 安装ia32-libs 需要添加源并且update才可以安装。
    我按照这个方法成功安装ia32-libs。
    参考这里：http://www.0838bbs.com/thread-15018-1-1.html
    
其实这个链接所在的网站需要回复才能看到具体的内容（万恶的回复机制），于是就又用“Ubunt13.10 64bit 安装ia32-libs”作为关键字，google之。于是找到了这个[链接](http://forum.ubuntu.org.cn/viewtopic.php?f=77&t=450634),里面直接将上面给出的解决方法直接贴到了论坛了，方法如下：

    安装新立德软件包管理器：打开终端，输入以下命令：sudo apt-get install synaptic
    打开新立德软件包管理器，选择“设置>软件库”
    选择“其他软件 > 添加”
    在APT行中输入 "deb http://archive.ubuntu.com/ubuntu/ raring main restricted universe multiverse"
    选择确定退出新立德软件包管理器
    在终端输入“sudo apt-get update”
    在终端输入“sudo apt-get install ia32-libs”
    
新立德自带的就有，于是直接从“添加”开始。在最后一步的时候，提示错误：

    #无法修正错误，因为您要求某些软件包保持现状，就是它们破坏了软件包间的依赖关系
    
然后就找到了这篇[文章](http://www.cnblogs.com/LeoGodfrey/p/3316834.html)，说是源的问题，让打开软件和更新，在“更新”选项卡中选则：重要安全更新 和 推荐更新，然后在“其他软件”选项卡中，去掉有问题等源。最后进行“sudo apt-get update”操作。但问题是我不知道什么是属于“有问题的源”。我尝试在“其他软件”中删除一个源，发现“其他软件”中有的源显示“已禁止升级到……”，然后就google，找到了这篇[文章](https://wiki.ubuntu.org.cn/viewtopic.php?f=48&t=415960),说：

    说明这2个源还不支持新版本。被禁止了。
    cd /etc/apt/sources.list.d/ 里面直接删除就是。

然后，我就进入目录删掉了一个，使用如下的命令：

    sudo rm fingerprint-fingerprint-gui-raring.list

在“其他软件”中发现少了一个“已禁止……”，于是就删掉了所有后缀是 list 的，查看“其他软件”，已经没有“有问题的源”了。

然后继续执行 apt-get Update 步骤，出现了错误：

    W: 无法下载 gzip:/var/lib/apt/lists/partial/archive.ubuntu.com_ubuntu_dists_raring_main_binary-i386_Packages Hash 校验和不符
    E: Some index files failed to download. They have been ignored, or old ones used instead.
    
然后搜索问题，找到了这篇[文章](https://wiki.ubuntu.org.cn/viewtopic.php?f=48&t=424986&p=2980527),说直接执行如下命令：

    sudo rm /var/lib/apt/lists/* -vf
    sudo apt-get update
    
我试了一下，还不行（出现的是什么问题我忘记了，可能还是上面的问题）！就找到了这篇[文章](http://forum.ubuntu.org.cn/viewtopic.php?f=77&t=424280),说执行如下命令：

    sudo rm -rf /var/lib/dpkg/updates/
    sudo rm -rf /var/lib/apt/lists
    sudo apt-get update -o APT::Cache-Limit=0
    sudo dpkg --clear-avail
    sudo dpkg --configure -a
    sudo apt-get -f install
    sudo apt-get --fix-missing install
    sudo apt-get update -o APT::Cache-Limit=0
    sudo apt-get dist-upgrade
    sudo apt-get update

当我执行到“ sudo dpkg --configure -a ”这一步时，出现错误：

    dpkg: error: 无法扫描更新目录 /var/lib/dpkg/updates/
    #我用下面命令查看
    cd /var/lib/dpkg/
    #发现果然没有 updates 目录
    
google这个错误，找到了这篇[文章](http://bbs.94yun.com/forum.php?mod=viewthread&tid=1306),说直接来：

    sudo mkdir /var/lib/dpkg/updates
    #实在不行就再来：
    sudo chmod 777 /var/lib/dpkg/updates
    
我只进行了第一步，然后尝试继续“ sudo dpkg --configure -a ”，ok了，然后接着执行“ sudo apt-get -f install ”，直至 update。然后开始安装32位库了吧：

    sudo apt-get install ia32-libs
但又出现错误：

    ……/var/cache/apt/archives/libglib2.0-0_2.38.0-1ubuntu1_i386.deb……
    Sub-process /usr/bin/dpkg returned an error code (1)
然后我用“ Sub-process /usr/bin/dpkg returned an error code (1) ”搜索，然后找到了[这篇文章](http://forum.ubuntu.org.cn/viewtopic.php?f=86&t=90547),说：

    有的时候，使用sudo apt-get install可能导致意想不到的错误，尤其是中途中断了安装时，错误信息为：
    E: Sub-process /usr/bin/dpkg returned an error code (1)
    此时可以这样解决：
    cd /var/lib/dpkg
    sudo mv info info.bak
    sudo mkdir info
    重新安装，在此为：
    sudo apt-get --reinstall install ×××××
    
然后，我就按上面的执行，然后执行 reinstall :

    sudo apt-get --reinstall install ia32-libs
顺利安装。
接着尝试打开 Scrivener 和 WPS ，均能正常打开。很好，问题解决了，但被我删掉的那些源怎么办？包含输入法 fcitx 和指纹扫描等的源。

