---
title: "软考-系统架构师"
date: 2023-08-06T18:21:01+08:00
draft: true
---

# 上篇

## 计算机系统基础知识

### 计算机硬件 0-1

#### 计算机硬件组成

![计算机硬件组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.50u9cjryeck0.png "计算机硬件组成")

#### 处理器

##### CPU 的功能

![CPU 的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5nujeeacm3o0.webp "CPU 的功能")

##### CPU 的组成

![CPU 的组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.fmceksfw06w.webp "CPU 的组成")

#### 存储器

##### 分级存储体系与局部性原理

![分级存储体系与局部性原理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.33dkhwgef0o0.webp "分级存储体系与局部性原理")

##### Cache 相关概念

![Cache 相关概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hxgdiahn3g.webp "Cache 相关概念")

##### Cache 映像方式

![Cache 映像方式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ep6d4fesqk0.webp "Cache 映像方式1")
![Cache 映像方式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.17iz0rps4rxc.webp "Cache 映像方式2")

##### Cache 替换算法

![Cache 替换算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ow3qsbt8vm0.webp "Cache 替换算法")

##### Cache 命中率及读取平均时间

![Cache 命中率及读取平均时间](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.29nk73n2unb4.webp "Cache 命中率及读取平均时间")

##### 磁盘结构和参数

![磁盘结构和参数](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1oeoxoad1p4w.webp "磁盘结构和参数")

##### 磁盘调度算法

![磁盘调度算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.15ryesazcin4.webp "磁盘调度算法")

##### 内存与接口地址的编址方法

![内存与接口地址的编址方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.b1pnqtuf1ug.webp "内存与接口地址的编址方法")

##### 相关公式

- 磁道记录的最大等待时间: 就是旋转一周的时间
- 磁道记录的最小等待时间: 就是 0
- 磁道按顺序排列的记录等待时间: 旋转一周的时间 - 处理时间
- 磁道记录的总处理时间: (旋转一块的时间 + 处理时间) \* 总块数 + 等待时间 \* (总块数 - 1)

##### 相关题型解题思路

- 求磁盘调度的响应序列: 按照采用的调度算法，来求序列，多个相同柱面号的情况下，扇区号由小到大排列，磁头号是无效信息。
- 求磁道记录的最长处理时间和最少处理时间: 通常给出逻辑记录的安排顺序表，磁盘的每周旋转速度，每个记录的处理时间，需要**注意还有个隐含的条件是磁盘的每块的旋转时间，且当前快数据旋转读取完后才能开始处理**，求出隐含条件后带入公式计算。

#### 总线

##### 总线的分类

![总线的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5kdhmitxwic0.webp "总线的分类")

#### 外部设备

##### 计算机和外设间的数据交互方式

![计算机和外设间的数据交互方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5zlfwjwdgg40.webp "计算机和外设间的数据交互方式")

#### 指令

##### 计算机指令的组成和执行过程

![计算机指令的组成和执行过程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6qdek30lpc80.webp "计算机指令的组成和执行过程")

##### 计算机指令的寻址方式

![计算机指令的寻址方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.ou2ih4m6j5s.webp "计算机指令的寻址方式")

##### CISC 与 RISC

![CISC 与 RISC](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.733cz61t52g0.webp "CISC 与 RISC")

##### 指令流水线

![指令流水线](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5t6g10ok4v40.webp "指令流水线")

##### 相关公式

- 流水线周期: 指令分成不同执行段，其中执行时间最长的段为流水线周期
- 流水线执行时间 1: 1 条指令的总执行时间 + (总指令条数 - 1) \* 流水线周期
- 流水线执行时间 2: (1 条指令的总执行时间 - 流水线周期) + 总指令条数 \* 流水线周期
- 流水线的吞吐率: 吞吐率即为单位时间内执行的指令条数 = 指令条数 / 流水线执行时间
- 流水线的最大吞吐率: 1 / 流水线周期
- 流水线的加速比: 不使用流水线的执行时间 / 使用流水线的执行时间
- 流水线的最大加速比: 1 条指令不使用流水线的执行时间 / 流水线周期

##### 相关题型解题思路

- 求流水线相关问题: 如果是让求吞吐率或加速比，通常情况下需要先求出执行时间，也就是说需要套两个公式;如果碰到和缓冲区结合考察的问题，**注意但单双缓冲区的差异，单缓冲区读入和写出不能同时进行，因此读入和写出的时间需要加在一起算做一段**。而双缓冲区的读入和写出可以同时进行，因此可以算做两段。
- 求流水线最大加速比: 加上最大两个字，就是求极限值了，通常不会给出总指令条数，而需要设为 n 来计算，求极限时忽略常数，带入公式即可。

#### 校验码

##### 奇偶校验码

![奇偶校验码](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1pgi3nxmcx4w.webp "奇偶校验码")

##### CRC 循环冗余校验码

![CRC 循环冗余校验码1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.24v5f4oszysg.webp "CRC 循环冗余校验码1")
![CRC 循环冗余校验码2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1elsprl1sue8.webp "CRC 循环冗余校验码2")

##### 相关公式

- CRC 编码: 1. 在原始信息串后面补多项式的阶个零; 2. 求除数，多项式中幂指数存在的为 1，不存在为 0; 3. 求校验码，进行模 2 除(异或运算)，**余数如果不足多项式的阶的位数则在左边补 0**

##### 相关题型解题思路

- 求 CRC 循环冗余校验码: 通常给出原始信息串和生成多项式，让求校验码，套公式即可。

### 计算机软件

#### 操作系统 3-5

##### 操作系统

###### 操作系统的定义、作用、特征

![操作系统的定义、作用、特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4ta08p68eug0.webp "操作系统的定义、作用、特征")

###### 操作系统的功能

![操作系统的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4ozf20qqg6g0.webp "操作系统的功能")

###### 操作系统的分类

![操作系统的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1hfphfzgmusg.webp "操作系统的分类")

##### 进程管理

###### 进程的组成和三态图

![进程的组成和三态图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1qa522vuo20w.webp "进程的组成和三态图")

###### 前趋图

![前趋图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4cxaged0yjq0.webp "前趋图")

###### 进程资源图

![进程资源图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.39n1vb9hou20.webp "进程资源图")

###### 同步互斥与信号量

![同步互斥与信号量](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.u47c4pdg4uo.webp "同步互斥与信号量")

###### PV 操作

![PV 操作](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6i8o5hlsafk0.webp "PV 操作")

###### 生产者消费者问题

![生产者消费者问题](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hiw1kyeeug0.webp "生产者消费者问题")

###### 进程调度方式与三级调度

