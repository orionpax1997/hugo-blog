---
title: "软考-系统架构师"
date: 2023-08-06T18:21:01+08:00
draft: true
---

## 计算机系统基础知识

### 计算机硬件 ✰

#### 相关概念

##### 计算机硬件组成

![计算机硬件组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.50u9cjryeck0.png "计算机硬件组成")

##### 处理器

![CPU 的功能](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5nujeeacm3o0.webp "CPU 的功能")

![CPU 的组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.fmceksfw06w.webp "CPU 的组成")

##### 存储器

![分级存储体系与局部性原理](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.33dkhwgef0o0.webp "分级存储体系与局部性原理")

![Cache 概念](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5hxgdiahn3g.webp "Cache 概念")

![Cache 映像方式1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5ep6d4fesqk0.webp "Cache 映像方式1")
![Cache 映像方式2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.17iz0rps4rxc.webp "Cache 映像方式2")

![Cache 替换算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2ow3qsbt8vm0.webp "Cache 替换算法")

![Cache 命中率及平均时间](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.29nk73n2unb4.webp "Cache 命中率及平均时间")

![磁盘结构和参数](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1oeoxoad1p4w.webp "磁盘结构和参数")

![磁盘调度算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.15ryesazcin4.webp "磁盘调度算法")

![内存与接口地址的编址方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.b1pnqtuf1ug.webp "内存与接口地址的编址方法")

##### 总线

![总线的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5kdhmitxwic0.webp "总线的分类")

##### 外部设备

![计算机和外设间的数据交互方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5zlfwjwdgg40.webp "计算机和外设间的数据交互方式")

##### 指令

![计算机指令的组成和执行过程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6qdek30lpc80.webp "计算机指令的组成和执行过程")

![计算机指令的寻址方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.ou2ih4m6j5s.webp "计算机指令的寻址方式")

![计算机指令的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.733cz61t52g0.webp "计算机指令的分类")

![指令流水线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5t6g10ok4v40.webp "指令流水线")

##### 校验码

![奇偶校验码](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1pgi3nxmcx4w.webp "奇偶校验码")

![CRC 循环冗余校验码1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.24v5f4oszysg.webp "CRC 循环冗余校验码1")
![CRC 循环冗余校验码2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1elsprl1sue8.webp "CRC 循环冗余校验码2")

#### 相关公式

- 磁道记录的最大等待时间: 就是旋转一周的时间
- 磁道记录的最小等待时间: 就是 0
- 磁道按顺序排列的记录等待时间: 旋转一周的时间 - 处理时间
- 磁道记录的总处理时间: (旋转一块的时间 + 处理时间) _ 总块数 + 等待时间 _ (总块数 - 1)
- 流水线周期: 指令分成不同执行段，其中执行时间最长的段为流水线周期
- 流水线执行时间1: 1 条指令的总执行时间 + (总指令条数 - 1) \* 流水线周期
- 流水线执行时间2: (1 条指令的总执行时间 - 流水线周期) + 总指令条数 \* 流水线周期
- 流水线的吞吐率: 吞吐率即为单位时间内执行的指令条数 = 指令条数 / 流水线执行时间
- 流水线的加速比: 不使用流水线的执行时间 / 使用流水线的执行时间
- 流水线的最大加速比: 1 条指令不使用流水线的执行时间 / 流水线周期
- CRC 编码: 1. 在原始信息串后面补多项式的阶个零; 2. 求除数，多项式中幂指数存在的为 1，不存在为 0; 3. 求校验码，进行模 2 除(异或运算)，**余数如果不足多项式的阶的位数则在左边补 0**

#### 相关题型解题思路

