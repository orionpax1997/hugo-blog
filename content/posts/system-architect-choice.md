---
title: "软考-系统架构师-选择"
date: 2024-04-02T19:29:53+08:00
draft: true
markmap:
  colorFreezeLevel: 2
  initialExpandLevel: 3
---

## 第 2 章 计算机系统基础知识

### 2.2 计算机硬件 0-1

#### [存储器](https://blog-draft.dramacat.top/system-architect-up/#存储器)

##### 相关公式

- 磁道记录的最大等待时间: 就是旋转一周的时间
- 磁道记录的最小等待时间: 就是 0
- 磁道按顺序排列的记录等待时间: 旋转一周的时间 - 处理时间
- 磁道记录的总处理时间: (旋转一块的时间 + 处理时间) \* 总块数 + 等待时间 \* (总块数 - 1)

##### 相关题型及解题思路

- **2022 求磁盘调度的响应序列**: 按照采用的调度算法，来求序列，多个相同柱面号的情况下，扇区号由小到大排列，磁头号是无效信息。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3o2jqasm51a0.webp)
- 求磁道记录的最长处理时间和最少处理时间: 通常给出逻辑记录的安排顺序表，磁盘的每周旋转速度，每个记录的处理时间，需要**注意还有个隐含的条件是磁盘的每块的旋转时间，且当前快数据旋转读取完后才能开始处理**，求出隐含条件后带入公式计算。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.21dt0hljwn28.webp)

#### [指令](https://blog-draft.dramacat.top/system-architect-up/#指令)

##### 相关公式

- 流水线周期: 指令分成不同执行段，其中执行时间最长的段为流水线周期
- 流水线执行时间 1: 1 条指令的总执行时间 + (总指令条数 - 1) \* 流水线周期
- 流水线执行时间 2: (1 条指令的总执行时间 - 流水线周期) + 总指令条数 \* 流水线周期
- 流水线的吞吐率: 吞吐率即为单位时间内执行的指令条数 = 指令条数 / 流水线执行时间
- 流水线的最大吞吐率: 1 / 流水线周期
- 流水线的加速比: 不使用流水线的执行时间 / 使用流水线的执行时间
- 流水线的最大加速比: 1 条指令不使用流水线的执行时间 / 流水线周期

##### 相关题型及解题思路

- 求流水线相关问题: 如果是让求吞吐率或加速比，通常情况下需要先求出执行时间，也就是说需要套两个公式;如果碰到和缓冲区结合考察的问题，**注意但单双缓冲区的差异，单缓冲区读入和写出不能同时进行，因此读入和写出的时间需要加在一起算做一段**。而双缓冲区的读入和写出可以同时进行，因此可以算做两段。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1cg0efv1irr4.webp)
- 求流水线最大加速比: 加上最大两个字，就是求极限值了，通常不会给出总指令条数，而需要设为 n 来计算，求极限时忽略常数，带入公式即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4piiqakpphk0.webp)

#### [校验码](https://blog-draft.dramacat.top/system-architect-up/#校验码)

##### 相关公式

- CRC 编码: 1. 在原始信息串后面补多项式的阶个零; 2. 求除数，多项式中幂指数存在的为 1，不存在为 0; 3. 求校验码，进行模 2 除(异或运算)，**余数如果不足多项式的阶的位数则在左边补 0**

##### 相关题型及解题思路

- 求 CRC 循环冗余校验码：通常给出原始信息串和生成多项式，让求校验码，套公式即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7hpcsdfp6is0.webp)

### 2.3 计算机软件

#### **操作系统 3-5**

##### [进程管理](https://blog-draft.dramacat.top/system-architect-up/#进程管理)

###### 相关公式

