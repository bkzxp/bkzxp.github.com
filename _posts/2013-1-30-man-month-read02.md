---
layout : post
category : lessons
tags : [读书, 人月神话]
title : 人月神话--人月神话
---


<div><ul>
	<li><div style="background-color:#cc0000;">
<a href="/lessons/2013/01/30/man-month-read00/" title="返回《人月神话》目录"><font color="#FFFF00" >返回《人月神话》目录</font></a>
<a href="/lessons/2013/01/30/man-month-read01/" title="上一篇">上一篇</a></div>
	<ul>
	<li><div style="background-color:#00cc66;">项目滞后的最主要原因是什么</div>
		<ul>
	<li><div>缺乏合理的时间进度</div></li></ul></li>
	<li><div style="background-color:#00cc66;">时间进度的不合理安排的原因以及表现是什么</div>
		<ul>
	<li><div style="background-color:#6699ff;">我们对估算技术缺乏有效的研究</div>
		<ul>
	<li><div>它反映了一种悄无声息，但并不真实的假设——一切都将运作良好。</div></li>
	<li><div>BK：把“一切都将运作良好”作为估算的潜在条件</div></li></ul></li>
	<li><div style="background-color:#6699ff;">我们采用的估算技术隐含的假设人和月可以互换，错误的将工作量相互混淆</div></li>
	<li><div style="background-color:#6699ff;">由于对自己缺乏信心，软件经理通常不会有耐心持续地进行估算这项工作</div></li>
	<li><div style="background-color:#6699ff;">对进度缺少跟踪和监督。</div></li>
	<li><div style="background-color:#6699ff;">当意识到进度的偏移时，下意识的反应是增加人力。</div>
		<ul>
	<li><div>BK刚读到这里的时候，感觉，这样做有什么不可以，很是不明白，到了后面才认识到。</div></li></ul></li></ul></li>
	<li><div style="background-color:#00cc66;">对上述观点的详细描述</div>
		<ul>
	<li><div style="background-color:#6699ff;">乐观主义</div>
		<ul>
	<li><div>程序员的口头禅：这次它肯定会运行，或者，我刚刚找出了最后一个错误，或者，给我几分钟我马上就能搞定</div></li>
	<li><div>系统编程的进度安排的第一个假设就是：一切都将运作良好，每一项任务仅花费它所应该花费的时间</div></li>
	<li><div>乐观主义产生的原因？</div>
		<ul>
	<li><div>编程人员通过非常纯粹的思维活动——概念以及灵活的表现形式来开发程序。正是由于介质的易于驾驭，我们期待在实现过程中不会碰到困难，因此造就了乐观主义的弥漫。而我们的构思是有缺陷的，因此总会有bug。也就是说，我们的乐观主义并不应该是理所当然的。</div></li></ul></li></ul></li>
	<li><div style="background-color:#6699ff;">人月</div>
		<ul>
	<li><div style="background-color:#999999;">用人月作为衡量一项工作的规模是一个危险和带有欺骗性质的神话。它暗示着人员和数量可以相互替换。</div>
		<ul>
	<li><div>为什么这样说？因为成本的确随着开发产品的人数和时间的不同，会有着很大的变化，但进度却非如此。</div></li></ul></li>
	<li><div style="background-color:#999999;">人数和时间的互换仅仅适用于：</div>
		<ul>
	<li><div>某个任务可以分解给参与人员，并且他们之间不需要相互的交流。如割小麦这样的工作。</div></li></ul></li>
	<li><div style="background-color:#999999;">这种互换不适用于：</div>
		<ul>
	<li><div>当任务由于次序上的限制不能分割时，忍受的添加对进度没有任何帮助。无论多少个母亲，孕育生命都需要十个月。</div></li>
	<li><div>BK：这让我想起了初中的一个物理题：问5个馒头蒸熟要用25分钟，1个馒头蒸熟要多少分钟？【水分子的高速运动必须要那么多时间才能引起馒头的变化】</div></li>
	<li><div>沟通所增加的负担（工作量）有两部分组成，培训和相互交流。</div>
		<ul>
	<li><div>培训任务不能分解，因此这部分增加的工作量随人员的数量呈线性变化。</div></li>
	<li><div>交流：如果任务的每个部分必须分别和其他部分单独协作，则工作量按照n(n-1)/2递增。三个人的工作量是两个人的三倍。</div></li>
	<li><div>软件开发本质上是一项系统工作，沟通交流的工作量非常大，它很快会消耗任务所节省下来的个人时间。于是，添加更多的人手，实际上是延长了时间进度。</div></li></ul></li></ul></li></ul></li>
	<li><div style="background-color:#6699ff;">系统测试</div>
		<ul>
	<li><div style="background-color:#999999;">系统测试进度的安排往往是编程中最不合理的部分。</div></li>
	<li><div style="background-color:#999999;">给出先前的经验法则：</div>
		<ul>
	<li><div>1/3时间计划，1/6时间编码，1/4构件测试和早期系统测试，1/4时间系统测试，所有的构件已经完成</div></li></ul></li>
	<li><div style="background-color:#999999;">该法则与传统的进度安排的不同：</div>
		<ul>
	<li><div>分配给计划的时间比寻常的多即使如此，仍然不足以产生详细和稳定的计划规格说明，也不足以容纳对全新技术的研究和摸索。</div></li>
	<li><div>对所完成代码的调试和测试，投入近一半的时间，比平常的安排多很多。</div></li>
	<li><div>容易估计的部分，即编码，仅仅分配了六分之一的时间。</div></li></ul></li></ul></li>
	<li><div style="background-color:#6699ff;">空泛的估算</div>
		<ul>
	<li><div style="background-color:#999999;">为了满足顾客期望的日期而造成的不合理进度安排，在软件领域中却比其他的任何工程领域要普遍的多。</div></li>
	<li><div style="background-color:#999999;">两种解决方案</div>
		<ul>
	<li><div>开发并推行生产率表、缺陷率、估算规则等等</div></li>
	<li><div>在基于可靠基础的估算出现之前，项目经理需要挺直腰杆，坚持他们的估计，确信自己的经验和直觉总比从期望派生出的结果要强得多</div></li></ul></li></ul></li>
	<li><div style="background-color:#6699ff;">重复产生的进度灾难</div>
		<ul>
	<li><div>场景：设想一个估计需要12个人月的任务，分派给3个成员4个月完成，在每个月末安排了可测量的里程碑。假定在第二个月后，第一个里程碑给没有达到。项目经理拥有哪些方案来解决这个问题？</div></li>
	<li><div>方案一：假设任务必须按时完成。再假设仅仅是任务的第一个部分的估计不当，则剩余了9个人月的工作量，时间还有两个月，需要4.5个开发人员。所以需要在原来的3个上再加2个人手。</div></li>
	<li><div>方案二：假设任务必须按时完成。假设整个任务的估计偏低。那么还有18个人月的工作量和2个月的时间。则需要增加人手至9人。</div></li>
	<li><div>方案三：重新安排进度。“避免小的偏差”。在新的进度安排重分配充分的时间，以确保工作能够仔细、彻底地完成，从而无需重新确定时间进度表。</div></li>
	<li><div>方案四：消减任务。在现实情况中，一旦开发团队观察到进度的偏差，总是倾向于对任务进度进行消减。当项目延期导致的后续成本非常高时，这常常是唯一可行的方法。</div></li>
	<li><div>项目经理相应的措施是仔细、正式地调整项目，重新安排进度；或者是默默地注视着任务项由于轻率的设计和不完整的测试而被剪除。而在前两种方案中，坚持把不经调整的任务在四个月内完成将是灾难性的。</div></li>
	<li><div>Brooks法则：向落后的项目中增加人手，只会使进度更加落后。</div></li></ul></li></ul></li>
	<li><div style="background-color:#00cc66;">总之，在众多的软件项目中，缺乏合理的时间进度是造成项目滞后的最主要原因，它比其他所有因素加起来的影响还要大。</div></li></ul>
	<div style="background-color:#ff0000;"><a href="/lessons/2013/03/11/man-month-read03/" title="下一篇">下一篇</a></div>
</li></ul></div>