- 求磁盘调度的响应序列: 按照采用的调度算法，来求序列，多个相同柱面号的情况下，扇区号由小到大排列，磁头号是无效信息。
- 求磁道记录的最长处理时间和最少处理时间: 通常给出逻辑记录的安排顺序表，磁盘的每周旋转速度，每个记录的处理时间，需要**注意还有个隐含的条件是磁盘的每块的旋转时间，且当前快数据旋转读取完后才能开始处理**，求出隐含条件后带入公式计算。
- 求流水线相关问题: 如果是让求吞吐率或加速比，通常情况下需要先求出执行时间，也就是说需要套两个公式;如果碰到和缓冲区结合考察的问题，**注意但单双缓冲区的差异，单缓冲区读入和写出不能同时进行，因此读入和写出的时间需要加在一起算做一段**。而双缓冲区的读入和写出可以同时进行，因此可以算做两段。
- 求流水线最大加速比: 加上最大两个字，就是求极限值了，通常不会给出总指令条数，而需要设为 n 来计算，求极限时忽略常数，带入公式即可。
- 求 CRC 循环冗余校验码: 通常给出原始信息串和生成多项式，让求校验码，套公式即可。

### 计算机软件

#### 操作系统 ✰✰✰✰✰

##### 操作系统

![操作系统的定义](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4ta08p68eug0.webp "操作系统的定义")

![操作系统的功能](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4ozf20qqg6g0.webp "操作系统的功能")

![操作系统的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1hfphfzgmusg.webp "操作系统的分类")

##### 进程管理

![进程的组成和状态](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1qa522vuo20w.webp "进程的组成和状态")

![前趋图](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4cxaged0yjq0.webp "前趋图")

![进程资源图](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.39n1vb9hou20.webp "进程资源图")

![进程同步与互斥](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.u47c4pdg4uo.webp "进程同步与互斥")

![PV 操作](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6i8o5hlsafk0.webp "PV 操作")

![生产者消费者问题](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5hiw1kyeeug0.webp "生产者消费者问题")

![进程调度方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6c2qe0jxwls0.webp "进程调度方式")

![进程调度算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2ty2cv623b60.webp "进程调度算法")

![死锁](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2wqhyeh9wvq0.webp "死锁")

![线程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6lmden7uo1g0.webp "线程")

###### 相关公式

- 每个进程需要资源数不同时发生死锁的最大资源数: (进程1需要的资源数 - 1) + (进程2需要的资源数 - 1) + ... + (进程n需要的资源数 - 1)
- 每个进程需要资源数相同时发生死锁的最大资源数: 系统中的进程数 \* (单个进程需要的资源数 - 1)
- 不发生死锁的最小资源数: 发生死锁的最大资源数 + 1
- 信号量的最大值: 资源数量
- 信号量的最小值: - (进程数量 - 资源数量)

###### 相关题型解题思路

- 考察进程三态图之间的转换: 给定服务调度算法、给定几个进程的当前状态，某进程发生某事件后，求所有进程的后续状态。以三态图的转变带入后解题。
- 考察进程资源图，求阻塞节点：某进程所请求的资源已经全部分配完毕，该进程为阻塞节点。
- 考察进程资源图，求化简顺序：先找非阻塞节点，然后释放其占用资源(划掉连线)后，找后续的非阻塞节点，直到所有节点都不被阻塞。
- **综合考察PV操作**: 给定前趋图，进程，和需要设置的信号量，然后给出进程部分执行过程中的PV操作，求空余的部分的PV操作。结合前趋图来看，从最开始无依赖的进程开始填空，进程执行完进行V操作，有几个后继则进行几次不同信号量的V操作。然后后面等待执行的进行的前驱如果都执行完了，则开始执行，有几个前驱进行几次不同信号量的P操作。
- 求信号量的取值范围: 给定进程数和资源数，求使用PV操作时需要设定的信号量的范围，带入公式计算，信号量为负几，则有几个等待进程。
- 考察银行家算法，求当前可用的资源数和安全的执行序列: 给定资源及其可用资源总数，给定几个进程及其最大需求量和已分配资源数图示。首先用资源的最大总数-当前所有进程分配的数量求出其当前可用的资源数。然后找到所有执行序列中资源最大需求量都能满足的进程，作为可执行的进程，执行完后把这个进程上已分配的资源数加回，可用资源数，再找下一个可执行进程。

##### 存储管理

![分区存储方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.qmuxffsi1n4.webp "分区存储方式")

![分区适应法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.32xww0kvkcy0.webp "分区适应法")

![分页存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2scnsm54dvc0.webp "分页存储")

![页面置换算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.727k1ckq7ms0.webp "页面置换算法")

