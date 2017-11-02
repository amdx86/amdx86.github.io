---
layout: post
title: x87 application programming 6 x87 Floating-Point Programming
---
  本系列博客用来记录自己对x86体系结构的学习总结，同时方便大家查阅，节省大家学习的时间。

## 6.1 Overview  
### 6.1.1 Capabilities  
  x87 instructions carry out all computations using the 80-BIT DOUBLE-EXTENDED-PRECISION FORMAT  
  Most x87 operations for addition, subtraction, multiplication, and division specify two source operands, the first of which is replaced by the result. Instructions for subtraction and division have reverse forms which swap the ordering of operands.
## 6.2 Registers  
  These registers include eight 80-bit data registers, three 16-bit registers that hold the x87 control word,
status word, and tag word, two 64-bit registers that hold instruction and data pointers, and an 11-bit register that holds a permutation of an x87 opcode

### 6.2.1 Capabilities  
  Figure 6-2 on page 286 shows the eight 80-bit data registers in more detail. Typically, x87 instructions. reference these registers as a STACK. x87 instructions store operands only in these 80-bit registers or in memory. They do not (with two exceptions) access the GPR registers, and they do not access the YMM/XMM registers.
  8个数据寄存器组成一个循环堆栈，栈顶记录保存于状态寄存器中，相当于堆栈指针。每次压栈（FLD指令载入数据），堆栈指针就减1，在0～7之间循环。代码并不直接使用这个指针操作这些寄存器，而是使用ST(0)～ST(7)表示。ST(0)指栈顶，即状态寄存器中栈顶指针指示的那个寄存器。 
  假设当前状态寄存器中的栈顶指针是N（即编号N的寄存器位于栈顶），则ST(i)对应的寄存器编号是：N+i mod 8 例如初始状态时，堆栈指针是0，FLD指令装载了一个数据以后，指针减小1是7，则ST(0)即是寄存器7，而ST(1)对应的寄存器编号是：7+1 mod 8 = 0
 

----
****
