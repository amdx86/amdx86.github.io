---
layout: post
title: x86 system programming 5 Page Translation and Protection
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。
  除了最基本的virtual -> physical mapping和基本的protection，还有如下的用途
  1 Shared mapping is typically used to allow access of shared-library routines by multiple applications. A read-only copy of the library routine is mapped to each application virtual-address space, but only a
single copy of the library routine is present in physical memory.
  2 Supervisor pages are only accessible by system software.
  finally, we only maintains little page in memory while most of the unused pages are in hard drives, which is called _demand-paged virtual memory_.
  ![x86 memory segmentation]({{ site.baseurl }}/images/va_to_pa.jpg "x86 virtual addr to physical addr in long mode")

## 5.1 Read Mode Segmentation  
  reset the first mode cpu enter is real mode, protected mode are enteredfrom real mode. real mode means addr are real(phsical) which is only 1M size.
CS/DS/ES/FS/GS/SS aligned on 16-byte boundaries. POP MOV to operate on the CS/DS/ES/FS/GS/SS 

## 4.2 virtual-8086 Mode segmentation

## 4.3 Protected  Mode Segmented-Memory Models.
### 4.3.2 flat-memory model
    全部seg base全部设置成为0可以好理解，为何limit都必须为4G? 这个是不是说, flat-memory model是用来做legacy的32的model？
### 4.3.3 Segmentation in 64-bit mode
    disabled. 
    exception: 1 CS-segment DPL D and L
    exception: 2 FS/GS segments can be used as additional base regs in addr calc.
    and those segments can have non-zero base-addresss values.

    exception: 1 CS-segment DPL D and L
### 4.4 Segmentation Data Structure and Registers
    这是关键

----
****
