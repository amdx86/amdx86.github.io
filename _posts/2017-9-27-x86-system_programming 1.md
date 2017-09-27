---
layout: post
title: x86 system programming 1 
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

## system-programming overview
  一句话,(CPL=0), privileged software
### Memory Model
1. backward-compatible with legacy memory model.
2. hardware-translation mechanisms for VA to PA.
3. long mode, falt-memory model.   
4. legacy mode, the architecture implements all legacy memory models.
#### Memory Addressing
1. Logical addr
2. Effective addr, or segmetns offsets, which are a portion of the logical addr
3. linear(virtual) address
4. Physical addr



----
****
