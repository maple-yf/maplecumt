---
layout: post
title:  "研究生毕业论文写作日志-07"
date:   2016-03-11 23:00:00
categories: Graduate-Paper
---
<strong>研究生毕业论文写作日志。</strong>
<p>
	论文总字数2.83W。
</p>
<p>
	动态阵列式布鲁姆过滤器优化部分块写完了，还差最后的一个优化函数。优化函数将会根据元素个数动态产生每个DBA所包含的BF的个数。这个数字必须是8的整数倍以有利于并行按位操作。
</p>
<p>
	最大的sBlock中可以存储2^15个sTable。每个sTable包含21个SSD Block，3402个SSD Page。Key Index Table在内存中被构建为Skiplist簇，每一条Skiplist索引一个sTable。BF Index Table中的每个DBA用来表示其所对应的Skiplist中索引的所有Key-Value对。
</p>
<p>
	今天成功安装MATLAB。
</p>