# 软考-系统架构师


# 上篇

## 第 2 章 计算机系统基础知识

### 2.2 计算机硬件 0-1

#### 计算机硬件组成

![计算机硬件组成](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.50u9cjryeck0.png "计算机硬件组成")

#### 处理器

##### CPU 的功能

![CPU 的功能](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5nujeeacm3o0.webp "CPU 的功能")

##### CPU 的组成

![CPU 的组成](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.fmceksfw06w.webp "CPU 的组成")

#### 存储器

##### 分级存储体系与局部性原理

![分级存储体系与局部性原理](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.33dkhwgef0o0.webp "分级存储体系与局部性原理")

##### Cache 相关概念

![Cache 相关概念](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5hxgdiahn3g.webp "Cache 相关概念")

##### Cache 映像方式

![Cache 映像方式1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ep6d4fesqk0.webp "Cache 映像方式1")
![Cache 映像方式2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.17iz0rps4rxc.webp "Cache 映像方式2")

##### Cache 替换算法

![Cache 替换算法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ow3qsbt8vm0.webp "Cache 替换算法")

##### Cache 命中率及读取平均时间

![Cache 命中率及读取平均时间](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.29nk73n2unb4.webp "Cache 命中率及读取平均时间")

##### 磁盘结构和参数

![磁盘结构和参数](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1oeoxoad1p4w.webp "磁盘结构和参数")

##### 磁盘调度算法

![磁盘调度算法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.15ryesazcin4.webp "磁盘调度算法")

##### 内存与接口地址的编址方法

![内存与接口地址的编址方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.b1pnqtuf1ug.webp "内存与接口地址的编址方法")

##### 相关公式

- 磁道记录的最大等待时间: 就是旋转一周的时间
- 磁道记录的最小等待时间: 就是 0
- 磁道按顺序排列的记录等待时间: 旋转一周的时间 - 处理时间
- 磁道记录的总处理时间: (旋转一块的时间 + 处理时间) \* 总块数 + 等待时间 \* (总块数 - 1)

##### 选择题相关题型及解题思路

- **2022 求磁盘调度的响应序列**: 按照采用的调度算法，来求序列，多个相同柱面号的情况下，扇区号由小到大排列，磁头号是无效信息。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3o2jqasm51a0.webp)
- 求磁道记录的最长处理时间和最少处理时间: 通常给出逻辑记录的安排顺序表，磁盘的每周旋转速度，每个记录的处理时间，需要**注意还有个隐含的条件是磁盘的每块的旋转时间，且当前快数据旋转读取完后才能开始处理**，求出隐含条件后带入公式计算。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.21dt0hljwn28.webp)

#### 总线

##### 总线的分类

![总线的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5kdhmitxwic0.webp "总线的分类")

#### 外部设备

##### 计算机和外设间的数据交互方式

![计算机和外设间的数据交互方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5zlfwjwdgg40.webp "计算机和外设间的数据交互方式")

#### 指令

##### 计算机指令的组成和执行过程

![计算机指令的组成和执行过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6qdek30lpc80.webp "计算机指令的组成和执行过程")

##### 计算机指令的寻址方式

![计算机指令的寻址方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.ou2ih4m6j5s.webp "计算机指令的寻址方式")

##### CISC 与 RISC

![CISC 与 RISC](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.733cz61t52g0.webp "CISC 与 RISC")

##### 指令流水线

![指令流水线](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5t6g10ok4v40.webp "指令流水线")

##### 相关公式

- 流水线周期: 指令分成不同执行段，其中执行时间最长的段为流水线周期
- 流水线执行时间 1: 1 条指令的总执行时间 + (总指令条数 - 1) \* 流水线周期
- 流水线执行时间 2: (1 条指令的总执行时间 - 流水线周期) + 总指令条数 \* 流水线周期
- 流水线的吞吐率: 吞吐率即为单位时间内执行的指令条数 = 指令条数 / 流水线执行时间
- 流水线的最大吞吐率: 1 / 流水线周期
- 流水线的加速比: 不使用流水线的执行时间 / 使用流水线的执行时间
- 流水线的最大加速比: 1 条指令不使用流水线的执行时间 / 流水线周期

##### 选择题相关题型及解题思路

- 求流水线相关问题: 如果是让求吞吐率或加速比，通常情况下需要先求出执行时间，也就是说需要套两个公式;如果碰到和缓冲区结合考察的问题，**注意但单双缓冲区的差异，单缓冲区读入和写出不能同时进行，因此读入和写出的时间需要加在一起算做一段**。而双缓冲区的读入和写出可以同时进行，因此可以算做两段。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1cg0efv1irr4.webp)
- 求流水线最大加速比: 加上最大两个字，就是求极限值了，通常不会给出总指令条数，而需要设为 n 来计算，求极限时忽略常数，带入公式即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4piiqakpphk0.webp)

#### 校验码

##### 奇偶校验码

![奇偶校验码](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1pgi3nxmcx4w.webp "奇偶校验码")

##### CRC 循环冗余校验码

![CRC 循环冗余校验码1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.24v5f4oszysg.webp "CRC 循环冗余校验码1")
![CRC 循环冗余校验码2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1elsprl1sue8.webp "CRC 循环冗余校验码2")

##### 相关公式

- CRC 编码: 1. 在原始信息串后面补多项式的阶个零; 2. 求除数，多项式中幂指数存在的为 1，不存在为 0; 3. 求校验码，进行模 2 除(异或运算)，**余数如果不足多项式的阶的位数则在左边补 0**

##### 选择题相关题型及解题思路

- 求 CRC 循环冗余校验码: 通常给出原始信息串和生成多项式，让求校验码，套公式即可。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7hpcsdfp6is0.webp)

### 2.3 计算机软件

#### **操作系统 3-5**

##### 操作系统

###### 操作系统的定义、作用、特征

![操作系统的定义、作用、特征](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4ta08p68eug0.webp "操作系统的定义、作用、特征")

###### 操作系统的功能

![操作系统的功能](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4ozf20qqg6g0.webp "操作系统的功能")

###### 操作系统的分类

![操作系统的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1hfphfzgmusg.webp "操作系统的分类")

##### 进程管理

###### 进程的组成和三态图

![进程的组成和三态图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1qa522vuo20w.webp "进程的组成和三态图")

###### 前趋图

![前趋图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4cxaged0yjq0.webp "前趋图")

###### 进程资源图

![进程资源图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.39n1vb9hou20.webp "进程资源图")

###### 同步互斥与信号量

![同步互斥与信号量](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.u47c4pdg4uo.webp "同步互斥与信号量")

###### PV 操作

![PV 操作](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6i8o5hlsafk0.webp "PV 操作")

###### 生产者消费者问题

![生产者消费者问题](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5hiw1kyeeug0.webp "生产者消费者问题")

###### 进程调度方式与三级调度

![进程调度方式与三级调度](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6c2qe0jxwls0.webp "进程调度方式与三级调度")

###### 进程调度算法

![进程调度算法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ty2cv623b60.webp "进程调度算法")

###### 死锁

![死锁](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2wqhyeh9wvq0.webp "死锁")

###### 线程

![线程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6lmden7uo1g0.webp "线程")

###### 相关公式

- 每个进程需要资源数不同时发生死锁的最大资源数: (进程 1 需要的资源数 - 1) + (进程 2 需要的资源数 - 1) + ... + (进程 n 需要的资源数 - 1)
- 每个进程需要资源数相同时发生死锁的最大资源数: 系统中的进程数 \* (单个进程需要的资源数 - 1)
- 不发生死锁的最小资源数: 发生死锁的最大资源数 + 1
- 互斥信号量初始值: 1
- 同步信号量的最大值: 资源数量
- 同步信号量的最小值: - (进程数量 - 资源数量)

###### 选择题相关题型及解题思路

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

##### 存储管理

###### 分区存储方式

![分区存储方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.qmuxffsi1n4.webp "分区存储方式")

###### 分区适应法

![分区适应法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.32xww0kvkcy0.webp "分区适应法")

###### 分页存储

![分页存储](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2scnsm54dvc0.webp "分页存储")

###### 页面置换算法

![页面置换算法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.727k1ckq7ms0.webp "页面置换算法")

###### 快表

![快表](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3iiym37nnks0.webp "快表")

###### 分段存储

![分段存储](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18syec51w934.webp "分段存储")

###### 段页式存储

![段页式存储](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4tqudwbw0om0.webp "段页式存储")

###### 相关公式

- 页内地址的位数: 每页大小以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 1: 内存大小 / 每页大小，然后求其以 2 的 n 次方表示时的 n
- 页号的 2 进制位数 2: 逻辑地址或物理地址的位数 - 页内地址的位数
- 分页式存储物理地址: 高位通过页号在页表中查到物理块号 拼接 低位页内地址(偏移地址)，**逻辑地址和物理地址中低位的偏移地址不变，区别只是将高位的逻辑页号替换为了物理快号**