![快表](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3iiym37nnks0.webp "快表")

![分段存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.18syec51w934.webp "分段存储")

![段页式存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4tqudwbw0om0.webp "段页式存储")

![磁盘冗余阵列技术1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3t761ry4bgk0.webp "磁盘冗余阵列技术1")
![磁盘冗余阵列技术2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.60ydmembgxg0.webp "磁盘冗余阵列技术2")
![磁盘冗余阵列技术3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1cnolw5yuxr.webp "磁盘冗余阵列技术3")

![网络存储技术1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5mtt846n0pw0.webp "网络存储技术1")
![网络存储技术2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2y6ond2fhi20.webp "网络存储技术2")

###### 相关公式

- 页内地址的位数: 每页大小以 2 的 n 次方表示时的 n
- 页号的2进制位数1: 内存大小 / 每页大小，然后求其以 2 的 n 次方表示时的 n
- 页号的2进制位数2: 逻辑地址或物理地址的位数 - 页内地址的位数
- 分页式存储物理地址: 高位通过页号在页表中查到物理块号 拼接 低位页内地址(偏移地址)，**逻辑地址和物理地址中低位的偏移地址不变，区别只是将高位的逻辑页号替换为了物理快号**

###### 相关题型解题思路

- 求分页式存储的物理地址: 通常给出页面大小和逻辑地址，以及页号和物理块号的对应表，让求物理地址。首先通过页面大小算出页内地址的位数，剩余的高位为页号，通过页号找到对应的物理块号，然后将逻辑地址高位替换为物理快号就是物理地址。
- 求淘汰那个页面代价最小: 通常给出一个表格，标识每个页面的状态位、修改位、访问位，根据局部性原理，有限淘汰最近未被访问过的，而后淘汰最近未被修改过的。
- 求段式存储中逻辑地址能否转换为物理地址(不违法)，给定几个(段号，段内偏移)，然后表格中给出段号和段长列，根据短号找到段长，段长大于段内偏移就不违法。

##### 设备管理

![设备管理概述](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1g5x73h6fyqo.webp "设备管理概述")

![I/O 设备](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.34mylt9dmqw0.webp "I/O 设备")

![设备管理技术](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1maz233knxk0.webp "设备管理技术")

#### 文件系统

##### 相关概念

![文件管理概述](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7gs2ocqkw480.webp "文件管理概述")

![文件结构分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3xwfe8q9sgu0.webp "文件结构分类")

![索引文件结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6hs13ibogkg0.webp "索引文件结构")

![文件目录](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.24huvvajhps0.webp "文件目录")

![文件存储空间管理1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5pr9lq294js0.webp "文件存储空间管理1")
![文件存储空间管理2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.67e5ut4ovnc0.webp "文件存储空间管理2")

##### 相关公式

- 一级间接索引逻辑块的个数: 磁盘索引块大小 / 每个地址项的大小
- 二级间接索引逻辑块的个数: (磁盘索引块大小 / 每个地址项的大小) \* (磁盘索引块大小 / 每个地址项的大小)
- 一级间接索引物理块号的表示范围: 直接索引的最大编号 + 1 到 直接索引的最大编号 + 一级间接索引逻辑块的总个数
- 可表示的单个文件的最大长度: 可表示的总的逻辑块数 \* 磁盘数据块大小
- 表示位示图需要的字的个数: 磁盘容量 / 磁盘物理块大小 / 系统字长位数

##### 相关题型解题思路

- 求采用什么索引和可表示的单个文件的最大长度: 通常给出一共几个地址项，以及其中几个直接索引，几个一级间接索引，几个二级间接索引，和每个地址项的大小，以及磁盘索引块和磁盘数据块的大小，然后问访问的逻辑块号应采用的是什么索引。题目中没明确说明时，逻辑块从0开始编号。首先将直接索引进行编号，然后带公式求一级间接索引的表示范围，以上就是二级间接索引的范围，这样就能判断采用的是什么索引。最后只要算出中的表示范围(可表示的总的逻辑块数) 乘以磁盘数据块大小，就能算出可表示的单个文件最大的长度。
- 求相对路径和绝对路径: 通常给出目录结构图，当前工作目录和需要访问的文件名，求相对路径和绝对路径，很简单。注意一点，路径最后的杠可以省略。
- 求需要表示的物理块在位示图中的第几个字描述: 通常需要表示的物理块号，和字长。**注意如果有余数，则向上取整，还有没有明确说明的情况下是从零开始编号的**
- 求位示图需要几个字来表示: 通常给出全部条件带入公式计算即可。