![进程调度方式与三级调度](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6c2qe0jxwls0.webp "进程调度方式与三级调度")

###### 进程调度算法

![进程调度算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ty2cv623b60.webp "进程调度算法")

###### 死锁

![死锁](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2wqhyeh9wvq0.webp "死锁")

###### 线程

![线程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6lmden7uo1g0.webp "线程")

###### 相关公式

- 每个进程需要资源数不同时发生死锁的最大资源数: (进程 1 需要的资源数 - 1) + (进程 2 需要的资源数 - 1) + ... + (进程 n 需要的资源数 - 1)
- 每个进程需要资源数相同时发生死锁的最大资源数: 系统中的进程数 \* (单个进程需要的资源数 - 1)
- 不发生死锁的最小资源数: 发生死锁的最大资源数 + 1
- 互斥信号量初始值: 1
- 同步信号量的最大值: 资源数量
- 同步信号量的最小值: - (进程数量 - 资源数量)

###### 相关题型解题思路

- 考察进程三态图之间的转换: 给定服务调度算法、给定几个进程的当前状态，某进程发生某事件后，求所有进程的后续状态。以三态图的转变带入后解题。
- 考察前趋图，给定前趋图，求可标记为。从开始节点开始读，排除错误答案即可，很简单。
- 考察进程资源图，求阻塞节点：某进程所请求的资源已经全部分配完毕，该进程为阻塞节点。
- 考察进程资源图，求化简顺序：先找非阻塞节点，然后释放其占用资源(划掉连线)后，找后续的非阻塞节点，直到所有节点都不被阻塞。
- **综合考察 PV 操作**: 给定前趋图，进程，和需要设置的信号量，然后给出进程部分执行过程中的 PV 操作，求空余的部分的 PV 操作。结合前趋图来看，从最开始无依赖的进程开始填空，进程执行完进行 V 操作，有几个后继则进行几次不同信号量的 V 操作。然后后面等待执行的进行的前驱如果都执行完了，则开始执行，有几个前驱进行几次不同信号量的 P 操作。
- 求信号量的取值范围: 给定进程数和资源数，求使用 PV 操作时需要设定的信号量的范围，带入公式计算，信号量为负几，则有几个等待进程。
- 考察银行家算法，求当前可用的资源数和安全的执行序列: 给定资源及其可用资源总数，给定几个进程及其最大需求量和已分配资源数图示。**首先用资源的最大总数-当前所有进程分配的数量求出其当前可用的资源数**。然后找到所有执行序列中资源最大需求量都能满足的进程，作为可执行的进程，执行完后把这个进程上已分配的资源数加回，可用资源数，再找下一个可执行进程。

##### 存储管理

###### 分区存储方式

![分区存储方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.qmuxffsi1n4.webp "分区存储方式")

###### 分区适应法

![分区适应法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.32xww0kvkcy0.webp "分区适应法")

###### 分页存储

![分页存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2scnsm54dvc0.webp "分页存储")

###### 页面置换算法

![页面置换算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.727k1ckq7ms0.webp "页面置换算法")

###### 快表

![快表](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3iiym37nnks0.webp "快表")

###### 分段存储

![分段存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.18syec51w934.webp "分段存储")

###### 段页式存储

![段页式存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4tqudwbw0om0.webp "段页式存储")

###### 磁盘冗余阵列技术

![磁盘冗余阵列技术1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3t761ry4bgk0.webp "磁盘冗余阵列技术1")
![磁盘冗余阵列技术2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.60ydmembgxg0.webp "磁盘冗余阵列技术2")
![磁盘冗余阵列技术3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1cnolw5yuxr.webp "磁盘冗余阵列技术3")

###### 网络存储技术

![网络存储技术1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5mtt846n0pw0.webp "网络存储技术1")
![网络存储技术2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2y6ond2fhi20.webp "网络存储技术2")

###### 相关公式

- 页内地址的位数: 每页大小以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 1: 内存大小 / 每页大小，然后求其以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 2: 逻辑地址或物理地址的位数 - 页内地址的位数
- 分页式存储物理地址: 高位通过页号在页表中查到物理块号 拼接 低位页内地址(偏移地址)，**逻辑地址和物理地址中低位的偏移地址不变，区别只是将高位的逻辑页号替换为了物理快号**

###### 相关题型解题思路

- 求分页式存储的物理地址: 通常给出页面大小和逻辑地址，以及页号和物理块号的对应表，让求物理地址。首先通过页面大小算出页内地址的位数(**也可以直接看答案中，多数答案与逻辑地址后面几位重复，且前面剩余的在页表里能查到，则其为偏移地址位数，页面大小通常为 4k，则二进制表示为 4 位，16 进制表示为 1 位**)，剩余高位为页号，通过页号找到对应的物理块号，然后将逻辑地址高位替换为物理快号就是物理地址。
- 求淘汰那个页面代价最小: 通常给出一个表格，标识每个页面的状态位、修改位、访问位，根据局部性原理，**优先淘汰最近未被访问过的，而后淘汰最近未被修改过的**。
- 求段式存储中逻辑地址能否转换为物理地址(不违法)，给定几个(段号，段内偏移)，然后表格中给出段号和段长列，**根据段号找到段长，段内偏移大于段长就违法**。

##### 设备管理

###### 设备管理概述

![设备管理概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1g5x73h6fyqo.webp "设备管理概述")

###### I/O 设备

![I/O 设备](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.34mylt9dmqw0.webp "I/O 设备")

###### 设备管理技术

![设备管理技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1maz233knxk0.webp "设备管理技术")

#### 文件系统 0-1

##### 相关概念

###### 文件管理概述

![文件管理概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7gs2ocqkw480.webp "文件管理概述")

###### 文件结构分类

![文件结构分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3xwfe8q9sgu0.webp "文件结构分类")

###### 索引文件结构

![索引文件结构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6hs13ibogkg0.webp "索引文件结构")

###### 文件目录

![文件目录](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.24huvvajhps0.webp "文件目录")

###### 文件存储空间管理

![文件存储空间管理1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5pr9lq294js0.webp "文件存储空间管理1")
![文件存储空间管理2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67e5ut4ovnc0.webp "文件存储空间管理2")

###### 相关公式

- 一级间接索引逻辑块的个数: 磁盘索引块大小 / 每个地址项的大小
- 二级间接索引逻辑块的个数: (磁盘索引块大小 / 每个地址项的大小) \* (磁盘索引块大小 / 每个地址项的大小)
- 一级间接索引物理块号的表示范围: 直接索引的最大编号 + 1 到 直接索引的最大编号 + 一级间接索引逻辑块的总个数
- 可表示的单个文件的最大长度: 可表示的总的逻辑块数 \* 磁盘数据块大小
- 表示位示图需要的字的个数: 磁盘容量 / 磁盘物理块大小 / 系统字长位数

