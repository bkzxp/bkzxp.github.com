---
layout : post
category : lessons
tags : [整理]
title : 正则替换工具对正则的支持(1)
---


 *本文还未完成，链接页面还未添加*
 
  ~~注本文是整理性文章，非记录性文章~~
  
 最近领导说让把PHP代码的注释部分生成Wiki放到Redmine上面。而Redmine上面的Wiki是有一定的格式的。而把PHP代码的注释部分提取出来是很简单的，使用PHPDocumentor就可以。而PHPDocumentor生成的是Web格式、HTML代码。于是我就有必要写一套（Redmine下的）Wiki样式的模板。
 
 于是就在 phpDocumentor\Converters\HTML\Smarty\templates 下，将PHP目录复制了一份，该名称为Wiki，并且准备把Wiki目录里面的模板改成Wiki可识别的形式。
 
 在我了解了Wiki后([详见文章](http://bkzxp.github.io/lessons/2013/04/11/Wiki-Summary/))，便把Wiki目录里面的相关模板的HTML标签去掉（关于PHP形式中各个模板的关系详见[这篇文章](http://www.xx.com)），因为Wiki语法并不是标签样式的；然后，使用命令
 
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
 
 - Search and Replace(版本6.5) 
  + 功能：证词匹配、搜索子目录、正则、忽略空格、更改文件属性、脚本等
  + 使用了一下，开始感觉好强大，但当我需要进行正则中的[零宽断言](http://baike.baidu.com/view/5201192.htm)时，发现它不支持，而我又是必须使用的，那就换一个
 - RegexTester(版本1.0.8.0)
  + 该软件是[deerchao的blog](http://www.cnblogs.com/deerchao/archive/2006/08/24/zhengzhe30fengzhongjiaocheng.html#balancedgroup)中推荐的正则表达式测试软件