###### 选择题相关题型及解题思路

- 求分页式存储的物理地址: 通常给出页面大小和逻辑地址，以及页号和物理块号的对应表，让求物理地址。首先通过页面大小算出页内地址的位数(**也可以直接看答案中，多数答案与逻辑地址后面几位重复，且前面剩余的在页表里能查到，则其为偏移地址位数，页面大小通常为 4k，则二进制表示为 4 位，16 进制表示为 1 位**)，剩余高位为页号，通过页号找到对应的物理块号，然后将逻辑地址高位替换为物理快号就是物理地址。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76lanl42ik00.webp)
- 求淘汰那个页面代价最小: 通常给出一个表格，标识每个页面的状态位、修改位、访问位，根据局部性原理，**优先淘汰最近未被访问过的，而后淘汰最近未被修改过的**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.ehvj7162biw.webp)
- 求段式存储中逻辑地址能否转换为物理地址(不违法)，给定几个(段号，段内偏移)，然后表格中给出段号和段长列，**根据段号找到段长，段内偏移大于段长就违法**。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76ijeivzch40.webp)

##### 设备管理

###### 设备管理概述

![设备管理概述](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1g5x73h6fyqo.webp "设备管理概述")

###### I/O 设备

![I/O 设备](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.34mylt9dmqw0.webp "I/O 设备")

###### 设备管理技术

![设备管理技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1maz233knxk0.webp "设备管理技术")

#### 文件系统 0-1

##### 文件管理概述

![文件管理概述](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7gs2ocqkw480.webp "文件管理概述")

##### 文件结构分类

![文件结构分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3xwfe8q9sgu0.webp "文件结构分类")

##### 索引文件结构

![索引文件结构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6hs13ibogkg0.webp "索引文件结构")

##### 文件目录

![文件目录](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.24huvvajhps0.webp "文件目录")

##### 文件存储空间管理

![文件存储空间管理1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5pr9lq294js0.webp "文件存储空间管理1")
![文件存储空间管理2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.67e5ut4ovnc0.webp "文件存储空间管理2")

##### 相关公式

- 一级间接索引逻辑块的个数: 磁盘索引块大小 / 每个地址项的大小
- 二级间接索引逻辑块的个数: (磁盘索引块大小 / 每个地址项的大小) \* (磁盘索引块大小 / 每个地址项的大小)
- 一级间接索引物理块号的表示范围: 直接索引的最大编号 + 1 到 直接索引的最大编号 + 一级间接索引逻辑块的总个数
- 可表示的单个文件的最大长度: 可表示的总的逻辑块数 \* 磁盘数据块大小
- 表示位示图需要的字的个数: 磁盘容量 / 磁盘物理块大小 / 系统字长位数

##### 选择题相关题型及解题思路

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

#### 中间件

##### 中间件的定义

![中间件的定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5dm6nuxci8k0.webp "中间件的定义")

##### 中间件的分类

![中间件的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6exx8nfljkk0.webp "中间件的分类")

### 2.4 嵌入式系统及软件 3-5 _超纲_

#### 嵌入式系统的组成和特点

##### 嵌入式操作系统的主要特点

![嵌入式操作系统的主要特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7089o6hoe840.webp "嵌入式操作系统的主要特点")

##### 冯诺依曼结构

![冯诺依曼结构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.14ex5c4elzcw.webp "冯诺依曼结构")

##### 哈佛结构

![哈佛结构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6c5e3h1a0eo0.webp "哈佛结构")

##### 嵌入式系统的组成

![嵌入式系统的组成](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3awqm214wv80.webp "嵌入式系统的组成")

##### 嵌入式系统的特性

![嵌入式系统的特性](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6ilkibhoz1o0.webp "嵌入式系统的特性")

##### 嵌入式系统的分层

![嵌入式系统的分层](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.67iw02a1tos0.webp "嵌入式系统的分层")

#### 嵌入式系统的分类

##### 嵌入式系统分类方式

![嵌入式系统分类方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4mgtxfa7vn60.webp "嵌入式系统分类方式")

##### 按用途划分的各种嵌入式系统的特点

![按用途划分的各种嵌入式系统的特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3oyxxpzllck0.webp "按用途划分的各种嵌入式系统的特点")

##### 多核微处理器

![多核微处理器](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6tn60veft380.webp "多核微处理器")

##### 嵌入式操作系统

![嵌入式操作系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.9kfz3dgkumo.webp "嵌入式操作系统")

##### 嵌入式实时操作系统的特点

![嵌入式实时操作系统的特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7grvl523q1g0.webp "嵌入式实时操作系统的特点")

##### 嵌入式实时操作系统的特征

![嵌入式实时操作系统的特征](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5359j8jrm400.webp "嵌入式实时操作系统的特征")

##### 嵌入式数据库使用环境特点

![嵌入式数据库使用环境特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1m3oqzzhakw0.webp "嵌入式数据库使用环境特点")

##### 嵌入式数据库组成

![嵌入式数据库组成](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4pj3zw951a00.webp "嵌入式数据库组成")

#### 嵌入式软件的组成和特点

##### 嵌入式软件分类

![嵌入式软件分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4d1pytpan9y0.webp "嵌入式软件分类")

##### 板级支持包 BSP

![板级支持包 BSP](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1cfioc8l9cm8.webp "板级支持包 BSP")

##### BootLoader

![BootLoader](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4bj678u5b3y0.webp "BootLoader")

##### 设备驱动程序

![设备驱动程序](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.21y37ylcwwow.webp "设备驱动程序")

##### 交叉平台开发环境

![交叉平台开发环境](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4bg0rqv7u3k0.webp "交叉平台开发环境")

##### 交叉编译与交叉调试

![交叉编译与交叉调试](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.llahskv7sj4.webp "交叉编译与交叉调试")

##### 软件开发工具

![软件开发工具](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.790tw8sh1vo0.webp "软件开发工具")

### 2.5 计算机网络 3-5 _超纲_

#### 网络的基本概念

##### 计算机网络功能和指标

![计算机网络功能和指标](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1khhtxg15gps.png "计算机网络功能和指标")

#### 通信技术

##### 通信技术基础概念

![通信技术基础概念](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6oz6rblhgp80.webp "通信技术基础概念")

#### 网络技术

##### 计算机网络按分布范围分类

![计算机网络按分布范围分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2qr257eyup00.webp "计算机网络按分布范围分类")

![计算机网络按拓扑结构分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.611mlkhzsvw0.webp "计算机网络按拓扑结构分类")

##### 通信方向

![通信方向](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5mkk0u56qf40.webp "通信方向")

##### 同步方式

![同步方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3m3y6cbwnsw0.webp "同步方式")

##### 交换方式

![交换方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.156hnydapam8.webp "交换方式")

#### 组网技术

##### OSI 七层协议

![OSI 七层协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.gdf75l2zhbk.webp "OSI 七层协议")

##### 局域网和广域网协议

![局域网和广域网协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.mmie4lvb0yo.webp "局域网和广域网协议")

##### TCP/IP 协议

![TCP/IP 协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.sqyzglyo3kw.webp "TCP/IP 协议")

##### 网络层协议

![网络层协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.53373fvqn1s0.webp "网络层协议")

##### 传输层协议

![传输层协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1emz9325c274.webp "传输层协议")

##### 应用层协议

![应用层协议](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.688vsxjc7l40.webp "应用层协议")

##### 协议端口对照表

![协议端口对照表](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.gh9fx41mf34.webp "协议端口对照表")

##### 交换机的功能

![交换机的功能](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2xuh3sxgs5i0.webp "交换机的功能")

##### 路由器的功能

![路由器的功能](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5y4rhk2fj8c0.webp "路由器的功能")

##### IP 地址的表示

![IP 地址的表示](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5d9he7ynk9g0.webp "IP 地址的表示")

##### IP 地址的分类

![IP 地址的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6b6twlatpok0.webp "IP 地址的分类")

##### 特殊 IP 地址

![特殊 IP 地址](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1vg8jr7xi9k0.webp "特殊 IP 地址")

##### 子网划分

![子网划分](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1wk0lxljtm80.webp "子网划分")

##### IPV6

![IPV6](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5v04cgmdqys0.webp "IPV6")

##### 相关公式

- 子网个数: 用划分了子网号后的网络号位数 - 原来的网络号位数，作为的 2 的幂，求 2 的幂次方
- 可使用的主机个数: 32 - 网络号位数，作为 2 的幂，求 2 的幂次方在减 2

##### 选择题相关题型及解题思路

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

#### 网路工程

##### 网络规划三层模型

![网络规划三层模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ttf5hm4niq0.webp "网络规划三层模型")

##### 建筑物综合布线系统