###### 相关题型解题思路

- 求逻辑快应采用什么索引: 通常给出一共几个地址项，以及其中几个直接索引，几个一级间接索引，几个二级间接索引，和每个地址项的大小，以及磁盘索引块和磁盘数据块的大小，然后问访问的逻辑块号应采用的是什么索引。题目中没明确说明时，**逻辑块从 0 开始编号**。首先将直接索引进行编号，然后带公式求一级间接索引的表示范围，以上就是二级间接索引的范围，这样就能判断采用的是什么索引。
- 求采用什么索引和可表示的单个文件的最大长度: 算出总的表示范围(可表示的总的逻辑块数)(**如果答案没有相近的长度，只用算二级索引就行了**) 乘以磁盘数据块大小，代公式计算，就能算出可表示的单个文件最大的长度。
- 求相对路径和绝对路径: 通常给出目录结构图，当前工作目录和需要访问的文件名，求相对路径和绝对路径，很简单。注意一点，路径最后的杠可以省略。
- 求需要表示的物理块在位示图中的第几个字描述: 通常需要表示的物理块号，和字长。**注意如果有余数，则向上取整，还有没有明确说明的情况下是从零开始编号的**
- 求位示图需要几个字来表示: 通常给出全部条件带入公式计算即可。

#### 中间件

![中间件的概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5dm6nuxci8k0.webp "中间件的概念")

![中间件的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6exx8nfljkk0.webp "中间件的分类")

#### 软件构件

![J2EE](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4xi19klhywo0.webp "J2EE")

![重量级与轻量级框架](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5i2z5xd0n8k0.webp "重量级与轻量级框架")

![.NET](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1shw9oux6co0.webp ".NET")

### 嵌入式系统及软件 3-5 _超纲_

#### 嵌入式系统的组成和特点

![嵌入式操作系统的特点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7089o6hoe840.webp "嵌入式操作系统的特点")

![冯诺依曼结构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.14ex5c4elzcw.webp "冯诺依曼结构")

![哈佛结构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6c5e3h1a0eo0.webp "哈佛结构")

![嵌入式系统的组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3awqm214wv80.webp "嵌入式系统的组成")

![嵌入式系统的特性](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6ilkibhoz1o0.webp "嵌入式系统的特性")

![嵌入式系统的分层](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67iw02a1tos0.webp "嵌入式系统的分层")

#### 嵌入式系统的分类

![微处理器分类1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4mgtxfa7vn60.webp "微处理器分类1")
![微处理器分类2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3oyxxpzllck0.webp "微处理器分类2")

![多核微处理器](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6tn60veft380.webp "多核微处理器")

![嵌入式操作系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.9kfz3dgkumo.webp "嵌入式操作系统")

![嵌入式实时操作系统的特点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7grvl523q1g0.webp "嵌入式实时操作系统的特点")

![嵌入式实时操作系统的特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5359j8jrm400.webp "嵌入式实时操作系统的特征")

![嵌入式数据库使用环境特点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1m3oqzzhakw0.webp "嵌入式数据库使用环境特点")

![嵌入式数据库组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4pj3zw951a00.webp "嵌入式数据库组成")

#### 嵌入式软件的组成和特点

![嵌入式软件分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4d1pytpan9y0.webp "嵌入式软件分类")

![板级支持包 BSP](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1cfioc8l9cm8.webp "板级支持包 BSP")

![BootLoader](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4bj678u5b3y0.webp "BootLoader")

![设备驱动程序](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.21y37ylcwwow.webp "设备驱动程序")

![交叉平台开发环境](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4bg0rqv7u3k0.webp "交叉平台开发环境")

![交叉编译与交叉调试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.llahskv7sj4.webp "交叉编译与交叉调试")

![软件开发工具](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.790tw8sh1vo0.webp "软件开发工具")

### 计算机网络 3-5 _超纲_

#### 网络的基本概念

![计算机网络功能和分类1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5a13jyx69e00.webp "计算机网络功能和分类1")
![计算机网络功能和分类2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.pchdfi5sulc.webp "计算机网络功能和分类2")

#### 通信技术

![通信技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6oz6rblhgp80.webp "通信技术")

![绞线](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7ijadk7wygs0.webp "绞线")

![网线安装标准](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1ut73626351c.webp "网线安装标准")

![光纤](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6pbshbhd3r40.webp "光纤")

![无线信道](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4su1zzn9wy60.webp "无线信道")

![通信方向](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5mkk0u56qf40.webp "通信方向")

![通信方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3m3y6cbwnsw0.webp "通信方式")

![交换方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.156hnydapam8.webp "交换方式")

#### 网络技术

![局域网和广域网协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.mmie4lvb0yo.webp "局域网和广域网协议")

![其他考点1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4b66at7qjso0.webp "其他考点1")

![其他考点2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3f1pr02zp7a0.webp "其他考点2")

#### 组网技术

![OSI 七层协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.gdf75l2zhbk.webp "OSI 七层协议")

![TCP/IP 协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.sqyzglyo3kw.webp "TCP/IP 协议")

![网络层协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.53373fvqn1s0.webp "网络层协议")

![传输层协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1emz9325c274.webp "传输层协议")

![应用层协议](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.688vsxjc7l40.webp "应用层协议")

![协议端口对照表](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.gh9fx41mf34.webp "协议端口对照表")

![交换机的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2xuh3sxgs5i0.webp "交换机的功能")

![路由器的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5y4rhk2fj8c0.webp "路由器的功能")

![IP 地址的表示](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5d9he7ynk9g0.webp "IP 地址的表示")

![IP 地址的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6b6twlatpok0.webp "IP 地址的分类")

![特殊 IP 地址](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1vg8jr7xi9k0.webp "特殊 IP 地址")

![子网划分](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1wk0lxljtm80.webp "子网划分")

![IPV6](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5v04cgmdqys0.webp "IPV6")

![网络规划三层模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3ttf5hm4niq0.webp "网络规划三层模型")

![建筑物综合布线系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3vwco7coc5s0.webp "建筑物综合布线系统")

##### 相关公式

- 子网个数: 用划分了子网号后的网络号位数 - 原来的网络号位数，作为的 2 的幂，求 2 的幂次方
- 可使用的主机个数: 32 - 网络号位数，作为 2 的幂，求 2 的幂次方在减 2

##### 相关题型解题思路

