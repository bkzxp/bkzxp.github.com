---
layout : post
category : lessons
tags : [软件功能说明书]
title : 历次的软件功能说明书1
---

*回顾书写软件功能说明书的历史，整理总结先前的问题*

第一份写的软件功能说明书是“仓储信息管理平台”。

文档的第一章是钱文豪写的，给我指定了书写的大纲和方向。当时的配图来自xmind的结构图截图。

在第一章的功能列表中，能够点击功能名称跳转到相应的功能描述，这一点功能在以后的两份说明书中被遗失了。以后要添加上。

在角色列表中只列出了角色与模块之间的访问关系，并没有体现出角色对功能点的控制关系。在写这几份功能说明书时，以及实际开发时，一个角色并非控制了某一个模块，往往是控制多个模块，并且也不是有权限控制模块中的所有功能。所有，有必要通过一种方法来展示出角色关系，通常的角色结构图已经无法有效展示问题了。我考虑，使用一个二维表格能够将信息更好地展示，但是界面上不容易体现。

第二章的功能描述中的图例都是使用Axure画的，界面相当丑。虽然图形的主要目的是为了告诉界面设计人员界面上的元素，但是也需要美观。