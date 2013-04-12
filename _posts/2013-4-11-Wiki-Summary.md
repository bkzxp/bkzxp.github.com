---
layout : post
category : lessons
tags : [Wiki]
title : 使用Wiki后的总结
---


<div><ul>
	<li>
		<div>使用Wiki后的总结</div>
		<ul>
	<li><div >说明</div>
		<ul>
	<li><div>在Redmine中使用Wiki编辑文档后，我想整理下在编写过程中所遇到的Wiki知识。后来在网上搜了搜，了解了更多的wiki知识，以我自己的理解，写下这篇文章。望对wiki理解深刻的TX围观、留言。</div></li></ul></li>
	<li><div >Wiki知识</div>
		<ul>
	<li><div >我的探索过程</div>
		<ul>
	<li><div>在了解Redmine中的wiki时，发现了这篇文章“<a href="http://redmine.ossxp.com/redmine/documents/8">Redmine wiki的文本格式</a>”，其中提到“Redmine默认使用Textile作为wiki的文本格式过滤器, 当然你也可以下载其他文本格式过滤器插件(Markdown, reST等),以下介绍的语法都是基于Textile的语法”。等一等，难道Wiki自己没有语法吗？他的意思是Redmine也可以使用Markdown来作为Wiki的文本格式过滤器吗？我们知道Markdown是有自己的语法的，那么Wiki到底是个什么？</div></li></ul></li>
	<li><div>什么是wiki？</div>
		<ul>
	<li><div>Wiki是软件、系统？是语法概念？还是一种语言？刚接触wiki的时候搞不明白它到底是什么，我们看看</div>
<ul>
	<li><div>维基百科给出的<a href="https://zh.wikipedia.org/wiki/Wiki">解释</a>：Wiki 是一种在网络上开放且可供多人协同创作的超文本系统，由沃德·坎宁安于1995年首先开发。沃德·坎宁安将Wiki定义为“一种允许一群用户利用简单的描述来创建和连接一组网页的社会计算系统”。</div></li>
	<li><div>百度百科的<a href="http://baike.baidu.com/view/737.htm">说法</a>：Wiki指一种超文本系统，这种超文本系统支持面向社群的协作式写作，同时也包括一组支持这种写作的辅助工具。</div></li>