- 考察 OSI 七层协议: 主要考察各层的协议、功能、设备。
- 考察 TCI/IP 协议: 主要考察功能
- 求子网个数: 通常给出两个 IP 地址，可以根据后面的网络号的位数减一下，代入公式计算。
- 求可用主机数: 只要算出来网络号的位数后，代入公式很容易计算。
- 求不属于网络的子网地址: 判断方式是看网络号是否相同，而网络号在左边，然后从 2 进制的角度来讲，数字越大越考左，所以大概率是最大的那个数。

### 计算机语言

![计算机语言概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2lbetdgjyyc0.webp "计算机语言概述")

![计算机语言的分类1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1xqngs521vnk.webp "计算机语言的分类1")
![计算机语言的分类2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1lgjqsw9t2bk.webp "计算机语言的分类2")

### 多媒体

![媒体的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.54wobnpoys00.webp "媒体的分类")

![多媒体的重要特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3qgpcfdagu00.webp "多媒体的重要特征")

![多媒体系统的基本组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7cg0bjgjhzk0.webp "多媒体系统的基本组成")

![多媒体系统的关键技术1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2o6lnyzumhe0.webp "多媒体系统的关键技术1")
![多媒体系统的关键技术2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3hlabp3qidw0.webp "多媒体系统的关键技术2")
![多媒体系统的关键技术3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.61lm67njx5k0.webp "多媒体系统的关键技术3")

### 系统工程 ✰

![系统工程方法1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1hspdvtdkskg.webp "系统工程方法1")
![系统工程方法2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.134qojvgz1i8.webp "系统工程方法2")
![系统工程方法3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3bmjbpf860s0.webp "系统工程方法3")
![系统工程方法4](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4j1y4yfu2lg0.webp "系统工程方法4")

![系统工程的生命周期1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1f5vu2w0w2f4.webp "系统工程的生命周期1")
![系统工程的生命周期2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.226r5l0ppwu8.webp "系统工程的生命周期2")

![基于模型的系统工程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4bw9naeriys0.webp "基于模型的系统工程")

### 系统性能 1-2

![性能指标1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.llhl0gkjkts.webp "性能指标1")
![性能指标2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2p55uuqhp000.webp "性能指标2")
![性能指标3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.og35ydk5ckg.webp "性能指标3")

![性能评测方法1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.78mcto4d1zk0.webp "性能评测方法1")
![性能评测方法2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6hwd2bqgbx00.webp "性能评测方法2")

![阿姆达尔解决方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67ps4puigzk0.webp "阿姆达尔解决方法")

## 信息系统基础知识 3 _超纲_

### 信息系统概述

![信息系统的定义](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4kklg59med20.webp "信息系统的定义")

![信息系统的发展](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7dbm654l25s0.webp "信息系统的发展")

![信息系统的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3s4kiwu2v9s0.webp "信息系统的分类")

![信息系统的应用](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6s1gtsljsc40.webp "信息系统的应用")

![信息系统的生命周期1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1g48xqs4xluo.webp "信息系统的生命周期1")
![信息系统的生命周期2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1mo2i4w2a22o.webp "信息系统的生命周期2")

![信息系统结构化开发方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3qdujr8fkiy0.webp "信息系统结构化开发方法")
![信息系统原型化开发方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6gmyyezvus00.webp "信息系统原型化开发方法")
![信息系统面向对象开发方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6c0dbeaxc280.webp "信息系统面向对象开发方法")
![信息系统面向服务开发方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1zein9luuwrk.webp "信息系统面向服务开发方法")

### 业务处理系统 TPS

![业务处理系统1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5sipr68g35k0.webp "业务处理系统1")
![业务处理系统2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.42wpqyu0y060.webp "业务处理系统2")

### 管理信息系统 MIS

![管理信息系统1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.naxh8wtm3bk.webp "管理信息系统1")
![管理信息系统2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6jjmz5kxjzs0.webp "管理信息系统2")

### 决策支持系统 DSS

![决策支持系统1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6mswpw1qj3k0.webp "决策支持系统1")
![决策支持系统2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.68dt1eeclyo0.webp "决策支持系统2")
![决策支持系统3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.po76xzn5aio.webp "决策支持系统3")

### 专家系统 ES

![专家系统1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.75v7b20dxqo0.webp "专家系统1")
![专家系统2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.ei2mczwr1kg.webp "专家系统2")

### 办公自动化系统 OAS

![办公自动化系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.xhlygqhii74.webp "办公自动化系统")

### 企业资源规划 ERP

![企业资源规划1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4vfsk3asuk60.webp "企业资源规划1")
![企业资源规划2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4ldn4wk4bcw0.webp "企业资源规划2")
![企业资源规划3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4irzuf0qkvu.webp "企业资源规划3")
![企业资源规划4](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.483zry7jf040.webp "企业资源规划4")

### 典型信息系统架构模型

![政府信息化和电子政务](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.lj81zy0fmxs.webp "政府信息化和电子政务")

![企业信息化和电子商务](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1c75djnv969s.webp "企业信息化和电子商务")

![企业信息化方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ozp341opm40.webp "企业信息化方法")

![电子商务](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3nbv442pjes0.webp "电子商务")

### 信息化战略体系

![信息化战略体系1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7hvk3pj7r700.webp "信息化战略体系1")
![信息化战略体系2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.24ixvktlaie8.webp "信息化战略体系2")

### 信息系统战略规划

![信息系统战略规划1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1dtmxhzp8qo0.webp "信息系统战略规划1")
![信息系统战略规划2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ofrbn4h21i0.webp "信息系统战略规划2")

### 客户关系管理 CRM

![客户关系管理1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5r5s1br6fow0.webp "客户关系管理1")
![客户关系管理2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5emtai7vegk0.webp "客户关系管理2")
![客户关系管理3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.19m3mplfc5mo.webp "客户关系管理3")

### 供应链管理 SCM

![供应链管理1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6fko2do1l740.webp "供应链管理1")
![供应链管理2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6qj45flv1w80.webp "供应链管理2")

### 企业应用集成 EAI

![企业应用集成1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4uc0hwx74360.webp "企业应用集成1")
![企业应用集成2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4wkgir3vz020.webp "企业应用集成2")
![企业应用集成3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.15ddslyjryqk.webp "企业应用集成3")
![企业应用集成4](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6xcon5frfwk0.webp "企业应用集成4")
![企业应用集成5](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3mes3ddu48o0.webp "企业应用集成5")
![企业应用集成6](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.18k3di2prd5s.webp "企业应用集成6")

## 信息安全技术基础知识 2-4

### 信息安全基础知识

![信息安全的基本要素](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1cvo09vimpog.webp "信息安全的基本要素")

![信息安全的范围](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.8vj5xgfxzv4.webp "信息安全的范围")