- 每个进程需要资源数不同时发生死锁的最大资源数: (进程 1 需要的资源数 - 1) + (进程 2 需要的资源数 - 1) + ... + (进程 n 需要的资源数 - 1)
- 每个进程需要资源数相同时发生死锁的最大资源数: 系统中的进程数 \* (单个进程需要的资源数 - 1)
- 不发生死锁的最小资源数: 发生死锁的最大资源数 + 1
- 互斥信号量初始值: 1
- 同步信号量的最大值: 资源数量
- 同步信号量的最小值: - (进程数量 - 资源数量)

###### 相关题型及解题思路

- 考察进程三态图之间的转换: 给定服务调度算法、给定几个进程的当前状态，某进程发生某事件后，求所有进程的后续状态。以三态图的转变带入后解题。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.15zmwdj8sv6k.webp)
- 考察前趋图，给定前趋图，求可标记为。从开始节点开始读，排除错误答案即可，很简单。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.527am2dbsxk0.webp)
- 考察进程资源图，求阻塞节点和化简顺序：求阻塞节点，某进程所请求的资源已经全部分配完毕，该进程为阻塞节点。求化简顺序，先找非阻塞节点，然后释放其占用资源(划掉连线)后，找后续的非阻塞节点，直到所有节点都不被阻塞。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3mg5pyejxi80.webp)
- **综合考察 PV 操作**: 给定前趋图，进程，和需要设置的信号量，然后给出进程部分执行过程中的 PV 操作，求空余的部分的 PV 操作。结合前趋图来看，从最开始无依赖的进程开始填空，进程执行完进行 V 操作，有几个后继则进行几次不同信号量的 V 操作。然后后面等待执行的进行的前驱如果都执行完了，则开始执行，有几个前驱进行几次不同信号量的 P 操作。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3cpj128qreq0.webp)
- 求信号量的取值范围: 给定进程数和资源数，求使用 PV 操作时需要设定的信号量的范围，带入公式计算，信号量为负几，则有几个等待进程。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4lw5jijli5y0.webp)
- 考察银行家算法，求当前可用的资源数和安全的执行序列: 给定资源及其可用资源总数，给定几个进程及其最大需求量和已分配资源数图示。**首先用资源的最大总数-当前所有进程分配的数量求出其当前可用的资源数**。然后找到所有执行序列中资源最大需求量都能满足的进程，作为可执行的进程，执行完后把这个进程上已分配的资源数加回，可用资源数，再找下一个可执行进程。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4qmw24kncpe0.webp)

##### [存储管理](https://blog-draft.dramacat.top/system-architect-up/#存储管理)

###### 相关公式

- 页内地址的位数: 每页大小以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 1: 内存大小 / 每页大小，然后求其以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 2: 逻辑地址或物理地址的位数 - 页内地址的位数
- 分页式存储物理地址: 高位通过页号在页表中查到物理块号 拼接 低位页内地址(偏移地址)，**逻辑地址和物理地址中低位的偏移地址不变，区别只是将高位的逻辑页号替换为了物理快号**

###### 相关题型及解题思路

- 求分页式存储的物理地址: 通常给出页面大小和逻辑地址，以及页号和物理块号的对应表，让求物理地址。首先通过页面大小算出页内地址的位数(**也可以直接看答案中，多数答案与逻辑地址后面几位重复，且前面剩余的在页表里能查到，则其为偏移地址位数，页面大小通常为 4k，则二进制表示为 4 位，16 进制表示为 1 位**)，剩余高位为页号，通过页号找到对应的物理块号，然后将逻辑地址高位替换为物理快号就是物理地址。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76lanl42ik00.webp)
- 求淘汰那个页面代价最小: 通常给出一个表格，标识每个页面的状态位、修改位、访问位，根据局部性原理，**优先淘汰最近未被访问过的，而后淘汰最近未被修改过的**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.ehvj7162biw.webp)
- 求段式存储中逻辑地址能否转换为物理地址(不违法)，给定几个(段号，段内偏移)，然后表格中给出段号和段长列，**根据段号找到段长，段内偏移大于段长就违法**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76ijeivzch40.webp)

#### [文件系统 0-1](https://blog-draft.dramacat.top/system-architect-up/#文件系统-0-1)

