---
layout : post
category : lessons
tags : [文档书写]
title : 统计反馈
---


<div><ul>
	<li><div style="background-color:#ff0000;">统计反馈</div>
		<ul>
	<li><div style="background-color:#9999ff;">文档作用</div>
		<ul>
	<li><div>提供给大家统计反馈的情况</div></li></ul></li>
	<li><div style="background-color:#9999ff;">下载地址</div>
		<ul>
	<li><div><a href="http://vdisk.weibo.com/s/vY7Zj" title="新浪微盘">Hi，推荐文件给你 "统计反馈V2.1.xls"</a></div></li></ul></li>
	<li><div style="background-color:#9999ff;">使用说明</div>
		<ul>
	<li><div style="background-color:#ccccff;">一.阅读</div>
		<ul>
	<li><div>统计表中蓝色数字是该列中最大值；</div></li>
	<li><div>统计表中灰色背景是完成了月指标15个；</div></li>
	<li><div>查阅反馈者的记录个数：从“反馈者”的列找到反馈者名字，再在相应的“反馈个数”列查找；	 </div></li>
	<li><div>查阅被反馈的名字次数：	 从“被反馈的名字”的列找到名字，再在相应的“被反馈次数”列查找；	</div></li></ul></li>
	<li><div style="background-color:#ccccff;">二.使用</div>
		<ul>
	<li><div>打开Redmine的反馈列表，页码切到第一页，并使每页显示100条记录；	 </div></li>
	<li><div>键盘操作，Ctrl+C复制整个网页页面，打开本excel，打开工作薄“1”，右键点击第0行第0列的单元格（左上角的那格），选择“粘贴为无文本格式”； 	 </div></li>
	<li><div>重复第2个步骤，把页面反馈列表的第2页、第3页数据粘贴到工作薄“2”、工作簿“3”中；	 </div></li>
	<li><div>若上述2、3步骤只使用了工作簿“1”，则需要清空工作薄“2”、“3”里面的数据。确保工作簿“1”、“2”、“3”中保留的数据是你需要的；	 </div></li>
	<li><div>切到工作簿“0”,就能看到统计结果了。	 </div></li></ul></li>
	<li><div style="background-color:#ccccff;">三.姓名变动</div>
		<ul>
	<li><div>删除的话，把所在行的8个单元格删掉，并使下方的单元格上移即可；	 </div></li>
	<li><div>新增的话，把左右两侧的“可填”改成相应的姓名即可；	 </div></li></ul></li>
	<li><div style="background-color:#ccccff;">四.注意必读</div>
		<ul>
	<li><div>姓名变动时，不要删除excel的整行，会把右侧的使用说明也删掉；	 </div></li>
	<li><div>统计名字时，只统计到第20行，若新增姓名太多，请联系作者修改excel；	</div></li>
	<li><div>第一列“反馈者”中的姓和名之间有一个空格，而“被反馈的名字”列中的姓和名之间没有空格；	 </div></li>
	<li><div>统计被反馈的名字的次数时，是严格按照所列出的“被反馈的名字”统计的， 即某些记录是反馈“雪培”、“张雪佩”的，就不会记到“张雪培”的被反馈次数上；</div></li>
	<li><div>请确保第二条“使用”中的第4步操作，使数据完整，否则会造成统计结果完全无效！	 </div></li>
	<li><div>可修改“当前日期”中的日期，使表格完成相应的统计，但统计结果可能无效！请确保数据完整性！	 </div></li></ul></li>
	<li><div style="background-color:#ccccff;">五.备注</div>
		<ul>
	<li><div>为何只有3个工作簿？300条反馈记录足够统计一个月的了。</div></li>
	<li><div>不能保证上月、上上月、……的反馈记录是完整的。	 </div></li></ul></li></ul></li>
	<li><div style="background-color:#9999ff;">涉及的函数</div>
		<ul>
	<li><div style="background-color:#ccccff;">TODAY()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>返回当前日期的序列号。序列号是 Excel 日期和时间计算使用的日期-时间代码。如果在输入函数前，单元格的格式为“常规”，Excel 会将单元格格式更改为“日期”。如果要查看序列号，则必须将单元格格式更改为“常规”或“数值”。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HP010342958.aspx">http://office.microsoft.com/zh-cn/excel-help/HP010342958.aspx</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>获取当前日期</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">FIND()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>FIND 用于查找其他文本字符串 (within_text) 内的文本字符串 (find_text)，并从 within_text 的首字符开始返回 find_text 的起始位置编号。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HP005209089.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HP005209089.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>FIND("RE",某区域,1)：查找主题是对反馈的回复的条目（回复的主题中包含“RE”）</div></li>
	<li><div>FIND(某单元格,某区域)：查找反馈的主题中包含“被反馈的名字”的条目</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">COUNTIF()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>计算区域中满足给定条件的单元格的个数。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HP005209029.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HP005209029.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>最初使用该方法统计的，发现不能使用多个条件</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">COUNTIFS()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>将条件应用于跨多个区域的单元格，并计算符合所有条件的次数。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102753238.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102753238.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>使用该函数时，发现不能满足一些特定条件的查找</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">SUMPRODUCT()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>在给定的几组数组中，将数组间对应的元素相乘，并返回乘积之和。数组参数必须具有相同的维数。 否则，函数 SUMPRODUCT 将返回 #VALUE! 错误值 #REF!。 函数 SUMPRODUCT 将非数值型的数组元素作为 0 处理。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102752853.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102752853.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>SUMPRODUCT((条件1)*(条件2)*(条件3)* …(条件n))，统计同时满足条件1、条件2到条件n的记录的个数。更多更强大使用的方法参见：<a href="http://blog.sina.com.cn/s/blog_4d712530010176u9.html">http://blog.sina.com.cn/s/blog_4d712530010176u9.html</a></div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">EOMONTH()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>返回指定月份数之前或之后的月份的最后一天的日期，该日期采用 datetime 格式。EOMONTH 可用于计算处于月份最后一天的到期日期。<a href="http://office.microsoft.com/zh-cn/excel-help/HA102837740.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102837740.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>使用该函数，确保某些反馈是在同一个月中的</div></li>
	<li><div>使用该函数获得当前月份的第一天</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">YEAR()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>以 1900-9999 范围的四位整数形式返回日期的年份。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102837739.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102837739.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>确保反馈时间是在同一年的（这点貌似没必要）</div></li>
	<li><div>获取当前的年份</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">ISERROR()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>检查某个值是否为错误，并且返回 TRUE 或 FALSE。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102838076.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102838076.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>FIND函数查找不到数据时，会返回“#VALUE!”，需要通过ISERROR()函数来判断</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">WEEKNUM()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>根据 return_type 值返回给定日期和年份的周数。周数指示该周在数字上属于一年中的何处。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102838299.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102838299.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>在统计一周的数据时，确保某些数据在同一周内。</div></li>
	<li><div>该函数在文档中使用的return_type是2</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">IF()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>如果指定条件的计算结果为 TRUE，IF 函数将返回某个值；如果该条件的计算结果为 FALSE，则返回另一个值。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HP010342586.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HP010342586.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>获取当前的几个工作薄中的最小日期，进行了判断</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">MIN()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>返回列中的最小数值。忽略逻辑值和文本。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102839077.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102839077.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>获取当前的几个工作薄中的最小日期。</div></li></ul></li></ul></li>
	<li><div style="background-color:#ccccff;">MONTH()</div>
		<ul>
	<li><div>方法：</div>
		<ul>
	<li><div>将月份返回为从 1（1 月）到 12（12 月）的数字。更详细参见：<a href="http://office.microsoft.com/zh-cn/excel-help/HA102838119.aspx?CTT=1">http://office.microsoft.com/zh-cn/excel-help/HA102838119.aspx?CTT=1</a></div></li></ul></li>
	<li><div>文档中：</div>
		<ul>
	<li><div>获取当前月份</div></li></ul></li></ul></li></ul></li>
	<li><div style="background-color:#9999ff;">在制作过程中注意到的</div>
		<ul>
	<li><div style="background-color:#ccccff;">混合引用</div>
		<ul>
	<li><div>参见：<a href="http://www.kaozc.com/computer/beikao/2514.html">http://www.kaozc.com/computer/beikao/2514.html</a>，<a href="http://blog.csdn.net/tianyi_lee/article/details/1815954">http://blog.csdn.net/tianyi_lee/article/details/1815954</a></div></li></ul></li>
	<li><div style="background-color:#ccccff;">条件格式</div>
		<ul>
	<li><div>当对某区域（或单元格）应用多个条件时，若条件之间不是互斥关系，则效果会出错</div></li>
	<li><div>特别要注意“公式”和“单元格数值”的区别</div></li></ul></li>
	<li><div style="background-color:#ccccff;">COUNTIFS 和 SUMPRODUCT</div>
		<ul>
	<li><div>为何这两个公式的结果不相同。 =COUNTIF(A1:A6,"&gt;=60")  =SUMPRODUCT((A1:A6&gt;=60)*1)？？A1和A5中有空格，在做sumproduct中a1:a6&gt;=60运算时，文本大于数值，故返回true。而countif中的“&gt;=60”只对数值单元格有效。</div></li>
	<li><div><a href="http://www.tangrenke.com/2011/08/06/sum-under-multiconditions-countifs-sumproduct-database-function/">http://www.tangrenke.com/2011/08/06/sum-under-multiconditions-countifs-sumproduct-database-function/</a></div></li>
	<li><div>今天来介绍下sumproduct的一种用法，然后如果在用07或10的亲，可以用更简单易懂的countifs函数来解决。countifs在教程里有详细的语法介绍及案例运用，就不介绍了。sumproduct的基础用法也很简单，但类似sum数组的那种用法有点深度吧。</div></li></ul></li>
	<li><div style="background-color:#ccccff;">整列引用和有限区域引用</div>
		<ul>
	<li><div>SUM(A:A), MATCH(B1,A:A,), VLOOKUP(C1,A:B,2,) SUMIF(A:A,"A",B:B) 这些公式里的A:A或A:B，我们称之为整列引用。在普通公式中，这种引用经常能见到。 但是我们也经常见到这样的写法：SUM(A1:A1000),VLOOKUP(C1,A1:B999,2,) 有些人认为，后一种写法（称之为“有限范围引用”吧）由于其范围远远小于整列，其速度应该比整列引用要快得多。 但是实际上不是这样的。 比如， 按我们通常的说法，SUMIF和COUNTIF是个“遍历算法”，就是说它把指定范围内的数据从头到尾检查一遍。比如SUMIF(A1:A100,"A",B1:B100)这个公式要检查A1:A100这100个单元格，看看哪一个是"A"。按照这种说法来推理，SUM(A:A,"A",B:B)这个公式就要检查65536个单元格了。实际并非如此。做个测试就知道，这两个公式的速度基本上是一样的。 我觉得，EXCEL在处理这个问题上是有“智能”的。 它首先检测你用到的最后一个单元格，你的所有计算都将限制在A1到最后一个单元格之间，而不管你的公式怎么写。 比如，如果你只有A1:A10，这10单元格有数据，那么不管你的公式写成SUM(A1:A10)，或SUM(A1:A1000),还是SUM(A:A)，计算量都是一样多的，它只计算10个单元格，所用时间是一样的。 所以，从我测试结果来看，普通公式写成有限范围引用是没有必要的。完全可以写成整列引用。 数组公式怎么样？2003及更低版本的数组公式不允许写成整列引用。 但2007版的可以。<br/><a href="http://club.excelhome.net/thread-339339-1-1.html">http://club.excelhome.net/thread-339339-1-1.html</a></div></li>
	<li><div><a href="http://support.microsoft.com/kb/166342/zh-cn">http://support.microsoft.com/kb/166342/zh-cn</a></div>
	</li></ul></li></ul></li></ul></li></ul></div>
	
	有了新的版本了，较上一版本月的任务数可以定义。
	
	下载：<a href='http://vdisk.weibo.com/s/yviDX'>统计反馈V2.2.xls</a>