![信息的存储安全](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3lzlxjg8fvg.webp "信息的存储安全")

![网络安全](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3t5e8t4d0uk0.webp "网络安全")

![防火墙](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4j8qq03flau0.webp "防火墙")

![入侵检测系统 IDS](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2rppvn5hax60.webp "入侵检测系统 IDS")

![入侵防御系统 IPS](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1490gryt6xts.webp "入侵防御系统 IPS")

![网络攻击和威胁](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6nlgolnu2ig0.webp "网络攻击和威胁")

![网络安全协议1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3lbougkf18m0.webp "网络安全协议1")
![网络安全协议2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1jyvvphpugo0.webp "网络安全协议2")
![网络安全协议3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1xwk5cd7ug2o.webp "网络安全协议3")

### 信息安全系统的组成框架

![技术体系](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.35945x7zm560.webp "技术体系")

### 信息加解密技术

![加密技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1zbnulg8w08w.webp "加密技术")

![对称加密技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.417o165qlzo0.webp "对称加密技术")

![非对称加密技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3hsyt86rj680.webp "非对称加密技术")

![数字信封](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3e4xd38fjiw0.webp "数字信封")

![信息摘要](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1ugzjlyiaz7k.webp "信息摘要")

### 密钥管理技术

![公钥基础设施](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4wphatvlzv20.webp "公钥基础设施")

### 访问控制及数字签名技术

![访问控制](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5f7oros0mbk0.webp "访问控制")

![数字签名](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.vqzix2q6w2o.webp "数字签名")

### 信息安全的抗攻击技术

![拒绝服务攻击](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4syz8gicum80.webp "拒绝服务攻击")

![拒绝服务攻击的抵御](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.53mzkx66ufc0.webp "拒绝服务攻击的抵御")

![ARP 欺骗原理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.47qeluysgic0.webp "ARP 欺骗原理")
![ARP 欺骗的防范](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7sp00fg2xdg0.webp "ARP 欺骗的防范")

![DNS 欺骗](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4qm78t44iz20.webp "DNS 欺骗")

![IP 欺骗](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3sfzplhfqzo0.webp "IP 欺骗")

![端口扫描](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1lct1nc5qjfk.webp "端口扫描")

### 信息安全的保障体系与评估方法

![计算机系统安全保护能力的等级](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.321blbsz1180.webp "计算机系统安全保护能力的等级")

![风险评估](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1z74skdaezwg.webp "风险评估")

## **软件工程基础知识 12-15**

### 软件工程

#### 软件工程定义

![软件工程概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3pn9h8ep2420.webp "软件工程概述")

![能力成熟度模型 CMM](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.tjfekd51vpc.webp "能力成熟度模型 CMM")

![能力成熟度模型集成 CMMI 1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.77vknxg4k6s0.webp "能力成熟度模型集成 CMMI 1")
![能力成熟度模型集成 CMMI 2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4vnh1mejsqo0.webp "能力成熟度模型集成 CMMI 2")

#### 软件过程模型

![瀑布模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4dadwg7fevs0.webp "瀑布模型")

![原型模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.23rgwkkevbxc.webp "原型模型")

![螺旋模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5nweqzehg6c0.webp "螺旋模型")

![V 模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.15s1yek6z0qo.webp "V 模型")

![增量模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2o4xem5ga7q0.webp "增量模型")

![其他模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.u4avqx51640.webp "其他模型")

![敏捷模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.j0u0m7rhmg8.webp "敏捷模型")
![敏捷模型方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.43k8xlq80ew0.webp "敏捷模型方法")

![统一过程模型1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1t6t2tqz3yjk.webp "统一过程模型1")
![统一过程模型2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5q2vvmuuvdc0.webp "统一过程模型2")
![统一过程模型3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.xey90hzodpc.webp "统一过程模型3")

![逆向工程1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5fpszt5m0e80.webp "逆向工程1")
![逆向工程2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4thzd2beh8g0.webp "逆向工程2")

### 需求工程

![软件需求1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4e3c1lln8h00.webp "软件需求1")
![软件需求2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2x1bvftmfrk0.webp "软件需求2")

![需求获取](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.30jr9ue3tn80.webp "需求获取")

![需求分析](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.709udxsog0c0.webp "需求分析")

![结构化的需求分析](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6gvjcfkkmco0.webp "结构化的需求分析")

![数据流图1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.46ln3lb4pke0.webp "数据流图1")
![数据流图2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6euvcqdir5k0.webp "数据流图2")
![分层数据流图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1yhtsyr6dj34.webp "分层数据流图")

![数据字典](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.76z66jq6b2w.webp "数据字典")

![需求定义](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.18mjzqkxsq3k.webp "需求定义")

![需求验证](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5lmza1w3v2g0.webp "需求验证")

![需求管理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.446ehphzjjc0.webp "需求管理")

![需求变更和风险](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3hgycw0gfuu0.webp "需求变更和风险")

![需求跟踪](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2l3qbuiwq720.webp "需求跟踪")

### 系统分析与设计

![系统设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.39bc1t61x6w0.webp "系统设计")

![系统设计原理和原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5kw3kp8qd9k0.webp "系统设计原理和原则")

![内聚分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7fp6io58keo0.webp "内聚分类")

![耦合分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.16wx0abix7gg.webp "耦合分类")

![人机界面设计原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7g0wc6lk4nw0.webp "人机界面设计原则")

### 软件测试

![测试原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67j33abek980.webp "测试原则")

![静态测试和动态测试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2h3hc5h2q400.webp "静态测试和动态测试")

![测试阶段1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.h8559yneqvc.webp "测试阶段1")
![测试阶段2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6qmd4jn8cpc0.webp "测试阶段2")

![测试策略](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ut87t7xkck0.webp "测试策略")

![黑盒测试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6e0qo9tku8w0.webp "黑盒测试")

![白盒测试1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.698iziqra6k0.webp "白盒测试1")
![白盒测试2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.21tr95jrc2hs.webp "白盒测试2")
![白盒测试3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6ygd5q0dus80.webp "白盒测试3")

![调试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ndsstia3cg0.webp "调试")

![软件度量](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6osscpx6tx80.webp "软件度量")

### 净室软件工程

![净室软件工程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2j9kadf30yw0.webp "净室软件工程")

### 基于构件的软件工程

![基于构件的软件工程的特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.dzk7tadoiiw.webp "基于构件的软件工程的特征")
![基于构件的软件工程1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4sp4rj7qhes0.webp "基于构件的软件工程1")
![基于构件的软件工程2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.9l8bz9n84so.webp "基于构件的软件工程2")

### 软件项目管理

#### 相关概念

