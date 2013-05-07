---
layout : post
category : lessons
tags : [整理]
title : Phpdocumentor Smarty-PHP模板中各个Tpl之间关系
---


*本文主要讲 Phpdocumentor Smarty 中 PHP 模板中各个 Tpl 文件之间的关系。*

*(2013.4.20 plan~2013.5.8 done)*

前一段时间领导有一个要求，要把 PHP 项目代码里面的注释弄到 Redmine 的 Wiki 里面，而当时的注释风格是为了使用的 Phpdocumentor 进行导出的，于是就创建了一套符合 Wiki 语法的模板，至于它的样式，还是 Phpdocumentor 默认的样式。

说是创建，只不过是把目录 php5.2.8\data\PhpDocumentor\phpDocumentor\Converters\HTML\Smarty\templates 下的 PHP 文件夹备份一份，并重命名为 Wiki。这样我更改 Wiki 目录里面的 tpl 模板的代码，就能生成符合 Wiki 语法的文件了。在使用 phpdoc 命令时，参数

    -o HTML:Smarty:Wiki

有人会问，为什么不一步到底呢？直接生成文件，传到 Redmine 里面？这个问题要从两点说起，第一，我没权限，我能做的是把代码粘贴到 Redmine 中相应的 Wiki 文件里面。第二，原本的注释写的并不是非常规范，在我执行了 phpdoc 命令生成一大堆文件后，我还要对这些文件中的代码进行查找替换（替换工具的选择，可以参看[这篇文章](http://bkzxp.github.io/lessons/2013/05/03/Regex-Tools/)），来使它们满足Wiki的语法，并且呈现出良好的阅读体验（就是样式的问题啦）。赶快进入正题。

先列出来有哪些模板文件

 - examplesource.tpl
 - filesource.tpl
 - ric.tpl
 - tutorial.tpl
 - tutorial_toc.tpl
 - tutorial_tree.tpl
 - index.tpl
 - page.tpl
 - class.tpl
 - todolist.tpl
 - classtrees.tpl
 - elementindex.tpl
 - pkgelementindex.tpl
 - errors.tpl
 - fileleft.tpl
 - classleft.tpl
 - header.tpl
 - footer.tpl 
 - blank.tpl
 - function.tpl
 - define.tpl
 - docblock.tpl
 - packages.tpl
 - include.tpl
 - global.tpl
 - var.tpl
 - method.tpl
 - const.tpl
 - basicindex.tpl

从两个方面说。

 1. 各个Tpl模板间的 include 关系
    - 代码中直接写明了 include 其他 tpl 文件的那些文件(我就用->表示吧)
        * index -> header  black  footer (省去了后缀 tpl 以及点.，下同)
        * page -> header  black  footer 
        * class -> header docblock var method const footer
        * todolist -> header footer
        * classtrees -> header footer
        * elementindex -> header basicindex footer
        * pkgelementindex -> header basicindex footer
        * errors -> header footer
        * examplesource -> header footer
        * filesource -> header footer
        * ric -> header footer
    - 需要特别说明的是：以下几个 tpl 文件同时 include 了 docblock.tpl 模板
        * include
        * global
        * define
        * function
        * var
        * method
        * const
    - 其他的 tpl 文件则是被包含的 tpl。以上就是它们在模板中的关系。
 2. 在执行 phpdoc 命令生成文件后，页面间的关系
    - index.html 页面 使用的是 index.tpl 模板
    - 左侧的 Files 列表、Classes 列表分别对应 fileleft.tpl、classleft.tpl，而 header.tpl 暗暗地 include 了这两个 tpl 文件
    - 左侧的 Files 列表中的链接，打开的是 page.tpl 对应的模板
    - 左侧的 Classes 列表中的链接，打开的是 class.tpl 对应的模板
    - 右上角的 classtrees、index、all elements 分别对应模板 classtrees.tpl、pkgelementindex.tpl、elementindex.tpl
    - 其他的 error.html、todolist.html 就不用说了，它们是单独的页面。
    - 在 header.tpl 中 发现了 和 tutorial.tpl、tutorial_toc.tpl、tutorial_tree.tpl 相关的代码。我在完成该任务的过程中并没有生成使用 tutorial.tpl 的文件，具体还不太清楚。

写这篇文章是为了方便了解各个模板之间的关系，也方便以后更改生成文件的模板格式。