![建筑物综合布线系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3vwco7coc5s0.webp "建筑物综合布线系统")

#### 其他考点

##### 传输介质

###### 绞线的分类

![绞线的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7ijadk7wygs0.webp "绞线的分类")

###### 网线安装标准

![网线安装标准](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ut73626351c.webp "网线安装标准")

###### 光纤的分类

![光纤的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6pbshbhd3r40.webp "光纤的分类")

###### 无线信道

![无线信道](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4su1zzn9wy60.webp "无线信道")

##### 磁盘冗余阵列技术

![磁盘冗余阵列技术1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3t761ry4bgk0.webp "磁盘冗余阵列技术1")
![磁盘冗余阵列技术2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.60ydmembgxg0.webp "磁盘冗余阵列技术2")
![磁盘冗余阵列技术3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1cnolw5yuxr.webp "磁盘冗余阵列技术3")

##### 网络存储技术

![网络存储技术1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5mtt846n0pw0.webp "网络存储技术1")
![网络存储技术2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2y6ond2fhi20.webp "网络存储技术2")

##### 网络地址翻译

![网络地址翻译](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.61serb96b140.webp "网络地址翻译")

##### 默认网关

![默认网关](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6m3wd63vd8c0.webp "默认网关")

##### 虚拟局域网

![虚拟局域网](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2fi6bk7cov9c.webp "虚拟局域网")

##### 虚拟专用网

![虚拟专用网](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1thu34jmjke8.webp "虚拟专用网")

##### PPP 安全认证

![PPP安全认证](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1nzfiac45fxc.webp "PPP安全认证")

##### 冲突域与广播域

![冲突域与广播域](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ioes5ddbzy8.webp "冲突域与广播域")

### 2.6 计算机语言

#### 计算机语言概述

![计算机语言概述](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2lbetdgjyyc0.webp "计算机语言概述")

#### 计算机语言的分类

![计算机语言的分类1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1xqngs521vnk.webp "计算机语言的分类1")
![计算机语言的分类2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1lgjqsw9t2bk.webp "计算机语言的分类2")

### 2.7 多媒体

#### 媒体的分类

![媒体的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.54wobnpoys00.webp "媒体的分类")

#### 多媒体的重要特征

![多媒体的重要特征](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3qgpcfdagu00.webp "多媒体的重要特征")

#### 多媒体系统的基本组成

![多媒体系统的基本组成](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7cg0bjgjhzk0.webp "多媒体系统的基本组成")

#### 多媒体系统的关键技术

![多媒体系统的关键技术1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2o6lnyzumhe0.webp "多媒体系统的关键技术1")
![多媒体系统的关键技术2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3hlabp3qidw0.webp "多媒体系统的关键技术2")
![多媒体系统的关键技术3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.61lm67njx5k0.webp "多媒体系统的关键技术3")

### 2.8 系统工程

#### 系统工程方法

##### 霍尔的三维结构

![霍尔的三维结构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6kj6m6nybaw0.webp "霍尔的三维结构")

##### 切克兰德方法

![切克兰德方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.134qojvgz1i8.webp "切克兰德方法")

##### 并行工程方法

![并行工程方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3bmjbpf860s0.webp "并行工程方法")

##### 综合集成法

![综合集成法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3u8vo7nwi5e0.webp "综合集成法")

##### WSR 系统方法

![WSR 系统方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.14m3wvi6ltmo.webp "WSR 系统方法")

#### 系统工程生命周期

![系统工程的生命周期1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1f5vu2w0w2f4.webp "系统工程的生命周期1")
![系统工程的生命周期2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.226r5l0ppwu8.webp "系统工程的生命周期2")

#### 基于模型的系统工程

![基于模型的系统工程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4bw9naeriys0.webp "基于模型的系统工程")

#### 选择题相关题型及解题思路

- 考察系统工程方法: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3r1a6u4adh20.webp)

### 2.9 系统性能 1-2

#### 性能指标

![性能指标1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.llhl0gkjkts.webp "性能指标1")
![性能指标2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2p55uuqhp000.webp "性能指标2")
![性能指标3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.og35ydk5ckg.webp "性能指标3")

#### 性能评测方法

![性能评测方法1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.78mcto4d1zk0.webp "性能评测方法1")
![性能评测方法2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6hwd2bqgbx00.webp "性能评测方法2")

#### 阿姆达尔解决方法

![阿姆达尔解决方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.67ps4puigzk0.webp "阿姆达尔解决方法")

#### 选择题相关题型及解题思路

- 考察性能指标: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6isgn12br4w0.webp)

## 第 3 章 信息系统基础知识 3 _超纲_

### 3. 信息系统概述

#### 信息系统的基本功能和性质

![信息系统的基本功能和性质](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2fb6naqnp0ys.webp "信息系统的基本功能和性质")

#### 诺兰模型

![诺兰模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2k8wu69mj8o0.webp "诺兰模型")

#### 信息系统的分类

![信息系统的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3s4kiwu2v9s0.webp "信息系统的分类")

#### 企业主要使用的信息化系统

![企业主要使用的信息化系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6s1gtsljsc40.webp "企业主要使用的信息化系统")

#### 信息系统的生命周期

![信息系统的生命周期1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1g48xqs4xluo.webp "信息系统的生命周期1")
![信息系统的生命周期2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1mo2i4w2a22o.webp "信息系统的生命周期2")

#### 信息系统开发方法

##### 信息系统结构化开发方法

![信息系统结构化开发方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3qdujr8fkiy0.webp "信息系统结构化开发方法")

##### 信息系统原型化开发方法

![信息系统原型化开发方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6gmyyezvus00.webp "信息系统原型化开发方法")

##### 信息系统面向对象开发方法

![信息系统面向对象开发方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6c0dbeaxc280.webp "信息系统面向对象开发方法")

##### 信息系统面向服务开发方法

![信息系统面向服务开发方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1zein9luuwrk.webp "信息系统面向服务开发方法")

### 3.2 业务处理系统 TPS

![业务处理系统1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5sipr68g35k0.webp "业务处理系统1")
![业务处理系统2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.42wpqyu0y060.webp "业务处理系统2")

### 3.3 管理信息系统 MIS

![管理信息系统1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.naxh8wtm3bk.webp "管理信息系统1")
![管理信息系统2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6jjmz5kxjzs0.webp "管理信息系统2")

### 3.4 决策支持系统 DSS

![决策支持系统1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6mswpw1qj3k0.webp "决策支持系统1")
![决策支持系统2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.68dt1eeclyo0.webp "决策支持系统2")
![决策支持系统3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.po76xzn5aio.webp "决策支持系统3")

### 3.5 专家系统 ES

![专家系统1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.75v7b20dxqo0.webp "专家系统1")
![专家系统2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.ei2mczwr1kg.webp "专家系统2")

### 3.6 办公自动化系统 OAS

![办公自动化系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.xhlygqhii74.webp "办公自动化系统")

### 3.7 企业资源规划 ERP

![企业资源规划1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4vfsk3asuk60.webp "企业资源规划1")
![企业资源规划2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4ldn4wk4bcw0.webp "企业资源规划2")
![企业资源规划3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4irzuf0qkvu.webp "企业资源规划3")
![企业资源规划4](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.483zry7jf040.webp "企业资源规划4")

### 3.8 典型信息系统架构模型

#### 政府信息化和电子政务

![政府信息化和电子政务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.lj81zy0fmxs.webp "政府信息化和电子政务")

#### 企业信息化和电子商务

##### 企业信息化和电子商务基础概念

![企业信息化和电子商务基础概念](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1c75djnv969s.webp "企业信息化和电子商务基础概念")

##### 企业信息化方法

![企业信息化方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ozp341opm40.webp "企业信息化方法")

##### 电子商务

![电子商务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3nbv442pjes0.webp "电子商务")

##### 信息化战略体系

![信息化战略体系1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7hvk3pj7r700.webp "信息化战略体系1")
![信息化战略体系2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.24ixvktlaie8.webp "信息化战略体系2")

##### 信息系统战略规划

![信息系统战略规划1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1dtmxhzp8qo0.webp "信息系统战略规划1")
![信息系统战略规划2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ofrbn4h21i0.webp "信息系统战略规划2")

##### 客户关系管理 CRM

![客户关系管理1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5r5s1br6fow0.webp "客户关系管理1")
![客户关系管理2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5emtai7vegk0.webp "客户关系管理2")
![客户关系管理3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.19m3mplfc5mo.webp "客户关系管理3")

##### 供应链管理 SCM

![供应链管理1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6fko2do1l740.webp "供应链管理1")
![供应链管理2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6qj45flv1w80.webp "供应链管理2")

##### 企业应用集成 EAI