![进度管理的过程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.113s21atlkb4.webp "进度管理的过程")

![进程安排的常用图形描述方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3d71zhga0de0.webp "进程安排的常用图形描述方法")

![关键路径法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1llrm3yu71kw.webp "关键路径法")
![7 格图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7gqli8bm3t40.webp "7 格图")
![浮动时间](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4qs7gznb7b40.webp "浮动时间")

![配置管理概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2qbsppph4ns0.webp "配置管理概述")
![配置项](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3783w9wctqa0.webp "配置项")
![配置项的状态](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6inmy4llqpk0.webp "配置项的状态")
![配置项版本](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.60dp8gdf15s0.webp "配置项版本")

![质量管理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3sl3rozcp2m.webp "质量管理")

![风险管理1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.40emcf9qpzm0.webp "风险管理1")
![风险管理2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5im9nqm7ks0.webp "风险管理2")

#### 相关公式

- 总浮动时间 1: 关键路径 - 活动路径
- 总浮动时间 2: 最迟开始 LS - 最早开始 ES
- 总浮动时间 3: 最迟完成 LF - 最早完成 EF
- 自由浮动时间: 紧后活动最早开始 LS 中的最小的 - 本活动的最早完成 EF

#### 相关题型解题思路

- 求项目最短工期: 通常给出项目计划评审(PERT)图，或者给个表格让你自己画下图，肉眼观察下找到最长的路径就是最短工期
- 求某活动的浮动时间: 先找最长路径，用最长路径 - 活动所在路径就是浮动时间

### 处理流程设计

![流程表示工具](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4xdb4ank63c0.webp "流程表示工具")

![业务流程重组](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.664dkgz52f40.webp "业务流程重组")

![业务流程管理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.41qo5s1kozq0.webp "业务流程管理")

### 系统转换和维护

![遗留系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6khpg007qy80.webp "遗留系统")

![系统转换方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.m2md1tgyddc.webp "系统转换方式")

![系统维护](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1monrsvm7v0g.webp "系统维护")

## 数据库设计基础知识 3-5

### 数据库基本概念

#### 数据库的基本特征

![数据库的基本特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.191f8qq6f1kw.webp "数据库的基本特征")

#### 数据库系统与数据库管理系统

![数据库系统与数据库管理系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.37h9jxeop740.webp "数据库系统与数据库管理系统")

#### 三级模式两级映像

![三级模式两级映像](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4xrvqgybsj80.webp "三级模式两级映像")

#### 数据模型分类与数据模型三要素

![数据模型分类与数据模型三要素](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1t4qn0udkou8.webp "数据模型分类与数据模型三要素")

#### E-R 模型

![E-R 模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3zjeo8s5jem0.webp "E-R 模型")

#### 关系模型的相关定义

![关系模型的相关定义](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5c5pc1fefds0.webp "关系模型的相关定义")

#### 关系模型优缺点

![关系模型优缺点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1pvv2q4g0xk0.webp "关系模型优缺点")

#### E-R 模型转关系模型

![E-R 模型转关系模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3ht5wfvcgt20.webp "E-R 模型转关系模型")

### 关系数据库

#### 关系代数并、交、差

![关系代数并、交、差](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.r05gox34s1c.webp "关系代数并、交、差")

#### 关系代数笛卡尔积、投影、选择

![关系代数笛卡尔积、投影、选择](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.53od7g3d1cg0.webp "关系代数笛卡尔积、投影、选择")

#### 关系代数自然连接

![关系代数自然连接](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2p08mdqw7u20.webp "关系代数自然连接")

#### 函数依赖规则

![函数依赖规则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6ekmpcoz8380.webp "函数依赖规则")

#### 函数依赖的公理系统

![函数依赖的公理系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.76imy2qc0wc0.webp "函数依赖的公理系统")

#### 键与约束

![键与约束](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.64h6x2fudc4.webp "键与约束")

#### 模式分解

![模式分解1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7j4ghkffvi40.webp "模式分解1")
![模式分解2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.682z4d6u4gg0.webp "模式分解2")
![模式分解3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.omahc7zk2uo.webp "模式分解3")

#### 相关题型解题思路

- 考察函数依赖的公理系统: 背下并理解四率两规则及其对应的数学代数表示。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3elkf4e09ho0.webp)
- 求元组个数和属性列数: 属性列很简单，自然连接求交集，笛卡尔积求并集，元组个数是，通过属性列相同且值相同连接后剩余的行数。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1svhfsvafz5s.webp)
- 求等价的关系代数表达式：常见的就是给个自然连接的表达式，等价的是一个笛卡尔积的表达式，笛卡尔积转自然连接需要经过投影和选择。**还有能用数字代替列名，从 1 开始，如果表达式中看到带引号的数字可以直接排除**。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3ux3o3ymu920.webp)
- 求关系代数等价的 SQL: 通常就是考察投影和选择，主要是行的问题，把属性列写一下很容易就能答出来。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6vbmh2dgmgo0.webp)
- 求候选键/属性闭包等式成立的代数表达式: 根据依赖集找出从未在右边出现过的属性，其必然是候选键之一，然后以其为基础看看能不能遍历所有属性，将无法遍历的加入候选键中。属性闭包表达式括号里所有属性，能求出依赖的所有属性就是闭包等式成立，通常就是全部候选键。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4pcplcadb140.webp)
- 求模式分解后是否保持函数依赖、是否无损连接: 是否保持函数依赖先求分解后的模式分别的函数依赖，如果拆分后的属性，包含了原来的依赖关系中的所有属性，那么就能继承相应的依赖关系。然后如果剩余全部未被包含的依赖能通过函数依赖的公理系统得到，那么就能说保持了函数依赖。是否保持无损连接分解后的模式先求交集，然后看交集的属性能不能推出，任意一个差集里的属性，如果可以那就算无损连接。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6g9hbzkcenw0.webp)

### 数据库设计

#### 数据库设计

![数据库设计阶段](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5dzoaaxpfaw0.webp "数据库设计阶段")

#### 第一范式

![第一范式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5qei5j4x6tw0.webp "第一范式1")
![第一范式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2m933rm0do80.webp "第一范式2")

#### 第二范式

![第二范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2sw5n9mldvo0.webp "第二范式")

#### 第三范式

![第三范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6twirr83ghc0.webp "第三范式")

#### BC 范式

![BC范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3yni6tbwn540.webp "BC范式")

#### 反规范化技术

![反规范化技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5kt1osw7mwg0.webp "反规范化技术")

#### 相关题型解题思路

