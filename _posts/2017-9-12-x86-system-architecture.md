---
layout: post
title: x86 system architecture学习总结 1 introduction
---

  本片系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

  本博客和标题相符，主要介绍x86系统角度的概念，所以对micro-architecture不会做过多介绍，对软件人员，汇编开发人员，验证人员有较大作用。


  本文主要参考的是amd官方的volume1-5，链接如下

1. [AMD64 Architecture Programmer’s Manual Volume 1: Application Programming](http://support.amd.com/TechDocs/24592.pdf).
2. [AMD64 Architecture Programmer’s Manual Volume 2: System Programming](http://support.amd.com/TechDocs/24593.pdf).
3. [AMD64 Architecture Programmer’s Manual Volume 3: General Purpose and System Instructions](http://support.amd.com/TechDocs/24594.pdf).
4. [AMD64 Architecture Programmer’s Manual Volume 4: 128-bit and 256 bit media instructions](http://support.amd.com/TechDocs/26568.pdf).
5. [AMD64 Architecture Programmer’s Manual Volume 5: 64-Bit Media and x87 Floating-Point Instructions](http://support.amd.com/TechDocs/26569_APM_v5.pdf).

  对原文的引用一般用斜体表示.

  当然本文也希望外行或者对计算机系统结构知识相对薄弱的人做简单的介绍，所以本文行文就相对比较发散和跑题，希望大家多多忍受博主的发散节奏。当然博主的很多观点都是自己的一些看法，很多观点不保证正确.大家多多指教.

  转发，请务必来源于 <http://amdx86.github.io>

  联系blog作者我请发信给 57318505@qq.com

## 计算机模型初谈（我的小观点）
  对于计算机系统结构来说，自从发明计算机以来，大的结构就没有突破. 图灵(大牛,破译德国密码的牛x事迹，我只有仰望欣赏的赶脚，破译的过程是艺术.再跑题一下，换做坂田荣男的说法，围棋的艺术是来源于胜利.大概意思是，你再有艺术，一直输棋，你的艺术怎么能被人认可呢？)发明的图灵机原型足够的牛逼，导致了我们现在的计算机的样子还是和图灵机没有本质的区别. 所以牛人的大脑构思出来的计算机模样，可以深刻影响后来人很多年. 这么多年计算机系统架构都是在这个大的框架里面去做事情来提高计算机的运算能力，至于更厉害的计算机的模型，至今未出现.


  所以计算机系统结构本质上很简单，就是一个运算部件，外面有一个大的线性的存储系统，和图灵机当年提出来的本质上一模一样. 所以计算机系统结构不难理解. 这也是为啥大家突击上蓝翔，上个java培训班就可以撸袖子怼代码的原因. 好吧，扯太远了，拉回来:(  

  本文主要论述的是对于开发软件或者汇编(适用于验证cpu人员)对cpu的_memory,registers,instructions,operands,I/O facilities,interrupt _的介绍.至于这些术语是啥意思，外行或者基础薄弱的不用担心，下面会有相当简单的语言来描述.

  _This volume is intended for programmers writing application programs, compilers, or assemblers. It assumes prior experience in microprocessor programming, although it does not assume prior
experience with the legacy x86 or AMD64 microprocessor architecture_

## x86计算机模型


![x86 寄存器]({{ site.baseurl }}/images/x86_regs.jpg "x86 寄存器")