![企业应用集成1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4uc0hwx74360.webp "企业应用集成1")
![企业应用集成2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4wkgir3vz020.webp "企业应用集成2")
![企业应用集成3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.15ddslyjryqk.webp "企业应用集成3")
![企业应用集成4](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6xcon5frfwk0.webp "企业应用集成4")
![企业应用集成5](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3mes3ddu48o0.webp "企业应用集成5")
![企业应用集成6](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18k3di2prd5s.webp "企业应用集成6")

### 相关题型及解题思路

- 考到的话超纲内容比较多，定义理解记忆下即可

## **第 4 章 信息安全技术基础知识 2-4**

### 4.1 信息安全基础知识

#### 信息安全的基本要素

![信息安全的基本要素](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1cvo09vimpog.webp "信息安全的基本要素")

#### 信息安全的范围

![信息安全的范围](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.8vj5xgfxzv4.webp "信息安全的范围")

#### 信息的存储安全

![信息的存储安全](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3lzlxjg8fvg.webp "信息的存储安全")

#### 网络安全

![网络安全](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3t5e8t4d0uk0.webp "网络安全")

##### 防火墙

![防火墙](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4j8qq03flau0.webp "防火墙")

##### 入侵检测系统 IDS

![入侵检测系统 IDS](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2rppvn5hax60.webp "入侵检测系统 IDS")

##### 入侵防御系统 IPS

![入侵防御系统 IPS](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1490gryt6xts.webp "入侵防御系统 IPS")

##### 网络攻击和威胁

![网络攻击和威胁](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6nlgolnu2ig0.webp "网络攻击和威胁")

##### 网络安全协议

![网络安全协议1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3lbougkf18m0.webp "网络安全协议1")
![网络安全协议2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1jyvvphpugo0.webp "网络安全协议2")
![网络安全协议3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1xwk5cd7ug2o.webp "网络安全协议3")

### 4.3 信息安全系统的组成框架

#### 技术体系

![技术体系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.35945x7zm560.webp "技术体系")

### 4.4 信息加解密技术

#### 加密技术

![加密技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1zbnulg8w08w.webp "加密技术")

#### 对称加密技术

![对称加密技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.417o165qlzo0.webp "对称加密技术")

#### 非对称加密技术

![非对称加密技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3hsyt86rj680.webp "非对称加密技术")

#### 数字信封

![数字信封](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3e4xd38fjiw0.webp "数字信封")

#### 信息摘要

![信息摘要](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ugzjlyiaz7k.webp "信息摘要")

### 4.5 密钥管理技术

#### 公钥基础设施

![公钥基础设施](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4wphatvlzv20.webp "公钥基础设施")

### 4.6 访问控制及数字签名技术

#### 访问控制

![访问控制](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5f7oros0mbk0.webp "访问控制")

#### 数字签名

![数字签名](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.vqzix2q6w2o.webp "数字签名")

### 4.7 信息安全的抗攻击技术

#### 拒绝服务攻击

![拒绝服务攻击](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4syz8gicum80.webp "拒绝服务攻击")

#### 拒绝服务攻击的抵御

![拒绝服务攻击的抵御](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.53mzkx66ufc0.webp "拒绝服务攻击的抵御")

#### ARP 欺骗原理

![ARP 欺骗原理](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.47qeluysgic0.webp "ARP 欺骗原理")

#### ARP 欺骗的防范

![ARP 欺骗的防范](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7sp00fg2xdg0.webp "ARP 欺骗的防范")

#### DNS 欺骗

![DNS 欺骗](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4qm78t44iz20.webp "DNS 欺骗")

#### IP 欺骗

![IP 欺骗](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3sfzplhfqzo0.webp "IP 欺骗")

#### 端口扫描

![端口扫描](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1lct1nc5qjfk.webp "端口扫描")

### 4.8 信息安全的保障体系与评估方法

#### 计算机系统安全保护能力的等级

![计算机系统安全保护能力的等级](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.321blbsz1180.webp "计算机系统安全保护能力的等级")

#### 风险评估

![风险评估](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1z74skdaezwg.webp "风险评估")

### 选择题相关题型及解题思路

- 考察信息安全的基本要素: 背一下
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1naip4g829wg.png)
- 考察各种攻击的原理与抵御: 理解记忆
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6tl3l4sb0000.webp)
- 考察网络安全协议: 大概记一下协议的应用场景。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3doz4fiuj1c0.webp)
- 考察信息的加解密技术: 大概记一下涉及到的技术及其作用。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7ezz2q9rzkc0.webp)

## **第 5 章 软件工程基础知识 12-15**

### 5.1 软件工程

#### 软件工程定义

##### 软件工程：生命周期、文档、过程、工具、软件设计四个活动

![软件工程：生命周期、文档、过程、工具、软件设计四个活动](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3pn9h8ep2420.webp "软件工程：生命周期、文档、过程、工具、软件设计四个活动")

#### 软件过程模型

##### 瀑布模型

![瀑布模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4dadwg7fevs0.webp "瀑布模型")

##### 原型模型

![原型模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.23rgwkkevbxc.webp "原型模型")

##### 螺旋模型

![螺旋模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5nweqzehg6c0.webp "螺旋模型")

##### V 模型

![V 模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.15s1yek6z0qo.webp "V 模型")

##### 增量模型

![增量模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2o4xem5ga7q0.webp "增量模型")

##### 其他模型

![其他模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.u4avqx51640.webp "其他模型")

#### 敏捷模型

##### 敏捷模型：开发宣言、特点、核心思想

![敏捷模型：开发宣言、特点、核心思想](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.j0u0m7rhmg8.webp "敏捷模型：开发宣言、特点、核心思想")

##### 敏捷模型方法：极限编程、水晶系列方法、并列争球法、特性驱动开发方法

![敏捷模型方法：极限编程、水晶系列方法、并列争球法、特性驱动开发方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.43k8xlq80ew0.webp "敏捷模型方法：极限编程、水晶系列方法、并列争球法、特性驱动开发方法")

#### 统一过程模型 RUP

##### 统一过程模型九个核心工作流

![统一过程模型九个核心工作流](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1t6t2tqz3yjk.webp "统一过程模型九个核心工作流")

##### 统一过程模型：四个阶段、3W1H

![统一过程模型：四个阶段、3W1H](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5q2vvmuuvdc0.webp "统一过程模型：四个阶段、3W1H")

##### 统一过程模型特点

![统一过程模型特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.xey90hzodpc.webp "统一过程模型特点")

#### 软件能力成熟度模型

##### 能力成熟度模型 CMM

![能力成熟度模型 CMM](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.tjfekd51vpc.webp "能力成熟度模型 CMM")

##### 能力成熟度模型集成 CMMI

![能力成熟度模型集成 CMMI 1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.77vknxg4k6s0.webp "能力成熟度模型集成 CMMI 1")
![能力成熟度模型集成 CMMI 2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4vnh1mejsqo0.webp "能力成熟度模型集成 CMMI 2")

#### 其他考点

##### 软件复用与逆向工程的四个级别

![软件复用与逆向工程的四个级别](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5fpszt5m0e80.webp "软件复用与逆向工程的四个级别")

##### 重构、设计恢复、再工程、正向工程

![重构、设计恢复、再工程、正向工程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4thzd2beh8g0.webp "重构、设计恢复、再工程、正向工程")

#### 选择题相关题型及解题思路

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

### 5.2 需求工程

#### 需求工程定义

##### 软件需求：概念、两大过程

![软件需求：概念、两大过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4e3c1lln8h00.webp "软件需求：概念、两大过程")

##### 业务需求、用户需求、系统需求

![业务需求、用户需求、系统需求](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2x1bvftmfrk0.webp "业务需求、用户需求、系统需求")

#### 需求获取

##### 需求获取：定义、常见的需求获取法

![需求获取：定义、常见的需求获取法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.30jr9ue3tn80.webp "需求获取：定义、常见的需求获取法")

#### 需求变更

##### 需求基线

![需求基线](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.446ehphzjjc0.webp "需求基线")

##### 需求：变更原因、风险做法

![需求：变更原因、风险做法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3hgycw0gfuu0.webp "需求：变更原因、风险做法")

#### 需求追踪：双向跟踪、正向跟踪

![需求追踪：双向跟踪、正向跟踪](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2l3qbuiwq720.webp "需求追踪：双向跟踪、正向跟踪")

#### 其他考点

##### 需求分析：定义、任务

![需求分析：定义、任务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.709udxsog0c0.webp "需求分析：定义、任务")

##### 结构化的需求分析：特点、三大模型

![结构化的需求分析：特点、三大模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6gvjcfkkmco0.webp "结构化的需求分析：特点、三大模型")

##### 数据流图

###### 数据流图基本图形元素

![数据流图基本图形元素](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.46ln3lb4pke0.webp "数据流图基本图形元素")

###### 数据流、加工、数据存储、外部实体

![数据流、加工、数据存储、外部实体](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6euvcqdir5k0.webp "数据流、加工、数据存储、外部实体")

