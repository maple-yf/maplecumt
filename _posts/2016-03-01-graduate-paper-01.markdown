---
layout: post
title:  "研究生毕业论文写作日志-01"
date:   2016-03-01 24:00:00
categories: Graduate-Paper
---
<strong>研究生毕业论文写作日志。</strong>
<p>目前论文总字数1.8W。今天对内存结构部分作了详细设计，画了三张图纸。结构类似于LevelDB，在硬盘中存储一个8X8的hBlock阵列。第0层的一个hBlock大小设计为4X16MB，每一层的hBlock大小都是上一层的4倍，第7层hBlock的大小应该是4^8X16MB，也就是1TB。按照SSD中每个page大小是8KB计算，第7层的hBlock中将存储1TB/8KB=2^27个page。三星SSD 850 EVO中一个block包含192个page，这样计算下来，一个hBlock将包含2^27/192=699050.667个block。哎呀，不是整数，这是个问题，需要继续改进。
目前存储结构设计三级结构：</p>
	hBlock->hTable->value