##### 相关公式

- 一级间接索引逻辑块的个数: 磁盘索引块大小 / 每个地址项的大小
- 二级间接索引逻辑块的个数: (磁盘索引块大小 / 每个地址项的大小) \* (磁盘索引块大小 / 每个地址项的大小)
- 一级间接索引物理块号的表示范围: 直接索引的最大编号 + 1 到 直接索引的最大编号 + 一级间接索引逻辑块的总个数
- 可表示的单个文件的最大长度: 可表示的总的逻辑块数 \* 磁盘数据块大小
- 表示位示图需要的字的个数: 磁盘容量 / 磁盘物理块大小 / 系统字长位数

##### 相关题型及解题思路

- 求逻辑快应采用什么索引: 通常给出一共几个地址项，以及其中几个直接索引，几个一级间接索引，几个二级间接索引，和每个地址项的大小，以及磁盘索引块和磁盘数据块的大小，然后问访问的逻辑块号应采用的是什么索引。题目中没明确说明时，**逻辑块从 0 开始编号**。首先将直接索引进行编号，然后带公式求一级间接索引的表示范围，以上就是二级间接索引的范围，这样就能判断采用的是什么索引。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4u0lba6pkj60.webp)
- 求采用什么索引和可表示的单个文件的最大长度: 算出总的表示范围(可表示的总的逻辑块数)(**如果答案没有相近的长度，只用算二级索引就行了**) 乘以磁盘数据块大小，代公式计算，就能算出可表示的单个文件最大的长度。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1v3qdf7n6hxc.webp)
- 求相对路径和绝对路径: 通常给出目录结构图，当前工作目录和需要访问的文件名，求相对路径和绝对路径，很简单。注意一点，路径最后的杠可以省略。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ghcdu97icsg.webp)
- 求需要表示的物理块在位示图中的第几个字描述: 通常需要表示的物理块号，和字长。**注意如果有余数，则向上取整，还有没有明确说明的情况下是从零开始编号的**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.27y0rbge5ha8.webp)
- 求位示图需要几个字来表示: 通常给出全部条件带入公式计算即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.73t259o9n6w0.webp)

#### [组网技术](https://blog-draft.dramacat.top/system-architect-up/#组网技术)

##### 相关公式

- 子网个数: 用划分了子网号后的网络号位数 - 原来的网络号位数，作为的 2 的幂，求 2 的幂次方
- 可使用的主机个数: 32 - 网络号位数，作为 2 的幂，求 2 的幂次方在减 2

##### 相关题型及解题思路

- **2022 考察常用端口号与协议的对应关系**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2r9nva54kkk.webp)
- **2022 考察 TCI/IP 协议: 主要考察功能**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.stflr0l4fs0.webp)
- 考察 OSI 七层协议: 主要考察各层的协议、功能、设备
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.496ao1hxl9k0.webp)
- 求子网个数及每个子网中可用主机数: 求子网个数，通常给出两个 IP 地址，可以根据后面的网络号的位数减一下，代入公式计算。求可用主机数，一样带公式计算即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.27ukozq4c6ck.webp)
- 求不属于网络的子网地址: 判断方式是看网络号是否相同，而网络号在左边，然后从 2 进制的角度来讲，数字越大越考左，所以**大概率是最大的那个数**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ek5l3w1dbo0.webp)

### [2.8 系统工程](https://blog-draft.dramacat.top/system-architect-up/#28-系统工程)

#### 相关题型及解题思路

- 考察系统工程方法: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3r1a6u4adh20.webp)

### [2.9 系统性能 1-2](https://blog-draft.dramacat.top/system-architect-up/#29-系统性能-1-2)

#### 相关题型及解题思路

- 考察性能指标: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6isgn12br4w0.webp)

## [第 4 章 信息安全技术基础知识 2-4](https://blog-draft.dramacat.top/system-architect-up/#第-4-章-信息安全技术基础知识-2-4)

