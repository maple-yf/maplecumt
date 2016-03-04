---
layout: post
title:  "研究生毕业论文写作日志-02"
date:   2016-03-04 24:00:00
categories: Graduate-Paper
---
<strong>研究生毕业论文写作日志。</strong>
<p>
	论文总字数2.06W字。
</p>
<p>
	今天重新设计了内存结构。内存结构由Write Buffer、hBlock地址列表、Key Index Table、BF Index Table、大尺寸Key-Value对索引表组成。Writer Buffer是缓存结构。hBlock地址列表由阵列索引位和hBlock的物理地址组成，用来索引硬盘中的hBlock存储块。大尺寸Key-Value对索引表用来存储尺寸大于8KB(单个SSD page的大小)的KV对。Key Index Table和BF Index Table是核心。两者是本文的两大创新点：分段式索引和阵列式动态布鲁姆过滤器。
</p>
<p>
	Key Index Table里存储的是Key和分段式索引项。分段式索引项包括1B的阵列索引位、3B的SSD Page前缀树索引结构（因为page是以整块append only的方式添加到block中的，所以这样构建前缀索引结构比较容易。）、2B的Key-Value对在SSD Page中的哈希索引结构。这样每条KV对占用16B的内存个空间，对于64GB的内存容量可以存储 64GB/16B=4*2^30条数据，即42.9亿条数据。在内存中，Key Index Table被组织成为skiplist簇，每一条skiplist索引的Key所对应的KV对应该存满一个SSD block。因此每一条skiplist索引的KV对最多是1536KB/2B=768*2^10条数据，即78.6万条数据。
</p>
<p>
	BF Index Table存储的是bloom filter和skiplist内存地址。先说bloom filter，这里每一个bloom filter都是1536KB（也就是SSD中一个block的大小）存储空间的KV对上的，最坏情况下，每个KV对占2B存储空间，则一共有768*2^10条数据，则每个BF只需要占用3B即24bit的存储空间。skiplist内存地址指向存储在该block中的KV对所对应的Key Index Table中skiplist在内存中的地址。按照硬盘中的结构设计，系统一共可以存储约734万个block，因此内存中也应该构建734万个skiplist，在32位机器上，每一条地址4B空间，则一条BF Index Table项占7B内存空间，734万条共占内存7*734*10^4B，大约是49MB。
</p>
