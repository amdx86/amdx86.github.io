---
layout: post
title: x86 system programming 4 Segmented Virtual Memory 
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。
  10 segments, CS/DS/ES/FS/GS/SS user segments which hold software,data,and the stack and can be used by both application and system software.
  GDT/LDT/IDT/TR system segments contains data structures intialized and used only by system software.

  segments registers contains a base address pointing to the start location of a segment, a limit defining the segment size, and the attribuits defining the segment-protection characteristics.
  although modern OS bypass the segmentation feature, but segmentation cannot be completedly disabled and an understanding of the segmentation mechanism is important to implementing long-mode system software.

  
## 4.1 Read Mode Segmentation  
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
