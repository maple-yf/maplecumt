---
layout: post
title:  "研究生毕业论文写作日志-02"
date:   2016-03-02 24:00:00
categories: Graduate-Paper
---
<strong>研究生毕业论文写作日志。</strong>
<p>目前论文总字数1.97W。今天开始写论文核心部分。前边已经完成的部分还有很多地方需要改进和完善。</p>
<p>关于昨天设计的8X8的hBlock阵列。今天做如下修改，主要是尺寸问题，为了迎合三星SSD 850EVO每个block大小为1536KB，包含192个page的参数需要。第0层的一个hBlock大小设计为63MB，每一层的hBlock大小都是上一层的4倍，第7层hBlock的大小应该是4^7X63MB，也就是1008GB。按照SSD中每个page大小是8KB计算，第7层的hBlock中将存储1008GB/8KB=126X2^20<2^27个page。三星SSD 850 EVO中一个block包含192个page，这样计算下来，一个hBlock将包含126X2^20/192=21X2^15个block。数字不是很美观，但是没办法，三星的SSD参数太奇葩。</p>