### 嵌入式系统及软件 ✰✰✰

#### 嵌入式系统的组成和特点

![嵌入式操作系统的特点](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7089o6hoe840.webp "嵌入式操作系统的特点")

![冯诺依曼结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.14ex5c4elzcw.webp "冯诺依曼结构")

![哈佛结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6c5e3h1a0eo0.webp "哈佛结构")

![嵌入式系统的组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3awqm214wv80.webp "嵌入式系统的组成")

![嵌入式系统的特性](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6ilkibhoz1o0.webp "嵌入式系统的特性")

![嵌入式系统的分层](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.67iw02a1tos0.webp "嵌入式系统的分层")

#### 嵌入式系统的分类

![微处理器分类1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4mgtxfa7vn60.webp "微处理器分类1")
![微处理器分类2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3oyxxpzllck0.webp "微处理器分类2")

![多核微处理器](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6tn60veft380.webp "多核微处理器")

![嵌入式操作系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.9kfz3dgkumo.webp "嵌入式操作系统")

![嵌入式实时操作系统的特点](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7grvl523q1g0.webp "嵌入式实时操作系统的特点")

![嵌入式实时操作系统的特征](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5359j8jrm400.webp "嵌入式实时操作系统的特征")

![嵌入式数据库使用环境特点](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1m3oqzzhakw0.webp "嵌入式数据库使用环境特点")

![嵌入式数据库组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4pj3zw951a00.webp "嵌入式数据库组成")

#### 嵌入式软件的组成和特点

![嵌入式软件分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4d1pytpan9y0.webp "嵌入式软件分类")

![板级支持包 BSP](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1cfioc8l9cm8.webp "板级支持包 BSP")

![BootLoader](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4bj678u5b3y0.webp "BootLoader")

![设备驱动程序](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.21y37ylcwwow.webp "设备驱动程序")

![交叉平台开发环境](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4bg0rqv7u3k0.webp "交叉平台开发环境")

![交叉编译与交叉调试](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.llahskv7sj4.webp "交叉编译与交叉调试")

![软件开发工具](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.790tw8sh1vo0.webp "软件开发工具")

### 计算机网络 ✰✰✰✰✰

#### 网络的基本概念

![计算机网络功能和分类1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5a13jyx69e00.webp "计算机网络功能和分类1")
![计算机网络功能和分类2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.pchdfi5sulc.webp "计算机网络功能和分类2")

#### 通信技术

![通信技术](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6oz6rblhgp80.webp "通信技术")

![绞线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7ijadk7wygs0.webp "绞线")

![网线安装标准](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1ut73626351c.webp "网线安装标准")

![光纤](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6pbshbhd3r40.webp "光纤")

![无线信道](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4su1zzn9wy60.webp "无线信道")

![通信方向](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5mkk0u56qf40.webp "通信方向")

![通信方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3m3y6cbwnsw0.webp "通信方式")

![交换方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.156hnydapam8.webp "交换方式")

#### 网络技术

![局域网和广域网协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.mmie4lvb0yo.webp "局域网和广域网协议")

![其他考点1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4b66at7qjso0.webp "其他考点1")

![其他考点2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3f1pr02zp7a0.webp "其他考点2")

#### 组网技术

![OSI 七层协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.gdf75l2zhbk.webp "OSI 七层协议")

![TCP/IP 协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.sqyzglyo3kw.webp "TCP/IP 协议")

![网络层协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.53373fvqn1s0.webp "网络层协议")

![传输层协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1emz9325c274.webp "传输层协议")

![应用层协议](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.688vsxjc7l40.webp "应用层协议")

![协议端口对照表](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.gh9fx41mf34.webp "协议端口对照表")