### 相关题型及解题思路

- 考察信息安全的基本要素: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1naip4g829wg.png)
- 考察各种攻击的原理与抵御: 理解记忆
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6tl3l4sb0000.webp)
- 考察网络安全协议: 大概记一下协议的应用场景。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3doz4fiuj1c0.webp)
- 考察信息的加解密技术: 大概记一下涉及到的技术及其作用。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7ezz2q9rzkc0.webp)

## **第 5 章 软件工程基础知识 12-15**

### [5.1 软件工程](https://blog-draft.dramacat.top/system-architect-up/#51-软件工程)

#### 相关题型及解题思路

- **2022 考察软件过程模型的定义**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6j5r6albd1g0.webp)
- 考察软件过程模型的差异
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.uvh7zfiraw0.webp)
- 考察到了 CMMI 的哪一级的成熟度
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6awosvxf4x00.webp)
- 考察软件的生命周期
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.58lsrk295840.webp)
- 考察敏捷方法的特点
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.61gzkmq9c0o0.webp)
- 考察敏捷方法核心思想
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6bgktz48pk40.webp)
- 考察 RUP 九个核心工作流
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4focfgutqws0.webp)
- 考察 RUP 的特点
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.536xsnkniho0.webp)
- 考察软件系统用户文档、系统文档的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.558l8g4tlqg0.webp)
- 考察软件工程过程的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4uyyey7ntaq0.webp)
- 考察软件设计四个活动的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2s6y7c46spk0.webp)
- 考察逆向工程的四个级别的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5acwx5euoug0.webp)

### [5.2 需求工程](https://blog-draft.dramacat.top/system-architect-up/#52-需求工程)

#### 相关题型及解题思路

- 考察需求工程的两大过程(需求开发、需求管理)的主要活动
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7k65w0v62u8.webp)

### [5.3 系统分析与设计](https://blog-draft.dramacat.top/system-architect-up/#53-系统分析与设计)

#### 相关题型及解题思路

- 考察内聚程度分类、耦合程度分类
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2k2494q577c0.webp)

### [5.4 软件测试](https://blog-draft.dramacat.top/system-architect-up/#54-软件测试)

#### 相关公式

- 环形复杂度 1: 流图中边的条数 - 节点数 + 2
- 环形复杂度 2: 判定节点数 + 1

#### 相关题型及解题思路

- **2022 考察各个测试阶段的测试对象、测试依据、测试目的**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18h1ho3us3vk.webp)
- 考察白盒测试覆盖级别
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.14hhb8kn3xy8.webp)
- 求环形复杂度：看图带公式即可
- 考察静态测试、动态测试的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6p4st42yn000.webp)

### [5.6 基于构件的软件工程](https://blog-draft.dramacat.top/system-architect-up/#56-基于构件的软件工程)

#### 相关题型及解题思路

- **2022 考察构件的定义**

### [5.7 软件项目管理](https://blog-draft.dramacat.top/system-architect-up/#57-软件项目管理)

#### 相关公式

- 总浮动时间 1: 关键路径 - 活动路径
- 总浮动时间 2: 最迟开始 LS - 最早开始 ES
- 总浮动时间 3: 最迟完成 LF - 最早完成 EF
- 自由浮动时间: 紧后活动最早开始 LS 中的最小的 - 本活动的最早完成 EF

#### 相关题型及解题思路

- **2022 求最低成本完成项目需要多少天：注意间接费用，可能赶工成本更低**

### [系统转换和维护](https://blog-draft.dramacat.top/system-architect-up/#_系统转换和维护_)

#### 相关题型及解题思路

- **2022 考察遗留系统的演化策略**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5cbbdu2bv700.webp)

## **第 6 章 数据库设计基础知识 3-5**

### [6.2 关系数据库](https://blog-draft.dramacat.top/system-architect-up/#62-关系数据库)

#### 相关题型及解题思路

