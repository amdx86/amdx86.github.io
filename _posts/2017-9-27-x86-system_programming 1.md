---
layout: post
title: x86 system programming 1 
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

## system-programming overview
  一句话,(CPL=0), privileged software
### 1.1 Memory Model
1. backward-compatible with legacy memory model.
2. hardware-translation mechanisms for VA to PA.
3. long mode, falt-memory model.   
4. legacy mode, the architecture implements all legacy memory models.
#### 1.1.1 Memory Addressing
1. Logical addr
   reference into a segmented-addr space
   Logical Addr = Segment Selector : Offset
   (Far pointers) ?
2. Effective addr, or segmetns offsets, which are a portion of the logical addr
   Effective Address = Base + (Scale x Index ) + Displacement
   (Near pointers) ?

3. linear(virtual) address
   Linear Address = Segment Base Addr +Effective Address

4. Physical addr

#### 1.1.2 Memory Organization
  Virtual Memory
  1. Protected Mode (32bits virtual addr)
  2. Long Mode      (64bits virtual addr)
  Physical Memory
  1. Real-Address Mode
     real mode, 1M bytes of physical address space using 20bits physical addr.
  2. Legacy Protected Mode
  3. Long Mode

----
****
