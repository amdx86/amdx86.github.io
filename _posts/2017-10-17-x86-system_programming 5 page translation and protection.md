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

## 5.1 Page Translation Overview  
  1. legacy is 32 to 32(**legacy has special mode to 36 or 40bits**)
  2. amd64 is 64 to 52
  如下是一个经典的page translation的示意图
  ![x86 va to pa long mode]({{ site.baseurl }}/images/va_to_pa_long_mode.jpg "x86 virtual addr to physical addr in long mode")
  size: 
  1. 4 Kbytes(long mode)  (legacy mode)
  2. 2 Mbytes(long mode)  (legacy mode)
  3. 4 Mbytes             (legacy mode)
  4. 1 Gbytes(long mode)
  **Currently the AMD64 architecture defines a mechanism for translating 48-bit virtual addresses to 52-bit physical addresses.**
### 5.1.1 Page-Translation Options
  1. Page-Translation Enable(CR0.PG)
  2. Physical-Addr extensions(CR4.PAE)
  3. Page-Size Extensions(CR4.PSE)
  4. Long-Mode active
     page options 和模式交叉的关系如下表格
  ![page options with mode]({{ site.baseurl }}/images/page_options_with_mode.jpg "x86 virtual addr to physical addr in long mode")

## 5.2 virtual-8086 Mode segmentation

## 5.3 Protected Mode Segmented-Memory Models.
### 5.3.2 flat-memory model
    全部seg base全部设置成为0可以好理解，为何limit都必须为4G? 这个是不是说, flat-memory model是用来做legacy的32的model？
### 5.3.3 Segmentation in 64-bit mode
    disabled. 
    exception: 1 CS-segment DPL D and L
    exception: 2 FS/GS segments can be used as additional base regs in addr calc.
    and those segments can have non-zero base-addresss values.

    exception: 1 CS-segment DPL D and L
### 5.4 Segmentation Data Structure and Registers
    这是关键

----
****
