---
layout: post
title: x86 system programming 1 
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

## memory 组织架构

### virtual memory

  virtual memory的核心是给软件编程人员提供一个连续的地址空间.原文解释的太好了.来段原文
> _Virtual memory consists of the entire address space available to programs. It is a large linear-address space that is translated by a combination of hardware and operating-system software to a smaller physical-address space, parts of which are located in memory and parts on disk or other external storage media._

  上图比写字更容易说明问题
![x86 memory segmentation]({{ site.baseurl }}/images/virtual_mem_segmentation.png "x86 memory segmentation")

1. 64-bit mode
> 需要注意的是_single/flat(unsegmented) address_
  原文也强调了_The operating system can use separate selectors for code, stack, and data segments for memory-protection purposes, but the base address of all these segments is always 0._

2. compatibility mode
  等同于传统的legacy protected mode.传统就是分段制度. 分段制就有每个段的base addr. 分段制这个后面如果没有详细介绍的话，应该有其他资料来源可以详细介绍的.
  
 OS确实是分段管理memory的，但是比较有讽刺意味的是，主流OS都不使用x86自带的分段制，而是用纯软件来维护分段的机制. amd64就顺从了这个趋势.



----
****
