---
layout : post
category : lessons
tags : [文档书写]
title : 软件功能说明书书写
---

<div><ul>
	<li><div style="background-color:#ff0000;">软件功能说明书书写</div>
		<ul>
	<li><div>注</div>
		<ul>
	<li><div>本说明针对模板文件〖TG-IT(AA03)〗软件功能说明书.doc 新浪微盘 http://vdisk.weibo.com/s/mtOTA</div></li>
	<li><div>对取消掉的部分应该把标题灰掉</div></li>
	<li><div>排版要好，才显专业</div></li></ul></li>
	<li><div style="background-color:#9999ff;">应用架构</div>
		<ul>
	<li><div style="background-color:#ccccff;">业务划分</div>
		<ul>
	<li><div style="background-color:#00ffcc;">HSF图例</div>
		<ul>
	<li><div>每个业务的功能点要从业务分析说明书中获取；</div></li>
	<li><div>先确定业务点，然后在每一个业务点中再确定功能点；</div></li>
	<li><div>功能点的命名动宾/主谓关系要保持一致；名字的字数要尽可能保持一致，如：都是4个字，或都是6个字；不要使用能让用户误解的字词；名字命名时避免大、空，要贴切功能点；</div></li></ul></li>
	<li><div style="background-color:#00ffcc;">功能列表</div>
		<ul>
	<li><img src="软件功能说明书书写.html_files/icons/yes.png" alt="yes"/> <div style="background-color:#ffcccc;">用途说明</div>
		<ul>
	<li><div>用途说明：使用用户的口吻描述该功能的用途；描述通过使用该功能能够完成什么样的工作；如果需要，还需指明操作的数据内容、操作方式等，但不限于这两个；最好，写出功能点在业务分析说明书中的出处；表达描述中，不能让业务人员无法理解；</div></li></ul></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">权限控制</div>
		<ul>
	<li><div style="background-color:#00ffcc;">RRF图例</div></li>
	<li><div style="background-color:#00ffcc;">角色列表</div>
		<ul>
	<li><div style="background-color:#ffcccc;">用户类型</div>
		<ul>
	<li><div>项目有哪些人使用</div></li></ul></li>
	<li><div style="background-color:#ffcccc;">职能说明</div>
		<ul>
	<li><div>能够做哪些操作</div>
		<ul>
	<li><div>列出功能点</div></li></ul></li></ul></li></ul></li>
	<li><div>注</div>
		<ul>
	<li><div>先进行权限控制的书写，最好的方法是从项目使用者的角色入手；角色确定以后， 业务划分中的HSF图就可以根据这些角色来分出大的业务块；</div></li></ul></li></ul></li></ul></li>
	<li><div style="background-color:#9999ff;">功能描述</div>
		<ul>
	<li><div style="background-color:#ccccff;">业务点</div>
		<ul>
	<li><div style="background-color:#00ffcc;">功能点</div>
		<ul>
	<li><img src="软件功能说明书书写.html_files/icons/yes.png" alt="yes"/> <div style="background-color:#ffcccc;">应用场景</div>
		<ul>
	<li><div>使用用户的口吻描述该功能的场景；在什么情况下会使用该功能点；场景可能不止一个；如果多角色使用该功能点，则要分开进行描述，因为不同角色使用的重点内容不同；“应用场景”是对功能点最重要的描述；</div></li></ul></li>
	<li><div style="background-color:#ffcccc;">参考界面</div>
		<ul>
	<li><div>参考界面能够帮助文档阅读者更好理解功能点；</div></li>
	<li><div>并不是每一个功能点都需要有界面；</div></li>
	<li><div>当然，一个功能点的参考界面也可能不止一个；</div></li></ul></li>
	<li><div style="background-color:#ffcccc;">特性说明</div>
		<ul>
	<li><div>特性说明：书写该功能点能够支持哪些特性、不支持哪些特性；最好能够分为三部分：支持、暂不支持、无需支持；把当前不支持的以后会支持的项写入到暂不支持中；同时，书写者应该能够讲的出为什么支持某些项、为什么不支持某些项；</div></li>
	<li><div>查询时，书写“按时间进行查询”的意思就是：查询结果按照时间进行分组；如果不是要表达分组这个意思，就应该换成其他的，如：将时间作为查询条件来查找数据</div></li></ul></li>
	<li><div style="background-color:#ffcccc;">相关信息</div>
		<ul>
	<li><div>描述的是信息实体；列出信息实体的具体内容；</div></li></ul></li>
	<li><div style="background-color:#ffcccc;">注意事项</div>
		<ul>
	<li><div>注意事项则是对特性说明的注释；不能列到特性说明的，并且需要指出的，就应该写到注意事项中；特性中的一些规则性的东西也要写到注意事项中；</div></li></ul></li>
	<li><div> 用途说明和应用场景的区别</div>
		<ul>
	<li><div>都要从业务用户的角度描述</div></li>
	<li><div>用途说明重点在于：用户使用某个功能点时系统能够帮用户完成“什么”样的工作；描述中应多使用“来”、“以”、“以便”、“能够”……这样的词；“什么”样的工作是指“用户”的工作，如：管理员可以查询已经记录下的日志，来分析用户操作情况，分析系统对外提供的服务情况；</div></li>
	<li><div>应用场景重点在于：用户在什么样的场景下使用某功能点；如：当有新的仓库加盟到平台时，使用“仓库管理”添加仓库信息、仓库系统访问地址，使仓库系统和平台能够进行数据通讯，完成仓库信息的初始化；<br/>同时，在场景中也要写出系统是如何完成这个过程的；</div></li></ul></li></ul></li></ul></li></ul></li>
	<li><div style="background-color:#9999ff;">对外接口</div>
		<ul>
	<li><div style="background-color:#ccccff;">系统交互</div>
		<ul>
	<li><div style="background-color:#00ffcc;">DSI图例</div></li>
	<li><div style="background-color:#00ffcc;">接口列表</div>
		<ul>
	<li><div style="background-color:#ffcccc;">接口名称</div></li>
	<li><div style="background-color:#ffcccc;">用途名称</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">接口名称</div>
		<ul>
	<li><div style="background-color:#00ffcc;">API图例</div></li>
	<li><div style="background-color:#00ffcc;">协议列表</div>
		<ul>
	<li><div style="background-color:#ffcccc;">协议名称</div></li>
	<li><div style="background-color:#ffcccc;">用途说明</div></li></ul></li></ul></li>
	<li><div>注</div>
		<ul>
	<li><div>还没有书写还不清楚有哪些注意事项；</div></li></ul></li></ul></li></ul></li></ul></div>