- **2022 考察函数依赖的公理系统**: 背下并理解四率两规则及其对应的数学代数表示。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3elkf4e09ho0.webp)
- **2022 求等价的关系代数表达式**：常见的就是给个自然连接的表达式，等价的是一个笛卡尔积的表达式，笛卡尔积转自然连接需要经过投影和选择。**还有能用数字代替列名，从 1 开始，如果表达式中看到带引号的数字可以直接排除**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ux3o3ymu920.webp)
- 求关系代数等价的 SQL: 通常就是考察投影和选择，主要是行的问题，把属性列写一下很容易就能答出来。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6vbmh2dgmgo0.webp)
- 求元组个数和属性列数: 属性列很简单，自然连接求交集，笛卡尔积求并集，元组个数是，通过属性列相同且值相同连接后剩余的行数。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1svhfsvafz5s.webp)
- 求候选键/属性闭包等式成立的代数表达式: 根据依赖集找出从未在右边出现过的属性，其必然是候选键之一，然后以其为基础看看能不能遍历所有属性，将无法遍历的加入候选键中。属性闭包表达式括号里所有属性，能求出依赖的所有属性就是闭包等式成立，通常就是全部候选键。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4pcplcadb140.webp)
- 求模式分解后是否保持函数依赖、是否无损连接: 是否保持函数依赖先求分解后的模式分别的函数依赖，如果拆分后的属性，包含了原来的依赖关系中的所有属性，那么就能继承相应的依赖关系。然后如果剩余全部未被包含的依赖能通过函数依赖的公理系统得到，那么就能说保持了函数依赖。是否保持无损连接分解后的模式先求交集，然后看交集的属性能不能推出，任意一个差集里的属性，如果可以那就算无损连接。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6g9hbzkcenw0.webp)

### [6.3 数据库设计](https://blog-draft.dramacat.top/system-architect-up/#63-数据库设计)

#### 相关题型及解题思路

- 求属于概念结构设计的什么冲突: 理解概念结构的冲突。**如果连着解决冲突的方式一起考，也可以根据解决方式倒推冲突类型**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1335yuslpl0g.webp)
- 求关系模式达到了第几范式: 理解各种范式的限定条件。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4mdz4t1ajta0.webp)

### [规范发和并发](https://blog-draft.dramacat.top/system-architect-up/#_规范发和并发_)

#### 相关题型及解题思路

- 求事务能否加锁成功: 很简单，排它(写)锁就是一个事务加了，其他事务什么锁也加不了。共享(读)锁就是一个事务加了，其他事务只能加共享(读)锁，不能加排它(写)锁。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7b4qv3t1rr00.webp)

## [第 7 章 系统架构设计的基础知识 15](https://blog-draft.dramacat.top/system-architect-up/#第-7-章-系统架构设计的基础知识-15)

### 相关题型及解题思路

- **2022 给定系统需求问应采用什么架构风格: 架构风格分类理解记忆**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.9q5ki5kspfc.webp "alt")
- **2022 考察软件架构复用类型的定义**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6114vjanjhg0.webp "alt")
- 考察软件架构复的阶段
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.sz8qpqmjehs.webp "alt")
- 考察 DSSA 的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4lrq13wysgo0.webp "alt")
- 考察 DSSA 三个基本活动：目的与活动的对应关系
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6grp3qdkwgg0.webp "alt")
- 考察分层架构风格: 理解记忆
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1syxi574bxuo.webp "alt")

## [第 8 章 系统质量属性与架构评估 10](https://blog-draft.dramacat.top/system-architect-up/#第-8-章-系统质量属性与架构评估-10)

### 相关题型及解题思路

- **2022 考察软件系统的质量属性**
- **2022 给定描述问是哪个面向架构的质量属性: 理解记忆**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1u1q487j2ncw.webp "alt")
- **2022 考察敏感点、权衡点、风险点的判断**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.400qjk8cu300.webp "alt")
- 考察质量属性场景的六个部分
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ywd7q8ejfs0.webp "alt")

