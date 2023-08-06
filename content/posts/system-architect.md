---
title: "软考-系统架构师"
date: 2023-08-06T18:21:01+08:00
draft: true
---

## 基础部分
### 计算机硬件
#### 相关概念

![计算机硬件组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.50u9cjryeck0.png "计算机硬件组成")

![CPU 的功能](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5nujeeacm3o0.webp "CPU 的功能")

![CPU 的组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.fmceksfw06w.webp "CPU 的组成")

![奇偶校验码](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1pgi3nxmcx4w.webp "奇偶校验码")

![CRC 循环冗余校验码1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.24v5f4oszysg.webp "CRC 循环冗余校验码1")
![CRC 循环冗余校验码2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1elsprl1sue8.webp "CRC 循环冗余校验码2")

![计算机指令的组成和执行过程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6qdek30lpc80.webp "计算机指令的组成和执行过程")

![计算机指令的寻址方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.ou2ih4m6j5s.webp "计算机指令的寻址方式")

![计算机指令的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.733cz61t52g0.webp "计算机指令的分类")

![指令流水线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5t6g10ok4v40.webp "指令流水线")

![分级存储体系与局部性原理](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.33dkhwgef0o0.webp "分级存储体系与局部性原理")

![Cache 概念](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5hxgdiahn3g.webp "Cache 概念")

![Cache 映像方式1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5ep6d4fesqk0.webp "Cache 映像方式1")
![Cache 映像方式2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.17iz0rps4rxc.webp "Cache 映像方式2")

![Cache 替换算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2ow3qsbt8vm0.webp "Cache 替换算法")

![Cache 命中率及平均时间](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.29nk73n2unb4.webp "Cache 命中率及平均时间")

![磁盘结构和参数](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1oeoxoad1p4w.webp "磁盘结构和参数")

![磁盘调度算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.15ryesazcin4.webp "磁盘调度算法")

![内存与接口地址的编址方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.b1pnqtuf1ug.webp "内存与接口地址的编址方法")

![计算机和外设间的数据交互方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5zlfwjwdgg40.webp "计算机和外设间的数据交互方式")

![总线的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5kdhmitxwic0.webp "总线的分类")

#### 相关公式

- CRC 编码: 1. 在原始信息串后面补多项式的阶个零; 2. 求除数，多项式中幂指数存在的为 1，不存在为 0; 3. 求校验码，进行模 2 除(异或运算)，**余数如果不足多项式的阶的位数则在左边补 0**
- 流水线周期: 指令分成不同执行段，其中执行时间最长的段为流水线周期
- 流水线执行时间1: 1 条指令的总执行时间 + (总指令条数 - 1) * 流水线周期
- 流水线执行时间2: (1 条指令的总执行时间 - 流水线周期) + 总指令条数 * 流水线周期
- 流水线的吞吐率: 吞吐率即为单位时间内执行的指令条数 = 指令条数 / 流水线执行时间
- 流水线的加速比: 不使用流水线的执行时间 / 使用流水线的执行时间
- 流水线的最大加速比: 1 条指令不使用流水线的执行时间 / 流水线周期 
- 磁道记录的最大等待时间: 就是旋转一周的时间
- 磁道记录的最小等待时间: 就是 0
- 磁道按顺序排列的记录等待时间: 旋转一周的时间 - 处理时间
- 磁道记录的总处理时间: (旋转一块的时间 + 处理时间) * 总块数 + 等待时间 * (总块数 - 1) 

#### 相关题型解题思路

- 求 CRC 循环冗余校验码: 通常给出原始信息串和生成多项式，让求校验码，套公式即可。
- 求流水线相关问题: 如果是让求吞吐率或加速比，通常情况下需要先求出执行时间，也就是说需要套两个公式;如果碰到和缓冲区结合考察的问题，注意但单双缓冲区的差异，单缓冲区读入和写出不能同时进行，因此读入和写出的时间需要加在一起算做一段。而双缓冲区的读入和写出可以同时进行，因此可以算做两段。
- 求流水线最大加速比: 加上最大两个字，就是求极限值了，通常不会给出总指令条数，而需要设为 n 来计算，求极限时忽略常数，带入公式即可。
- 求磁盘调度的响应序列: 按照采用的调度算法，来求序列，多个相同柱面号的情况下，扇区号由小到大排列，磁头号是无效信息。
- 求磁道记录的最长处理时间和最少处理时间: 通常给出逻辑记录的安排顺序表，磁盘的每周旋转速度，每个记录的处理时间，需要**注意还有个隐含的条件是磁盘的每块的旋转时间，且当前快数据旋转读取完后才能开始处理**，求出隐含条件后带入公式计算。