</ul>

	</li></ul></li>
	<li><div>wiki语法？wiki到底有没有语法？</div>
		<ul>
	<li><div>还在纠结wiki是否有语法吗？</div></li>
	<li><div>维基百科在词条Wiki的特征中<a href="https://zh.wikipedia.org/wiki/Wiki">提到</a>：沃德·坎宁安和波·路夫（Bo Leuf）在《The Wiki Way: Quick Collaboration on the Web》一书中描述了Wiki概念的几个本质特征：</div>
		<ul>
	<li><div>Wiki允许任何用户在Wiki网站内剪辑任何页面或新建页面，不需要任何额外的附加组件，只需通过普通的网页浏览器即可。</div></li>
	<li><div>Wiki中用户使用很多方式来编辑。通常需要通过文本标记语言。</div></li></ul></li>
	<li><div>终于发现了，编辑Wiki是需要其他语言来实现的（如Markdown、Textile）。So,Wiki不是一种语言，其实也就没有所谓的Wiki语法，通常说的Wiki的语法就是指编辑维基百科的Wiki时用的语法，而维基百科是用“<a href="http://zh.wikipedia.org/wiki/MediaWiki">MediaWiki</a>”的<a href="http://zh.wikipedia.org/wiki/Help:%E7%BC%96%E8%BE%91%E9%A1%B5%E9%9D%A2">语法</a>。</div></li>
	<li><div>Wiki是一种技术。</div></li></ul></li>
	<li><div>认识Textile、markdown等</div>
		<ul>
	<li><div>他们是“轻量级的标记语言”，可以在wiki中<a href="http://forum.libracafe.com/comments.php?DiscussionID=107">使用</a></div></li></ul></li>
	<li><div>mediawiki、Dokuwiki等是什么</div>
		<ul>
	<li><div><a href="http://zh.wikipedia.org/wiki/Wiki%E5%BC%95%E6%93%8E">Wiki引擎</a></div></li></ul></li></ul></li>
	<li><div >Textile 语法</div>
		<ul>
	<li><div><a href="http://www.lfhacks.com/textile-syntax">http://www.lfhacks.com/textile-syntax</a></div></li>
	<li><div><a href="http://qt-project.org/wiki/TextileSyntax_SimplifiedChinese#6ba7a320100686b22f39ce180e0df716">http://qt-project.org/wiki/TextileSyntax_SimplifiedChinese#6ba7a320100686b22f39ce180e0df716</a></div></li></ul></li>
	<li><div >编辑Redmine中Wiki</div>
		<ul>
	<li><div>增加Wiki</div>
		<ul>
	<li><div>http://您的IP地址:您的端口/projects/项目标识/wiki/新建的wiki的名称。也可以这样说，当你打开Wiki后，直接在地址栏的“***/wiki/”后面写上你准备新建的wiki的名称，回车即完成了新建过程。</div></li></ul></li>
	<li><div>编辑Wiki</div>
		<ul>
	<li><div>引用</div>
		<ul>
	<li><div>对同目录的其他wiki文件的引用，使用：\{\{include(projectname:Foo)\}\}</div></li></ul></li>
	<li><div>表格</div>
		<ul>
	<li><div>通常使用</div>
		<ul>
	<li><div><code>|_.UserID|_.Name|_.Group|</code>：下划线以及点号，表明了该行是表格表头行；把下划线以及点号去掉，就是普通行。另外一种也可以，就是使用*号，如<br /> <code>|*NO*  |*接口名称* |	*用途说明*|</code></div></li></ul></li>
	<li><div>单元格单行横向合并</div>
		<ul>
	<li><div><code>|\3=.IT|</code>：3表示合并的单元格的个数，英文标点点号与管道符之间的文字为该单元格的内容</div></li></ul></li>
	<li><div>单元格单列纵向合并</div>
		<ul>
	<li><div><code>
      |5|张三|/2.Users|
    <br />
      |6|李四|  </code>  2表示纵向合并的个数
    </div></li></ul></li>
	<li><div>臆想</div>
		<ul>
	<li><div>纵向横向一起合并，我摸索了半天，没弄出来，用户手册也没有给出方法</div></li></ul></li></ul></li>
	<li><div>文字样式</div>
		<ul>
	<li><div>标题</div>
		<ul>
	<li><div><p>
      h1. 一级标题
    </p><p>
      h2. 二级标题
    </p><p>
      h3. 三级标题
    </p></div></li></ul></li>
	<li><div>文字颜色</div>
		<ul>
	<li><div><code>{background:#999}.</code>别忘了加英文的点号</div></li>
	<li><div><code>{color:#999}.</code>别忘了加英文的点号</div></li>
	<li><div><a href="http://blog.chinaunix.net/uid-1877180-id-1740096.html">http://blog.chinaunix.net/uid-1877180-id-1740096.html</a></div></li></ul></li>
	<li><div>缩进</div>
		<ul>
	<li><div>用户手册中并没有讲如何缩进，使用半角空白字符是不起作用的，使用全角的空格字符倒是可以实现缩进。</div></li></ul></li></ul></li>
	<li><div>图片</div>
		<ul>
	<li><div><code>!{width:300px}image_url!</code> 设置图片的显示宽度</div></li></ul></li></ul></li></ul></li>
	<li><div >备注</div>
		<ul>
	<li><div>不完全相同的语法</div>
		<ul>
	<li><div>标记语言间</div>
		<ul>
	<li><div>毫无疑问，不同语言间的语法本来就不一样，但是因为他们隶属于轻量级的标记语言，所以在语法的形式上体现出一定的相似性</div></li></ul></li>
	<li><div>Wiki引擎间</div>
		<ul>
	<li><div><a href="https://www.dokuwiki.org/zh:wiki:syntax">DokuWiki</a>的删除线格式是“<code>&lt;del&gt;删除线&lt;/del&gt;</code>”，MediaWiki的则是“<code>&lt;strike&gt;删除线&lt;/strike&gt;</code>,<code>&lt;s&gt;简易删除线&lt;/s&gt;</code>”</div></li></ul></li>
	<li><div>这就解释了：为什么我最初把mediawiki生成表格的示例贴到textile(Redmine的Wiki)中，不能生成表格</div></li></ul></li>
	<li><div>是谁确定了wiki引擎的基本语法？</div>
		<ul>
	<li><div>如：不同wiki引擎，*，**，***，#，##，###等表示的意思大体都是一样的</div></li></ul></li>
	<li><div>Redmine中的Textile的语法还是比较简单的，相比mediawiki、Dokuwiki引擎</div></li>
	<li><div>比较Wiki引擎</div>
		<ul>
	<li><div><a href="http://www.wikimatrix.org/index.php">http://www.wikimatrix.org/index.php</a></div></li>
	<li><div><a href="http://www.wikimatrix.org/show/dokuwiki">http://www.wikimatrix.org/show/dokuwiki</a></div></li>
	<li><div><a href="http://linux.cn/thread/7113/1/1/">http://linux.cn/thread/7113/1/1/</a></div></li></ul></li>
	<li><div>Redmine用户手册：<a href="http://www.ossxp.com/doc/redmine/user_guide/user_guide.html#id32">http://www.ossxp.com/doc/redmine/user_guide/user_guide.html#id32</a></div></li></ul></li></ul></li></ul></div>