- 求属于概念结构设计的什么冲突: 理解概念结构的冲突。**如果连着解决冲突的方式一起考，也可以根据解决方式倒推冲突类型**
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1335yuslpl0g.webp)
- 求关系模式达到了第几范式: 理解各种范式的限定条件。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4mdz4t1ajta0.webp)

### 规范发和并发

#### 并发控制

![并发控制1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2i75upllyj40.webp "并发控制1")
![并发控制2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6g3ytt1vz1g0.webp "并发控制2")

#### 封锁协议

![封锁协议1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.55ujp9qldz00.webp "封锁协议1")
![封锁协议2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3bsu6p7e8wo0.webp "封锁协议2")
![封锁协议3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.yy6tuoni09c.webp "封锁协议3")

#### 相关题型解题思路

- 求事务能否加锁成功: 很简单，排它(写)锁就是一个事务加了，其他事务什么锁也加不了。共享(读)锁就是一个事务加了，其他事务只能加共享(读)锁，不能加排它(写)锁。
  ![alt](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7b4qv3t1rr00.webp)

### 数据库新技术

#### 数据库安全

![数据库安全](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3cv1j4ljnny0.webp "数据库安全")

#### 数据库备份

![数据库备份](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3tqyj91k41o0.webp "数据库备份")

#### 分布式数据库

![分布式数据库](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5fjzuunsuas0.webp "分布式数据库")

#### 数据仓库技术

![数据仓库技术1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5a5firz8ynw0.webp "数据仓库技术1")
![数据仓库技术2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7kpdbrrtbn40.webp "数据仓库技术2")
![数据仓库技术3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2cadqwnfv30g.webp "数据仓库技术3")

#### 大数据

![大数据](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7b421s6py9c0.webp "大数据")

## **系统架构设计的基础知识 15**

### 软件架构概念

![软件架构概述1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.33ejy13bq8u0.webp "软件架构概述1")
![软件架构概述2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.45cn657azgs0.webp "软件架构概述2")

![软件架构设计与生命周期1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6brsxetodww0.webp "软件架构设计与生命周期1")
![软件架构设计与生命周期2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3p8ov2qwe060.webp "软件架构设计与生命周期2")

![构件的基本概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1qmjow4ipc1s.webp "构件的基本概念")

![构件与对象的特性](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1fc6p3uyjugw.webp "构件与对象的特性")

![构件接口与面向构件编程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.47w478ab28e0.webp "构件接口与面向构件编程")

![构件技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.31kkzrl1amq0.webp "构件技术")

### 基于架构的软件开发方法

![ABSD方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7c90nb3oyuo0.webp "ABSD方法")

![基于架构的软件开发过程1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2nmijp2nsfu0.webp "基于架构的软件开发过程1")
![基于架构的软件开发过程2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5irvz3bbtio0.webp "基于架构的软件开发过程2")
![基于架构的软件开发过程3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4fzrm4jp9wy0.webp "基于架构的软件开发过程3")

### 软件架构风格

![软件架构风格概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.65ygvxr8g2c0.webp "软件架构风格概述")

![软件架构风格的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4k839sfcmmq0.webp "软件架构风格的分类")

![数据流风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1r4kdemcihkw.webp "数据流风格")

![调用返回风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3xcc9yzy0j40.webp "调用返回风格")

![独立构件风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7ecmzadwv380.webp "独立构件风格")

![虚拟机风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3ok68cn1v9i0.webp "虚拟机风格")

![仓库（数据共享）风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3cpj11ftdmg0.webp "仓库（数据共享）风格")

![闭环控制风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.45e7vwag3ay0.webp "闭环控制风格")

![C2架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.dkoytlnsxyo.webp "C2架构风格")

![架构风格简介](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ruao32fwks0.webp "架构风格简介")

### 软件架构复用

![软甲架构复用](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4do65se1qjc0.webp "软甲架构复用")

### 特定领域软件体系结构

![DSSA的概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5lno3cgwhsg0.webp "DSSA的概念")

![DSSA的三个基本活动](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1a3bydlyrahs.webp "DSSA的三个基本活动")

![DSSA的四种角色人员](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.xbstjlaiyww.webp "DSSA的四种角色人员")

![建立DSSA的过程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1ef04rcct0hs.webp "建立DSSA的过程")

![三层次模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2r7sqrswz1k0.webp "三层次模型")

### _层次架构风格_

![两层C/S架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hvzhnuqjh00.webp "两层C/S架构风格")

![三层C/S架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3pd4dhzuari0.webp "三层C/S架构风格")

![三层B/S架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6fx9senl5m00.webp "三层B/S架构风格")

![富互联网应用RIA](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6wv98brnmi80.webp "富互联网应用RIA")

![MVC架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3fi5psmi0fy0.webp "MVC架构风格")

![MVP架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.42m6gsq4rzq0.webp "MVP架构风格")

![MVVM架构风格](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6gqwqtkdr240.webp "MVVM架构风格")

## **系统质量属性与架构评估 15**

### 软件系统质量属性

![软件系统质量属性](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2s4vrihswus0.webp "软件系统质量属性")

![面向架构评估的质量属性1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6fm58jtwnxw0.webp "面向架构评估的质量属性1")
![面向架构评估的质量属性2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5w8fgp83oxc0.webp "面向架构评估的质量属性2")

![质量属性的场景](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3wn1adb2xm80.webp "质量属性的场景")

### 系统架构评估

![软件架构评估的概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.47qlp3y6js40.webp "软件架构评估的概念")

![三种常用的评估方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3w5ibwlheio0.webp "三种常用的评估方式")

![基于场景的架构分析方法SAAM](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4o2fkxbye5y0.webp "基于场景的架构分析方法SAAM")

![架构权衡分析法ATAM](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.pfc64ta4eww.webp "架构权衡分析法ATAM")

![成本效益分析法CBAM](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.p256hb858xc.webp "成本效益分析法CBAM")

![其他评估方法1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7ii3ua4j7d00.webp "其他评估方法1")
![其他评估方法2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.58s3mj1wez80.webp "其他评估方法2")

## 软件可靠性基础知识 2

### 软件可靠性基本概念

![软件可靠性的基本概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.mpuwvlrz8j4.webp "软件可靠性的基本概念")

![串联系统与并联系统的可靠性](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.678jt43ccgw0.webp "串联系统与并联系统的可靠性")

![软件可靠性的测试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.68ys280et5s0.webp "软件可靠性的测试")

### 软件可靠性建模

![软件可靠性建模1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6fatlh4pd8c0.webp "软件可靠性建模1")
![软件可靠性建模2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6qanb26k5740.webp "软件可靠性建模2")

### 软件可靠性管理

![软件可靠性管理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1x4zmr8nkqps.webp "软件可靠性管理")