###### 分层数据流图

![分层数据流图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1yhtsyr6dj34.webp "分层数据流图")

##### 数据字典的作用

![数据字典的作用](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76z66jq6b2w.webp "数据字典的作用")

##### 需求定义：定义、方法

![需求定义：定义、方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18mjzqkxsq3k.webp "需求定义：定义、方法")

##### 需求验证

![需求验证](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5lmza1w3v2g0.webp "需求验证")

#### 选择题相关题型及解题思路

- 考察需求工程的两大过程(需求开发、需求管理)的主要活动
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7k65w0v62u8.webp)

#### 案例题相关题型及解题思路

- 给定系统的主要功能，看图填空补充数据流图：送分题，排除法做。

### 5.3 系统分析与设计

#### 系统设计：目的、方法、内容、基本任务

![系统设计：目的、方法、内容、基本任务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.39bc1t61x6w0.webp "系统设计：目的、方法、内容、基本任务")

#### 系统设计：基本原理、设计原则

![系统设计：基本原理、设计原则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5kw3kp8qd9k0.webp "系统设计：基本原理、设计原则")

#### 内聚程度分类

![内聚程度分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7fp6io58keo0.webp "内聚程度分类")

#### 耦合程度分类

![耦合程度分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.16wx0abix7gg.webp "耦合程度分类")

#### 人机界面设计三大原则

![人机界面设计三大原则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7g0wc6lk4nw0.webp "人机界面设计三大原则")

#### 选择题相关题型及解题思路

- 考察内聚程度分类、耦合程度分类
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2k2494q577c0.webp)

### 5.4 软件测试

#### 测试原则

![测试原则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.67j33abek980.webp "测试原则")

#### 静态测试和动态测试

![静态测试和动态测试](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2h3hc5h2q400.webp "静态测试和动态测试")

#### 测试阶段

##### 单元测试、集成测试、确认测试

![单元测试、集成测试、确认测试](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.h8559yneqvc.webp "单元测试、集成测试、确认测试")

##### 系统测试、配置项测试、回归测试

![系统测试、配置项测试、回归测试](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6qmd4jn8cpc0.webp "系统测试、配置项测试、回归测试")

#### 测试策略

![测试策略](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ut87t7xkck0.webp "测试策略")

#### 黑盒测试

![黑盒测试](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6e0qo9tku8w0.webp "黑盒测试")

#### 白盒测试覆盖级别

![白盒测试1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.698iziqra6k0.webp "白盒测试1")
![白盒测试2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.21tr95jrc2hs.webp "白盒测试2")
![白盒测试3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6ygd5q0dus80.webp "白盒测试3")

#### 调试：定义、方法

![调试：定义、方法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ndsstia3cg0.webp "调试：定义、方法")

#### 软件度量：两种属性、McCabe 度量法

![软件度量：两种属性、McCabe 度量法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6osscpx6tx80.webp "软件度量：两种属性、McCabe 度量法")

#### 相关公式

- 环形复杂度 1: 流图中边的条数 - 节点数 + 2
- 环形复杂度 2: 判定节点数 + 1

#### 选择题相关题型及解题思路

- **2022 考察各个测试阶段的测试对象、测试依据、测试目的**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18h1ho3us3vk.webp)
- 考察白盒测试覆盖级别
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.14hhb8kn3xy8.webp)
- 求环形复杂度：看图带公式即可
- 考察静态测试、动态测试的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6p4st42yn000.webp)

### 5.5 净室软件工程

#### 净室软件工程：定义、理论基础、应用技术手段、缺点

![净室软件工程：定义、理论基础、应用技术手段、缺点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2j9kadf30yw0.webp "净室软件工程：定义、理论基础、应用技术手段、缺点")

### 5.6 基于构件的软件工程

#### 构件的定义

![构件的定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1qmjow4ipc1s.webp "构件的定义")

#### 构件与对象的特性

![构件与对象的特性](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1fc6p3uyjugw.webp "构件与对象的特性")

#### 构件接口与面向构件编程

![构件接口与面向构件编程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.47w478ab28e0.webp "构件接口与面向构件编程")

#### 构件技术

![构件技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.31kkzrl1amq0.webp "构件技术")

#### 基于构件的软件工程的特征

![基于构件的软件工程的特征](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.dzk7tadoiiw.webp "基于构件的软件工程的特征")

#### 基于构件的软件工程：六个主要活动、与传统软件开发过程的不同点

![基于构件的软件工程：六个主要活动、与传统软件开发过程的不同点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4sp4rj7qhes0.webp "基于构件的软件工程：六个主要活动、与传统软件开发过程的不同点")

#### 构件组装：三种方式、三种不兼容问题

![构件组装：三种方式、三种不兼容问题](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.9l8bz9n84so.webp "构件组装：三种方式、三种不兼容问题")

#### 选择题相关题型及解题思路

- **2022 考察构件的定义**

### 5.7 软件项目管理

#### 软件进度管理

##### 进度管理：定义、过程

![进度管理：定义、过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.113s21atlkb4.webp "进度管理：定义、过程")

##### 进程安排的常用图形描述方法：甘特(Gantt)图、项目计划评审技术(PERT)图

![进程安排的常用图形描述方法：甘特(Gantt)图、项目计划评审技术(PERT)图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3d71zhga0de0.webp "进程安排的常用图形描述方法")

##### 关键路径

![关键路径](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1llrm3yu71kw.webp "关键路径")

##### 7 格图

![7 格图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7gqli8bm3t40.webp "7 格图")

#### 软件配置管理

##### 配置管理：定义、六个主要活动

![配置管理：定义、六个主要活动](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2qbsppph4ns0.webp "配置管理：定义、六个主要活动")

##### 配置项：定义、主要配置内容、典型配置项、主要属性、分类

![配置项：定义、主要配置内容、典型配置项、主要属性、分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3783w9wctqa0.webp "配置项：定义、主要配置内容、典型配置项、主要属性、分类")

##### 配置项状态

![配置项状态](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6inmy4llqpk0.webp "配置项状态")

##### 配置项版本

![配置项版本](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.60dp8gdf15s0.webp "配置项版本")

#### 软件质量管理

##### 质量管理：定义、过程

![质量管理：定义、过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3sl3rozcp2m.webp "质量管理：定义、过程")

#### 软件风险管理

##### 风险管理定义

![风险管理定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.40emcf9qpzm0.webp "风险管理定义")

##### 风险管理：项目风险、技术风险、商业风险

![风险管理：项目风险、技术风险、商业风险](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5im9nqm7ks0.webp "风险管理：项目风险、技术风险、商业风险")

#### 相关公式

- 总浮动时间 1: 关键路径 - 活动路径
- 总浮动时间 2: 最迟开始 LS - 最早开始 ES
- 总浮动时间 3: 最迟完成 LF - 最早完成 EF
- 自由浮动时间: 紧后活动最早开始 LS 中的最小的 - 本活动的最早完成 EF

#### 选择题相关题型及解题思路

- **2022 求最低成本完成项目需要多少天：注意间接费用，可能赶工成本更低**

### _处理流程设计_

#### 流程表示工具：程序流程图 PFD、IPO 图、N-S 图、问题分析图 PAD

![流程表示工具：程序流程图 PFD、IPO 图、N-S 图、问题分析图 PAD](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4xdb4ank63c0.webp "流程表示工具：程序流程图 PFD、IPO 图、N-S 图、问题分析图 PAD")

#### 业务流程重组 BPR：定义、设计原则、系统规划、步骤

![业务流程重组 BPR：定义、设计原则、系统规划、步骤](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.664dkgz52f40.webp "业务流程重组 BPR：定义、设计原则、系统规划、步骤")

#### 业务流程管理 BPM：定义、与 BPR 的区别、三个层面

![业务流程管理 BPM：定义、与 BPR 的区别、三个层面](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.41qo5s1kozq0.webp "业务流程管理 BPM：定义、与 BPR 的区别、三个层面")

### _系统转换和维护_

#### 遗留系统：特点、演化策略

![遗留系统：特点、演化策略](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6khpg007qy80.webp "遗留系统：特点、演化策略")

#### 系统转换三种计划、数据转换与迁移

![系统转换三种计划、数据转换与迁移](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.m2md1tgyddc.webp "系统转换三种计划、数据转换与迁移")

#### 可维护性评价指标、软件维护类型

![可维护性评价指标、软件维护类型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1monrsvm7v0g.webp "可维护性评价指标、软件维护类型")

#### 选择题相关题型及解题思路

- **2022 考察遗留系统的演化策略**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5cbbdu2bv700.webp)

## **第 6 章 数据库设计基础知识 3-5**

### 6.1 数据库基本概念

#### 数据库的基本特征

![数据库的基本特征](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.191f8qq6f1kw.webp "数据库的基本特征")