![交换机的功能](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2xuh3sxgs5i0.webp "交换机的功能")

![路由器的功能](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5y4rhk2fj8c0.webp "路由器的功能")

![IP 地址的表示](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5d9he7ynk9g0.webp "IP 地址的表示")

![IP 地址的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6b6twlatpok0.webp "IP 地址的分类")

![特殊 IP 地址](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1vg8jr7xi9k0.webp "特殊 IP 地址")

![子网划分](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1wk0lxljtm80.webp "子网划分")

![IPV6](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5v04cgmdqys0.webp "IPV6")

![网络规划三层模型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3ttf5hm4niq0.webp "网络规划三层模型")

![建筑物综合布线系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3vwco7coc5s0.webp "建筑物综合布线系统")

##### 相关公式

- 子网个数: 用划分了子网号后的网络号位数 - 原来的网络号位数，作为的 2 的幂，求 2 的幂次方
- 可使用的主机个数: 32 - 网络号位数，作为 2 的幂，求 2 的幂次方在减 2

##### 相关题型解题思路

- 考察OSI 七层协议: 主要考察各层的协议、功能、设备。
- 考察TCI/IP 协议: 主要考察功能
- 求子网个数: 通常给出两个 IP 地址，可以根据后面的网络号的位数减一下，代入公式计算。
- 求可用主机数: 只要算出来网络号的位数后，代入公式很容易计算。
- 求不属于网络的子网地址: 判断方式是看网络号是否相同，而网络号在左边，然后从 2 进制的角度来讲，数字越大越考左，所以大概率是最大的那个数。

### 计算机语言

![计算机语言概述](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2lbetdgjyyc0.webp "计算机语言概述")

![计算机语言的分类1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1xqngs521vnk.webp "计算机语言的分类1")
![计算机语言的分类2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1lgjqsw9t2bk.webp "计算机语言的分类2")

### 多媒体

![媒体的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.54wobnpoys00.webp "媒体的分类")

![多媒体的重要特征](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3qgpcfdagu00.webp "多媒体的重要特征")

![多媒体系统的基本组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7cg0bjgjhzk0.webp "多媒体系统的基本组成")

![多媒体系统的关键技术1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2o6lnyzumhe0.webp "多媒体系统的关键技术1")
![多媒体系统的关键技术2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3hlabp3qidw0.webp "多媒体系统的关键技术2")
![多媒体系统的关键技术3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.61lm67njx5k0.webp "多媒体系统的关键技术3")

### 系统工程 ✰

![系统工程方法1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1hspdvtdkskg.webp "系统工程方法1")
![系统工程方法2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.134qojvgz1i8.webp "系统工程方法2")
![系统工程方法3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3bmjbpf860s0.webp "系统工程方法3")
![系统工程方法4](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4j1y4yfu2lg0.webp "系统工程方法4")

![系统工程的生命周期1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1f5vu2w0w2f4.webp "系统工程的生命周期1")
![系统工程的生命周期2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.226r5l0ppwu8.webp "系统工程的生命周期2")

![基于模型的系统工程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4bw9naeriys0.webp "基于模型的系统工程")

### 系统性能 ✰

![性能指标1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.llhl0gkjkts.webp "性能指标1")
![性能指标2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2p55uuqhp000.webp "性能指标2")
![性能指标3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.og35ydk5ckg.webp "性能指标3")

![性能评测方法1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.78mcto4d1zk0.webp "性能评测方法1")
![性能评测方法2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6hwd2bqgbx00.webp "性能评测方法2")

![阿姆达尔解决方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.67ps4puigzk0.webp "阿姆达尔解决方法")

## 信息系统基础知识 ✰✰✰

### 信息系统概述

![信息系统的定义](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4kklg59med20.webp "信息系统的定义")

![信息系统的发展](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7dbm654l25s0.webp "信息系统的发展")

![信息系统的分类](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3s4kiwu2v9s0.webp "信息系统的分类")

![信息系统的应用](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6s1gtsljsc40.webp "信息系统的应用")

![信息系统的生命周期1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1g48xqs4xluo.webp "信息系统的生命周期1")
![信息系统的生命周期2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1mo2i4w2a22o.webp "信息系统的生命周期2")

