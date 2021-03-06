---
layout : post
category : lessons
tags : [整理, 正则]
title : 正则替换工具对正则的支持
---

 ~~本文还未彻底完成，文中的链接暂时是无效的~~
 
  *注本文是整理性文章，非记录性文章(2013.4.20 plan~2013.5.6 done)*
  
 最近领导说让把PHP代码的注释部分生成Wiki放到Redmine上面。而Redmine上面的Wiki是有一定的格式的。而把PHP代码的注释部分提取出来是很简单的，使用PHPDocumentor就可以。而PHPDocumentor生成的是Web格式、HTML代码。于是我就有必要写一套（Redmine下的）Wiki样式的模板。
 
 于是就在 phpDocumentor\Converters\HTML\Smarty\templates 下，将PHP目录复制了一份，该名称为Wiki，并且准备把Wiki目录里面的模板改成Wiki可识别的形式。
 
 在我了解了Wiki后([详见文章](http://bkzxp.github.io/lessons/2013/04/11/Wiki-Summary/))，便把Wiki目录里面的相关模板的HTML标签去掉（关于PHP形式中各个模板的关系详见[这篇文章](http://bkzxp.github.io/lessons/2013/05/08/PhpDocumentor-Tpls/)），因为Wiki语法并不是标签样式的；然后，使用命令
 
     -o HTML:Smarty:Wiki    
     
来生成页面；接着在页面代码中使用正则来匹配替换。

 一下子生成了好多页面，所以需要使用工具来进行替换，对于工具的选择，希望能够支持以下条件：
 
 1. 正则匹配替换
 2. 针对多文件查找替换
 3. 多目录查找替换
 4. 自定义文件类型
 5. 字符编码支持（不会出现乱码）
 6. 操作简单（当然了）
 7. 最好有一键还原（不用事先备份文件）
 8. ……（很多）
 
所以呢，就在网上找了点小软件，下面一个一个地说：
 
 - [Search and Replace](http://vdisk.weibo.com/s/BoFC5)(版本6.5) 
    + 功能：证词匹配、搜索子目录、正则、忽略空格、更改文件属性、脚本等
    + 使用了一下，开始感觉好强大，但当我需要进行正则中的[零宽断言](http://baike.baidu.com/view/5201192.htm)时，发现它不支持，而我又是必须使用的，那就换一个
 - [RegexTester](http://vdisk.weibo.com/s/BoGnv)(版本1.0.8.0)
    + 该软件是[deerchao的blog](http://www.cnblogs.com/deerchao/archive/2006/08/24/zhengzhe30fengzhongjiaocheng.html#balancedgroup)中推荐的正则表达式测试软件。.Net Framework 4.0 下正则表达式的行为。
    + 功能：查找替换（可以忽略大小写、空白，显示匹配）
    + 查找替换对象必须为文本，不能是文件
    + 该软件作为日常的正则校验是可以的，但是文本文件替换，还是算了吧
 - [UltraReplace.exe](http://vdisk.weibo.com/s/BoGKL)(版本5.0.2)
    + 好强大功能：目录、文件下查找替换，文件后缀，特征替换、批量替换、恢复（回滚），区分大小写，替换前备份等
    + 我在做这个替换任务的时候，最开始用的就是这个。但，当我需要使用特殊的正则时，它就不支持了，如零宽断言。于是，我就继续寻找满足我要求的小工具。
    + 如果你只使用普通的正则，我仍推荐你用这个。
 - SuperTextReplace.exe(V3.0)(安装版的，就不给链接了)
    + 功能：基本功能都有，并且，界面上我认为和 UltraReplace 类似，但是没有后者强大
    + 使用了几下，感觉操作不舒服，于是就放掉了，也不支持零宽断言
 - PilotEdit(安装版的，就不给链接了)
    + 功能蛮强大的，但是我不喜欢它的操作界面和方式。也不支持零宽断言。
 - [Bulk Rename Utility](http://vdisk.weibo.com/s/BoHfj)(版本2,7,1,2)
    + 不得不说，它与上面几个小工具都不太一样。同时也具备强大文件重命名的功能。我在做这个任务时使用到了这个软件，但是遗憾的是，也不支持零宽断言。
    + 它的界面有好多框、按钮。所以，功能才很强大。

就当我走投无路的时候，突然想到Sublime编辑器上就支持正则，于是写了一个简单的零宽断言的正则，试了一下，Yes，恰巧，Sublime还可以对多个目录中的文件操作。于是，问题解决了。

如果，以后需要文件中文本替换，我想我还是会选择 UltraReplace，会把Sublime放在一边的，毕竟前者是专门的替换工具。