#### 数据库系统与数据库管理系统

![数据库系统与数据库管理系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.37h9jxeop740.webp "数据库系统与数据库管理系统")

#### 三级模式两级映像

![三级模式两级映像](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4xrvqgybsj80.webp "三级模式两级映像")

#### 数据模型分类与数据模型三要素

![数据模型分类与数据模型三要素](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1t4qn0udkou8.webp "数据模型分类与数据模型三要素")

#### E-R 模型

![E-R 模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3zjeo8s5jem0.webp "E-R 模型")

#### 关系模型的相关定义

![关系模型的相关定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5c5pc1fefds0.webp "关系模型的相关定义")

#### 关系模型优缺点

![关系模型优缺点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1pvv2q4g0xk0.webp "关系模型优缺点")

#### E-R 模型转关系模型

![E-R 模型转关系模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ht5wfvcgt20.webp "E-R 模型转关系模型")

### 6.2 关系数据库

#### 关系代数并、交、差

![关系代数并、交、差](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.r05gox34s1c.webp "关系代数并、交、差")

#### 关系代数笛卡尔积、投影、选择

![关系代数笛卡尔积、投影、选择](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.53od7g3d1cg0.webp "关系代数笛卡尔积、投影、选择")

#### 关系代数自然连接

![关系代数自然连接](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2p08mdqw7u20.webp "关系代数自然连接")

#### 函数依赖规则

![函数依赖规则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6ekmpcoz8380.webp "函数依赖规则")

#### 函数依赖的公理系统

![函数依赖的公理系统](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76imy2qc0wc0.webp "函数依赖的公理系统")

#### 键与约束

![键与约束](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.64h6x2fudc4.webp "键与约束")

#### 模式分解

![模式分解1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7j4ghkffvi40.webp "模式分解1")
![模式分解2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.682z4d6u4gg0.webp "模式分解2")
![模式分解3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.omahc7zk2uo.webp "模式分解3")

#### 选择题相关题型及解题思路

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

#### 案例题相关题型及解题思路

- 给定系统主要功能描述，看图填空补充 E-R 图：送分题，排除法做。

### 6.3 数据库设计

#### 数据库设计

![数据库设计阶段](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5dzoaaxpfaw0.webp "数据库设计阶段")

#### 第一范式

![第一范式1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5qei5j4x6tw0.webp "第一范式1")
![第一范式2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2m933rm0do80.webp "第一范式2")

#### 第二范式

![第二范式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2sw5n9mldvo0.webp "第二范式")

#### 第三范式

![第三范式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6twirr83ghc0.webp "第三范式")

#### BC 范式

![BC范式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3yni6tbwn540.webp "BC范式")

#### 反规范化技术

![反规范化技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5kt1osw7mwg0.webp "反规范化技术")

#### 选择题相关题型及解题思路

- 求属于概念结构设计的什么冲突: 理解概念结构的冲突。**如果连着解决冲突的方式一起考，也可以根据解决方式倒推冲突类型**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1335yuslpl0g.webp)
- 求关系模式达到了第几范式: 理解各种范式的限定条件。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4mdz4t1ajta0.webp)

#### 案例题相关题型及解题思路

- 考察反规范化技术定义和选用

### _规范发和并发_

#### 并发控制

![并发控制1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2i75upllyj40.webp "并发控制1")
![并发控制2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6g3ytt1vz1g0.webp "并发控制2")

#### 封锁协议

![封锁协议1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.55ujp9qldz00.webp "封锁协议1")
![封锁协议2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3bsu6p7e8wo0.webp "封锁协议2")
![封锁协议3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.yy6tuoni09c.webp "封锁协议3")

#### 选择题相关题型及解题思路

- 求事务能否加锁成功: 很简单，排它(写)锁就是一个事务加了，其他事务什么锁也加不了。共享(读)锁就是一个事务加了，其他事务只能加共享(读)锁，不能加排它(写)锁。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7b4qv3t1rr00.webp)

### _数据库新技术_

#### 数据库安全

![数据库安全](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3cv1j4ljnny0.webp "数据库安全")

#### 数据库备份

![数据库备份](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3tqyj91k41o0.webp "数据库备份")

#### 分布式数据库

![分布式数据库](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5fjzuunsuas0.webp "分布式数据库")

#### 数据仓库技术

![数据仓库技术1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5a5firz8ynw0.webp "数据仓库技术1")
![数据仓库技术2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7kpdbrrtbn40.webp "数据仓库技术2")
![数据仓库技术3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2cadqwnfv30g.webp "数据仓库技术3")

#### 大数据

![大数据](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7b421s6py9c0.webp "大数据")

## **第 7 章 系统架构设计的基础知识 15**

### 7.1 软件架构概念

#### 软件架构定义

![软件架构定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.33ejy13bq8u0.webp "软件架构定义")
![软件架构定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.45cn657azgs0.webp "软件架构定义")

#### 软件架构设计的生命周期

![软件架构设计的生命周期1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6brsxetodww0.webp "软件架构设计的生命周期1")
![软件架构设计的生命周期2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3p8ov2qwe060.webp "软件架构设计的生命周期2")

### 7.2 基于架构的软件开发方法

#### ABSD：定义、三个基础

![ABSD：定义、三个基础](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7c90nb3oyuo0.webp "ABSD：定义、三个基础")

#### 基于架构的软件开发过程

![基于架构的软件开发过程1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2nmijp2nsfu0.webp "基于架构的软件开发过程1")
![基于架构的软件开发过程2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5irvz3bbtio0.webp "基于架构的软件开发过程2")
![基于架构的软件开发过程3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4fzrm4jp9wy0.webp "基于架构的软件开发过程3")

### 7.3 **软件架构风格**

#### 软件架构风格定义

![软件架构风格定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.65ygvxr8g2c0.webp "软件架构风格定义")

#### 软件架构风格的分类

![软件架构风格的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4k839sfcmmq0.webp "软件架构风格的分类")

#### 软件架构风格：常考关键字及实例、简介

![软件架构风格：常考关键字及实例、简介](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ruao32fwks0.webp "软件架构风格：常考关键字及实例、简介")

#### 软件架构风格：主要特点、优缺点、适合领域对比

![软件架构风格：主要特点、优缺点、适合领域对比](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4lzein1n1j40.webp "软件架构风格：主要特点、优缺点、适合领域对比")

#### 数据流风格

![数据流风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1r4kdemcihkw.webp "数据流风格")

#### 调用返回风格

![调用返回风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3xcc9yzy0j40.webp "调用返回风格")

#### 独立构件风格

![独立构件风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7ecmzadwv380.webp "独立构件风格")

#### 虚拟机风格

![虚拟机风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ok68cn1v9i0.webp "虚拟机风格")

#### 仓库（数据共享）风格

![仓库（数据共享）风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3cpj11ftdmg0.webp "仓库（数据共享）风格")

#### 闭环控制风格

![闭环控制风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.45e7vwag3ay0.webp "闭环控制风格")

#### C2 架构风格

![C2架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.dkoytlnsxyo.webp "C2架构风格")

### 7.4 软件架构复用

#### 软件架构复用：定义、类型、可复用的资产包括、过程

![软件架构复用：定义、类型、可复用的资产包括、过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4do65se1qjc0.webp "软件架构复用：定义、类型、可复用的资产包括、过程")

### 7.5 特定领域软件体系结构

#### DSSA 的定义

![DSSA 的定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5lno3cgwhsg0.webp "DSSA 的定义")

#### DSSA 的三个基本活动

![DSSA 的三个基本活动](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1a3bydlyrahs.webp "DSSA 的三个基本活动")

#### DSSA 的四种角色人员

![DSSA 的四种角色人员](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.xbstjlaiyww.webp "DSSA 的四种角色人员")

#### 建立 DSSA 的过程

![建立 DSSA 的过程](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ef04rcct0hs.webp "建立 DSSA 的过程")

#### 三层次模型

![三层次模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2r7sqrswz1k0.webp "三层次模型")

### _层次架构风格_

#### 两层 C/S 架构风格

![两层C/S架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5hvzhnuqjh00.webp "两层C/S架构风格")

#### 三层 C/S 架构风格

![三层C/S架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3pd4dhzuari0.webp "三层C/S架构风格")

#### 三层 B/S 架构风格

![三层B/S架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6fx9senl5m00.webp "三层B/S架构风格")

#### 富互联网应用 RIA

![富互联网应用RIA](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6wv98brnmi80.webp "富互联网应用RIA")

#### MVC 架构风格

![MVC架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3fi5psmi0fy0.webp "MVC架构风格")

#### MVP 架构风格

![MVP架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.42m6gsq4rzq0.webp "MVP架构风格")

#### MVVM 架构风格

![MVVM架构风格](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6gqwqtkdr240.webp "MVVM架构风格")

### 选择题相关题型及解题思路

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