![信息系统结构化开发方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3qdujr8fkiy0.webp "信息系统结构化开发方法")
![信息系统原型化开发方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6gmyyezvus00.webp "信息系统原型化开发方法")
![信息系统面向对象开发方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6c0dbeaxc280.webp "信息系统面向对象开发方法")
![信息系统面向服务开发方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1zein9luuwrk.webp "信息系统面向服务开发方法")

### 业务处理系统 TPS

![业务处理系统1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5sipr68g35k0.webp "业务处理系统1")
![业务处理系统2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.42wpqyu0y060.webp "业务处理系统2")

### 管理信息系统 MIS

![管理信息系统1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.naxh8wtm3bk.webp "管理信息系统1")
![管理信息系统2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6jjmz5kxjzs0.webp "管理信息系统2")

### 决策支持系统 DSS

![决策支持系统1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6mswpw1qj3k0.webp "决策支持系统1")
![决策支持系统2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.68dt1eeclyo0.webp "决策支持系统2")
![决策支持系统3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.po76xzn5aio.webp "决策支持系统3")

### 专家系统 ES

![专家系统1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.75v7b20dxqo0.webp "专家系统1")
![专家系统2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.ei2mczwr1kg.webp "专家系统2")

### 办公自动化系统 OAS

![办公自动化系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.xhlygqhii74.webp "办公自动化系统")

### 企业资源规划 ERP

![企业资源规划1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4vfsk3asuk60.webp "企业资源规划1")
![企业资源规划2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4ldn4wk4bcw0.webp "企业资源规划2")
![企业资源规划3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4irzuf0qkvu.webp "企业资源规划3")
![企业资源规划4](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.483zry7jf040.webp "企业资源规划4")

### 典型信息系统架构模型

![政府信息化和电子政务](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.lj81zy0fmxs.webp "政府信息化和电子政务")

![企业信息化和电子商务](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1c75djnv969s.webp "企业信息化和电子商务")

![企业信息化方法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5ozp341opm40.webp "企业信息化方法")

![电子商务](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3nbv442pjes0.webp "电子商务")

### 信息化战略体系

![信息化战略体系1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7hvk3pj7r700.webp "信息化战略体系1")
![信息化战略体系2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.24ixvktlaie8.webp "信息化战略体系2")

### 信息系统战略规划

![信息系统战略规划1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1dtmxhzp8qo0.webp "信息系统战略规划1")
![信息系统战略规划2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2ofrbn4h21i0.webp "信息系统战略规划2")

### 客户关系管理 CRM

![客户关系管理1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5r5s1br6fow0.webp "客户关系管理1")
![客户关系管理2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5emtai7vegk0.webp "客户关系管理2")
![客户关系管理3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.19m3mplfc5mo.webp "客户关系管理3")

### 供应链管理 SCM

![供应链管理1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6fko2do1l740.webp "供应链管理1")
![供应链管理2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6qj45flv1w80.webp "供应链管理2")

### 企业应用集成 EAI

![企业应用集成1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4uc0hwx74360.webp "企业应用集成1")
![企业应用集成2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4wkgir3vz020.webp "企业应用集成2")
![企业应用集成3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.15ddslyjryqk.webp "企业应用集成3")
![企业应用集成4](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6xcon5frfwk0.webp "企业应用集成4")
![企业应用集成5](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3mes3ddu48o0.webp "企业应用集成5")
![企业应用集成6](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.18k3di2prd5s.webp "企业应用集成6")

## 数据库设计基础知识 ✰✰✰✰✰

### 数据库基本概念

![数据库的基本特征](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.191f8qq6f1kw.webp "数据库的基本特征")

![数据库系统与数据库管理系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.37h9jxeop740.webp "数据库系统与数据库管理系统")

![三级模式两级映像](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.4xrvqgybsj80.webp "三级模式两级映像")

![数据模型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1t4qn0udkou8.webp "数据模型")

![E-R 模型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3zjeo8s5jem0.webp "E-R 模型")

![关系模型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5c5pc1fefds0.webp "关系模型")

![关系模型优缺点](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.1pvv2q4g0xk0.webp "关系模型优缺点")

