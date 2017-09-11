---
layout: post
title: x86 system architecture学习总结
---

本片系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

本博客和标题相符，主要介绍x86系统角度的概念，所以对micro-architecture不会做过多介绍，对软件人员，汇编开发人员，验证人员有较大作用。

本文主要参考的是amd官方的volume1-5，链接如下

1 [volume1](http://support.amd.com/TechDocs/24592.pdf).
2 [volume2](http://support.amd.com/TechDocs/24593.pdf).
3 [volume3](http://support.amd.com/TechDocs/24594.pdf).
4 [volume4](http://support.amd.com/TechDocs/26568.pdf).
5 [volume5](http://support.amd.com/TechDocs/26569_APM_v5.pdf).

斜体是对文档的引用
_This volume is intended for programmers writing application programs, compilers, or assemblers. It assumes prior experience in microprocessor programming, although it does not assume prior
experience with the legacy x86 or AMD64 microprocessor architecture_

当然本文也希望外行或者对计算机系统结构知识相对薄弱的人做简单的介绍，所以本文行文就相对比较发散和跑题，希望大家多多忍受博主的发散节奏。

转发，请务必来源于 <http://amdx86.github.io>
 