### 软件可靠性设计

![软件可靠性设计原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4onelptveei0.webp "软件可靠性设计原则")

![软件容错技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2sxfq83y00s0.webp "软件容错技术")

![N 版本程序设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3vn3gygnipg0.webp "N 版本程序设计")
![恢复块设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.52gg9pooihc0.webp "恢复块设计")
![二者比较](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5g0jd9b92ag0.webp "二者比较")

![防卫式程序设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.36gcaghwx5k0.webp "防卫式程序设计")

![双机容错技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4yj5de38u0o.webp "双机容错技术")

![集群技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4sxp5kg861w0.webp "集群技术")

![负载均衡](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6jfp6t8mto00.webp "负载均衡")

### 软件可靠性测试

![软件可靠性测试](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1wcmr9i7908w.webp "软件可靠性测试")

### 软件可靠性评价

![软件可靠性评价](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.8x7fbhuma48.webp "软件可靠性评价")

## 软件架构的演化和维护 2

### 软件架构演化和定义的的关系

![软件架构演化和定义](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6ono1266iqk0.webp "软件架构演化和定义")

### 面向对象软件架构演化过程

![对象演化和消息演化](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7281rflwi8w0.webp "对象演化和消息演化")

![复合片段演化和约束演化](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.74621oils8c0.webp "复合片段演化和约束演化")

### 软件架构演化方式的分类

![软件架构演化方式的分类1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3li6sphxjhk0.webp "软件架构演化方式的分类1")
![软件架构演化方式的分类2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.56zsxmh0m240.webp "软件架构演化方式的分类2")
![软件架构演化方式的分类3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hcoq8au8gk0.webp "软件架构演化方式的分类3")
![软件架构演化方式的分类4](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5dxlujkqpac0.webp "软件架构演化方式的分类4")

### 软件架构演化原则

![软件架构演化原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ati8q0iw4e8.webp "软件架构演化原则")

### 软件架构演化评估方法

![软件架构演化评估方法1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.23hfcg3usyqo.webp "软件架构演化评估方法1")
![软件架构演化评估方法2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5zlu311am6c0.webp "软件架构演化评估方法2")

### 大型网站系统架构演化实例

![大型网站架构演化1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5c4isrhvyjk0.webp "大型网站架构演化1")
![大型网站架构演化2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.62lr2vizusw0.webp "大型网站架构演化2")

### 软件架构维护

![软件架构维护](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.185wxsbvi03g.webp "软件架构维护")

## 未来信息综合技术 2-3

### 信息物理系统技术概述

![CPS 体系架构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6gq4dy62wno0.webp "CPS 体系架构")

![CPS 技术体系](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2n980fq0kxy0.webp "CPS 技术体系")

![CPS 应用场景](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2126qkdjimg0.webp "CPS 应用场景")

### 人工智能技术概述

![人工智能1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.152nf82n2psw.webp "人工智能1")
![人工智能2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.37hyd8cn3pw0.webp "人工智能2")
![人工智能3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.vra5s2ya14g.webp "人工智能3")

### 机器人技术概述

![机器人核心技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.219rohhquuao.webp "机器人核心技术")

![机器人分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1ykdyu7r48ps.webp "机器人分类")

### 边缘计算概述

![边缘计算概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2zlhptkkz4q0.webp "边缘计算概念")
![边缘计算特点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.ma7azror3k0.webp "边缘计算特点")
![边缘计算协同](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.18i80yhbya8w.webp "边缘计算协同")

### 数字孪生体技术概述

![数字孪生体](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1etkqy1lvlnk.webp "数字孪生体")

### 云计算和大数据技术概述

![云计算的服务方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5k35fkykokw0.webp "云计算的服务方式")

![云计算的部署模式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4t4otu10hp20.webp "云计算的部署模式")

![大数据](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.um80oj0uee8.webp "大数据")

# 下篇

## 面向服务的架构设计与理论实践

![SOA的概念1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ginldmlou40.webp "SOA的概念1")
![SOA的概念2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1slxcr3tvb1.webp "SOA的概念2")

![SOA的关键技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1uyzz8b9fy2.webp "SOA的关键技术")

![SOA的实现方式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.522v3mf7en00.webp "SOA的实现方式1")
![SOA的实现方式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6zio1sbc48g0.webp "SOA的实现方式2")

# 拓展

## 案例分析

### 案例分析历年考点分析

![案例分析历年考点分析](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2h10pysjksu0.png "案例分析历年考点分析")

### 案例分析解题技巧

![案例分析解题技巧](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67gmh3mvlg00.png "案例分析解题技巧")

## 面向对象技术 3-5

### 面向对象开发

![面向对象的基本概念1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5x2glj4vs6c0.webp "面向对象的基本概念1")
![面向对象的基本概念2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7202n1zp3vw0.webp "面向对象的基本概念2")
![面向对象的基本概念3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3nzldz5pt5k0.webp "面向对象的基本概念3")

![面向对象的分析建模](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4d8f09sina60.webp "面向对象的分析建模")

![面向对象的设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3xic8hftvcc.webp "面向对象的设计")

![面向对象的设计原则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.21cx3ymp9r0g.webp "面向对象的设计原则")

![面向对象软件的测试层次](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6n5bcofc2js0.webp "面向对象软件的测试层次")

### 统一建模语言 UML

![UML 的结构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ayoarp30a00.webp "UML 的结构")

![UML 的事物](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.204bcxcyslhc.webp "UML 的事物")

![UML 的关系](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.76k7nu9r7i80.webp "UML 的关系")

![UML 的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1sqgnoleeav4.webp "UML 的分类")

![类图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.vfkc8sogi9c.webp "类图")

![对象图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.38b756olc5u0.webp "对象图")

![用例图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3tqgt7wwpso0.webp "用例图")

![序列图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.152nf78oo5eo.webp "序列图")

![通信图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5se35jl1zsg0.webp "通信图")

![状态图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3gbzreo7h500.webp "状态图")

![活动图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1nihtfnw1zy8.webp "活动图")

![构件图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ky7tqcqnjm0.webp "构件图")

![部署图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.13qp5g4kncow.webp "部署图")

![UML 视图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6yrscew3tgw0.webp "UML 视图")

### 设计模式

![设计模式的概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6xusva4yddc0.webp "设计模式的概述")

![创建型设计模式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5jssyxvg9ak.webp "创建型设计模式")

![结构型设计模式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4oa42fn1amu0.webp "结构型设计模式")

![行为型设计模式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4aj4u8ga8zq0.webp "行为型设计模式1")
![行为型设计模式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.669ecjzd4uk0.webp "行为型设计模式2")