![E-R 模型转关系模型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3ht5wfvcgt20.webp "E-R 模型转关系模型")

### 关系数据库

#### 相关概念

![关系代数并、交、差](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.r05gox34s1c.webp "关系代数并、交、差")

![关系代数笛卡尔积、投影、选择](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.53od7g3d1cg0.webp "关系代数笛卡尔积、投影、选择")

![关系代数自然连接](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2p08mdqw7u20.webp "关系代数自然连接")

![函数依赖规则](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6ekmpcoz8380.webp "函数依赖规则")

![函数依赖的公理系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.76imy2qc0wc0.webp "函数依赖的公理系统")

![键与约束](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.64h6x2fudc4.webp "键与约束")

![模式分解1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7j4ghkffvi40.webp "模式分解1")
![模式分解2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.682z4d6u4gg0.webp "模式分解2")
![模式分解3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.omahc7zk2uo.webp "模式分解3")

#### 相关题型解题思路

- 求元组个数和属性列数: 属性列很简单，自然连接求交集，笛卡尔积求并集，元组个数是，通过属性列相同且值相同连接后剩余的行数。
- 求等价的关系代数表达式：常见的就是给个自然连接的表达式，等价的是一个笛卡尔积的表达式，笛卡尔积转自然连接需要经过投影和选择。**还有能用数字代替列名，从1开始，注意不要加引号**。
- 求关系代数等价的SQL: 通常就是考察投影和选择，主要是行的问题，把属性列写一下很容易就能答出来。
- 求候选键: 根据依赖集找出从未在右边出现过的属性，其必然是候选键之一，然后以其为基础看看能不能遍历所有属性，将无法遍历的加入候选键中。
- 求模式分解后是否保持函数依赖: 先求分解后的模式分别的函数依赖，如果拆分后的属性，包含了原来的依赖关系中的所有属性，那么就能继承相应的依赖关系。然后如果剩余全部未被包含的依赖能通过函数依赖的公理系统得到，那么就能说保持了函数依赖。
- 求模式分解后是否无损连接: 分解后的模式先求交集，然后看交集的属性能不能推出，任意一个差集里的属性，如果可以那就算无损连接。

### 数据库设计

#### 相关概念

![数据库设计](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5dzoaaxpfaw0.webp "数据库设计")

![第一范式1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5qei5j4x6tw0.webp "第一范式1")
![第一范式2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2m933rm0do80.webp "第一范式2")

![第二范式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2sw5n9mldvo0.webp "第二范式")

![第三范式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6twirr83ghc0.webp "第三范式")

![BC范式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3yni6tbwn540.webp "BC范式")

![反规范化技术](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5kt1osw7mwg0.webp "反规范化技术")

#### 相关题型解题思路

- 求属于概念结构设计的什么冲突: 理解概念结构的冲突。
- 求关系模式达到了第几范式: 理解各种范式的限定条件。

### 规范发和并发

![并发控制1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2i75upllyj40.webp "并发控制1")
![并发控制2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.6g3ytt1vz1g0.webp "并发控制2")

![封锁协议1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.55ujp9qldz00.webp "封锁协议1")
![封锁协议2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3bsu6p7e8wo0.webp "封锁协议2")
![封锁协议3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.yy6tuoni09c.webp "封锁协议3")

#### 相关题型解题思路

- 求事务能否加锁成功: 很简单，排它(写)锁就是一个事务加了，其他事务什么锁也加不了。共享(读)锁就是一个事务加了，其他事务只能加共享(读)锁，不能加排它(写)锁。

### 数据库新技术

![数据库安全1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3cv1j4ljnny0.webp "数据库安全1")
![数据库安全2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.3tqyj91k41o0.webp "数据库安全2")

![分布式数据库](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5fjzuunsuas0.webp "分布式数据库")

![数据仓库技术1](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.5a5firz8ynw0.webp "数据仓库技术1")
![数据仓库技术2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7kpdbrrtbn40.webp "数据仓库技术2")
![数据仓库技术3](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.2cadqwnfv30g.webp "数据仓库技术3")

![大数据](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/Development/image.7b421s6py9c0.webp "大数据")