### 案例题相关题型及解题思路

- 给定两种架构风格和需要对比的方面，问为何采用其中一个。给定系统的核心需求，问应该采用什么风格：理解记忆各个软件架构风格和其对比情况。
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ea5u73tha1w.webp "alt")
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5cax7er7h5o0.webp "alt")

## **第 8 章 系统质量属性与架构评估 10**

### **8.1 软件系统质量属性**

#### 软件系统质量属性：开发时期、运行时期

![软件系统质量属性：开发时期、运行时期](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2s4vrihswus0.webp "软件系统质量属性：开发时期、运行时期")

#### 面向架构评估的质量属性：性能、可靠性、可用性、安全性

![面向架构评估的质量属性：性能、可靠性、可用性、安全性](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6fm58jtwnxw0.webp "面向架构评估的质量属性：性能、可靠性、可用性、安全性")

#### 面向架构评估的质量属性：可修改性、功能性、可变性、互操作性

![面向架构评估的质量属性：可修改性、功能性、可变性、互操作性](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5w8fgp83oxc0.webp "面向架构评估的质量属性：可修改性、功能性、可变性、互操作性")

#### 质量属性场景的六个部分

![质量属性场景的六个部分](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3wn1adb2xm80.webp "质量属性场景的六个部分")

### 8.2 系统架构评估

#### 软件架构评估：敏感点、权衡点、风险点

![软件架构评估：敏感点、权衡点、风险点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.47qlp3y6js40.webp "软件架构评估：敏感点、权衡点、风险点")

#### 三种常用的评估方式：调查问卷、度量、场景

![三种常用的评估方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3w5ibwlheio0.webp "三种常用的评估方式")

#### 基于场景的架构分析方法 SAAM

![基于场景的架构分析方法 SAAM](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4o2fkxbye5y0.webp "基于场景的架构分析方法 SAAM")

#### 架构权衡分析法 ATAM

![架构权衡分析法 ATAM](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.pfc64ta4eww.webp "架构权衡分析法 ATAM")

#### 成本效益分析法 CBAM

![成本效益分析法 CBAM](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.p256hb858xc.webp "成本效益分析法 CBAM")

#### 其他评估方法：SAEM、SAABNet、SACMM、ALRRA、AHP、COSMIC+UML

![其他评估方法1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7ii3ua4j7d00.webp "其他评估方法1")
![其他评估方法2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.58s3mj1wez80.webp "其他评估方法2")

### 必背概念

#### 软件架构风格、架构风险、风险点与非风险点、敏感点、权衡点

![软件架构风格、架构风险、风险点与非风险点、敏感点、权衡点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.681zocif0p40.webp "软件架构风格、架构风险、风险点与非风险点、敏感点、权衡点")

### 选择题相关题型及解题思路

- **2022 考察软件系统的质量属性**
- **2022 给定描述问是哪个面向架构的质量属性: 理解记忆**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1u1q487j2ncw.webp "alt")
- **2022 考察敏感点、权衡点、风险点的判断**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.400qjk8cu300.webp "alt")
- 考察质量属性场景的六个部分
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3ywd7q8ejfs0.webp "alt")

### 案例题相关题型及解题思路

- 给定关键质量属性场景，看图填空补充质量效用树：送分题，排除法做。
- 给定专家评估意见，让判断风险点、敏感点、权衡点：送分题，排除法做。

## 第 9 章 软件可靠性基础知识 2

### 9.1 软件可靠性基本概念

#### 软件可靠性的基本概念：定义、与硬件可靠性的区别、定量描述

![软件可靠性的基本概念：定义、与硬件可靠性的区别、定量描述](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.mpuwvlrz8j4.webp "软件可靠性的基本概念：定义、与硬件可靠性的区别、定量描述")

#### 串联系统与并联系统的可靠性

![串联系统与并联系统的可靠性](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.678jt43ccgw0.webp "串联系统与并联系统的可靠性")

#### 软件可靠性的测试的意义

![软件可靠性的测试的意义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.68ys280et5s0.webp "软件可靠性的测试的意义")

### 9.2 软件可靠性建模

#### 软件可靠性建模：定义、影响可靠性的因素、可靠性模型的组成、可靠性模型的三个假设

![软件可靠性建模：定义、影响可靠性的因素、可靠性模型的组成、可靠性模型的三个假设](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6fatlh4pd8c0.webp "软件可靠性建模：定义、影响可靠性的因素、可靠性模型的组成、可靠性模型的三个假设")

#### 软件可靠性模型分类

![软件可靠性模型分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6qanb26k5740.webp "软件可靠性模型分类")

### 9.3 软件可靠性管理

#### 软件可靠性管理：定义、内容包括、各阶段涉及任务

![软件可靠性管理：定义、内容包括、各阶段涉及任务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1x4zmr8nkqps.webp "软件可靠性管理：定义、内容包括、各阶段涉及任务")

### 9.4 软件可靠性设计

#### 软件可靠性设计：定义、原则、主要技术

![软件可靠性设计：定义、原则、主要技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4onelptveei0.webp "软件可靠性设计：定义、原则、主要技术")

#### 软件容错技术

![软件容错技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2sxfq83y00s0.webp "软件容错技术")

#### N 版本程序设计

![N 版本程序设计](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3vn3gygnipg0.webp "N 版本程序设计")

#### 恢复块设计

![恢复块设计](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.52gg9pooihc0.webp "恢复块设计")

#### N 版本与恢复块二者比较

![N 版本与恢复块二者比较](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5g0jd9b92ag0.webp "N 版本与恢复块二者比较")

#### 防卫式程序设计

![防卫式程序设计](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.36gcaghwx5k0.webp "防卫式程序设计")

#### 双机容错技术

![双机容错技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4yj5de38u0o.webp "双机容错技术")

#### 集群技术

![集群技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4sxp5kg861w0.webp "集群技术")

#### 负载均衡

![负载均衡](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6jfp6t8mto00.webp "负载均衡")

### 9.5 软件可靠性测试

#### 软件可靠性测试：定义、步骤

![软件可靠性测试：定义、步骤](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1wcmr9i7908w.webp "软件可靠性测试：定义、步骤")

### 9.6 软件可靠性评价

#### 软件可靠性评价：过程、考虑因素、数据收集、评估预测

![软件可靠性评价：过程、考虑因素、数据收集、评估预测](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.8x7fbhuma48.webp "软件可靠性评价：过程、考虑因素、数据收集、评估预测")

## 第 10 章 软件架构的演化和维护 2

### 10.1 软件架构演化和定义的的关系

![软件架构演化和定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6ono1266iqk0.webp "软件架构演化和定义")

### 10.2 面向对象软件架构演化过程

#### 对象演化、消息演化

![对象演化、消息演化](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7281rflwi8w0.webp "对象演化、消息演化")

#### 复合片段演化、约束演化

![复合片段演化、约束演化](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.74621oils8c0.webp "复合片段演化、约束演化")

### 10.3 软件架构演化方式的分类

![软件架构演化方式的分类1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3li6sphxjhk0.webp "软件架构演化方式的分类1")
![软件架构演化方式的分类2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.56zsxmh0m240.webp "软件架构演化方式的分类2")
![软件架构演化方式的分类3](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5hcoq8au8gk0.webp "软件架构演化方式的分类3")
![软件架构演化方式的分类4](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5dxlujkqpac0.webp "软件架构演化方式的分类4")

### 10.4 软件架构演化原则

![软件架构演化原则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ati8q0iw4e8.webp "软件架构演化原则")

### 10.5 软件架构演化评估方法

![软件架构演化评估方法1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.23hfcg3usyqo.webp "软件架构演化评估方法1")
![软件架构演化评估方法2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5zlu311am6c0.webp "软件架构演化评估方法2")

### 10.6 大型网站系统架构演化实例

![大型网站架构演化1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5c4isrhvyjk0.webp "大型网站架构演化1")
![大型网站架构演化2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.62lr2vizusw0.webp "大型网站架构演化2")

### 10.7 软件架构维护

![软件架构维护](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.185wxsbvi03g.webp "软件架构维护")

## 第 11 章 未来信息综合技术 2-3 _超纲_

### 11.1 信息物理系统技术概述

#### CPS：定义、体系架构

![CPS：定义、体系架构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6gq4dy62wno0.webp "CPS：定义、体系架构")

#### CPS 技术体系

![CPS 技术体系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2n980fq0kxy0.webp "CPS 技术体系")

#### CPS 应用场景

![CPS 应用场景](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2126qkdjimg0.webp "CPS 应用场景")

### 11.2 人工智能技术概述

#### 人工智能：定义、关键技术

![人工智能：定义、关键技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.152nf82n2psw.webp "人工智能：定义、关键技术")

#### 人工智能学习模式分类

![人工智能学习模式分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.37hyd8cn3pw0.webp "人工智能学习模式分类")

#### 人工智能：学习方法分类、常见算法

![人工智能：学习方法分类、常见算法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.vra5s2ya14g.webp "人工智能：学习方法分类、常见算法")

### 11.3 机器人技术概述

#### 机器人：定义、核心技术

![机器人：定义、核心技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.219rohhquuao.webp "机器人：定义、核心技术")

#### 机器人分类

![机器人分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1ykdyu7r48ps.webp "机器人分类")

### 11.4 边缘计算概述

#### 边缘计算：定义、业务

![边缘计算：定义、业务](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2zlhptkkz4q0.webp "边缘计算：定义、业务")

#### 边缘计算特点

![边缘计算特点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.ma7azror3k0.webp "边缘计算特点")

#### 边缘计算协同

![边缘计算协同](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.18i80yhbya8w.webp "边缘计算协同")

### 11.5 数字孪生体技术概述

![数字孪生体：定义、关键技术](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1etkqy1lvlnk.webp "数字孪生体：定义、关键技术")

### 11.6 云计算和大数据技术概述

#### 云计算：内涵、服务方式

![云计算：内涵、服务方式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5k35fkykokw0.webp "云计算：内涵、服务方式")

#### 云计算的部署模式

![云计算的部署模式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4t4otu10hp20.webp "云计算的部署模式")

#### 大数据：定义、特点、分析步骤、应用领域

![大数据：定义、特点、分析步骤、应用领域](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.um80oj0uee8.webp "大数据：定义、特点、分析步骤、应用领域")

# 下篇

## 第 15 章 面向服务的架构设计与理论实践

### 15.1 SOA 的相关概念

#### **SOA：定义、优点**

![SOA：定义、优点](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ginldmlou40.webp "SOA：定义、优点")

#### SOA：关键目标、特征、基于服务的构件与传统构件的区别

![SOA：关键目标、特征、基于服务的构件与传统构件的区别](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1slxcr3tvb1.webp "SOA：关键目标、特征、基于服务的构件与传统构件的区别")

### 15.4 SOA 主要协议和规范

#### UDDI、WSDL、SOAP、XML、REST 等

![UDDI、WSDL、SOAP、XML、REST 等](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1uyzz8b9fy2.webp "UDDI、WSDL、SOAP、XML、REST 等")

### 15.8 SOA 的设计模式

#### 服务注册表模式

![服务注册表模式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.522v3mf7en00.webp "服务注册表模式")

#### **企业服务总线模式 ESB**

![企业服务总线模式1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6zio1sbc48g0.webp "企业服务总线模式1")
![企业服务总线模式2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4jcoig20une0.webp "企业服务总线模式2")

### 选择题相关题型及解题思路

- 考察 SOA 主要协议和规范：背一下

# 拓展

## 案例分析

### 案例分析历年考点分析

![案例分析历年考点分析](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2h10pysjksu0.png "案例分析历年考点分析")

### 案例分析解题技巧

![案例分析解题技巧](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.67gmh3mvlg00.png "案例分析解题技巧")

## 论文

### 摘要

- 时间
- 客户
- 项目
- 角色
- 负责
- 功能
- 效果
- 金额
- 历时
- 表扬
- 论述
- 包括

### 正文

- 背景
- 简介 部分复制摘要 + 技术介绍

## Java 语言相关

### J2EE

#### J2EE 四层结构

![J2EE 四层结构1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7cbdpyyw8qo0.webp "J2EE 四层结构1")
![J2EE 四层结构2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.93ltyr6jcqg.webp "J2EE 四层结构2")

#### J2EE 与 MVC 的对应

![J2EE 与 MVC 的对应](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.35w22yxz48q0.webp "J2EE 与 MVC 的对应")

### EJB

#### EJB 定义

![EJB 定义](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4j3thlri1i80.webp "EJB 定义")

#### EJB 的三种 Bean

![EJB 的三种 Bean](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1fchbz63msps.webp "EJB 的三种 Bean")

## **面向对象技术 3-5** 老版教材

### 面向对象开发

#### 面向对象定义：对象、类、抽象

![面向对象定义：对象、类、抽象](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5x2glj4vs6c0.webp "面向对象定义：对象、类、抽象")

#### 面向对象定义：封装、继承、多态

![面向对象定义：封装、继承、多态](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.7202n1zp3vw0.webp "面向对象定义：封装、继承、多态")

#### 面向对象定义：接口、消息、覆盖、重载、绑定

![面向对象定义：接口、消息、覆盖、重载、绑定](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3nzldz5pt5k0.webp "面向对象定义：接口、消息、覆盖、重载、绑定")

#### 面向对象：分析、需求建模

![面向对象：分析、需求建模](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4d8f09sina60.webp "面向对象：分析、需求建模")

#### 面向对象：设计、分析模型

![面向对象：设计、分析模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3xic8hftvcc.webp "面向对象：设计、分析模型")

#### 面向对象的设计原则

![面向对象的设计原则](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.21cx3ymp9r0g.webp "面向对象的设计原则")

#### 面向对象软件的测试的四个层次

![面向对象软件的测试的四个层次](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6n5bcofc2js0.webp "面向对象软件的测试的四个层次")

### 统一建模语言 UML

#### UML：定义、结构

![UML：定义、结构](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ayoarp30a00.webp "UML：定义、结构")

#### UML 事物：结构、行为、分组、注释

![UML 事物：结构、行为、分组、注释](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.204bcxcyslhc.webp "UML 事物：结构、行为、分组、注释")

#### UML 关系：依赖、关联、泛化、实现

![UML 关系：依赖、关联、泛化、实现](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.76k7nu9r7i80.webp "UML 关系：依赖、关联、泛化、实现")

#### UML 的分类

![UML 的分类](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1sqgnoleeav4.webp "UML 的分类")

##### 类图

![类图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.vfkc8sogi9c.webp "类图")

##### 对象图

![对象图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.38b756olc5u0.webp "对象图")

##### 用例图

![用例图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3tqgt7wwpso0.webp "用例图")

##### 序列图/顺序图

![序列图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.152nf78oo5eo.webp "序列图")

##### 通信图/协作图

![通信图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5se35jl1zsg0.webp "通信图")

##### 状态图

![状态图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.3gbzreo7h500.webp "状态图")

##### 活动图

![活动图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1nihtfnw1zy8.webp "活动图")

##### 构件图

![构件图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2ky7tqcqnjm0.webp "构件图")

##### 部署图

![部署图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.13qp5g4kncow.webp "部署图")

##### UML 视图

![UML 视图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6yrscew3tgw0.webp "UML 视图")

### **设计模式**

#### 设计模式分类、架构模式、设计模式、惯用法

![设计模式分类、架构模式、设计模式、惯用法](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6xusva4yddc0.webp "设计模式分类、架构模式、设计模式、惯用法")

#### 创建型设计模式

![创建型设计模式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5jssyxvg9ak.webp "创建型设计模式")

#### 结构型设计模式

![结构型设计模式](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4oa42fn1amu0.webp "结构型设计模式")

#### 行为型设计模式

![行为型设计模式1](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4aj4u8ga8zq0.webp "行为型设计模式1")
![行为型设计模式2](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.669ecjzd4uk0.webp "行为型设计模式2")

### 选择题相关题型及解题思路

- **2022 考察 UML 各种图的定义**
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.2efyz4xql04k.webp)
- 问是什么图：给出一个图示
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.74xq3xnerc00.webp)
- **考察设计模式的定义**，问是什么模式，英文名称需要记
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.31opvdzs4po0.webp)
- 考察面向对象的分析模型的定义
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.g9vl9z7rmmg.webp)
- 考察面向对象的设计原则
  ![alt](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ilhkiee1lg0.webp)

### 案例题相关题型及解题思路

- 给定主要功能描述，看图填空补充用例图：送分题，排除法。
- 考察 UML 各个图的定义：红色部分定义背一下。

## 知识产权与标准化 2-3

### 知识产权概述

![知识产权概述](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.5ey1e1llxg00.webp "知识产权概述")

### 知识产权保护期限

![知识产权保护期限](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.6q5q2mudneo0.webp "知识产权保护期限")

### 职务作品知识产权人的确定

![职务作品知识产权人的确定](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.274kw54d058g.webp "职务作品知识产权人的确定")

### 委托作品知识产权人的确定

![委托作品知识产权人的确定](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.4xn21oux0fk0.webp "委托作品知识产权人的确定")

### 侵权判定

![侵权判定](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.1c5rr35utx5s.webp "侵权判定")

### 标准划分：国际标准、国家标准、行业标准、区域/地方标准、企业标准

![标准划分：国际标准、国家标准、行业标准、区域/地方标准、企业标准](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/Development/image.211sk61ghpuo.webp "标准划分：国际标准、国家标准、行业标准、区域/地方标准、企业标准")

