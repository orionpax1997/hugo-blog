---
title: "软考-系统架构师"
date: 2023-08-06T18:21:01+08:00
draft: true
---

## 计算机系统基础知识

### 计算机硬件

#### 相关概念

##### 计算机硬件组成

![计算机硬件组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.50u9cjryeck0.png "计算机硬件组成")

##### 处理器

![CPU 的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5nujeeacm3o0.webp "CPU 的功能")

![CPU 的组成](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.fmceksfw06w.webp "CPU 的组成")

##### 存储器

![分级存储体系与局部性原理](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.33dkhwgef0o0.webp "分级存储体系与局部性原理")

![Cache 概念](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hxgdiahn3g.webp "Cache 概念")

![Cache 映像方式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5ep6d4fesqk0.webp "Cache 映像方式1")
![Cache 映像方式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.17iz0rps4rxc.webp "Cache 映像方式2")

![Cache 替换算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ow3qsbt8vm0.webp "Cache 替换算法")

![Cache 命中率及平均时间](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.29nk73n2unb4.webp "Cache 命中率及平均时间")

![磁盘结构和参数](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1oeoxoad1p4w.webp "磁盘结构和参数")

![磁盘调度算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.15ryesazcin4.webp "磁盘调度算法")

![内存与接口地址的编址方法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.b1pnqtuf1ug.webp "内存与接口地址的编址方法")

##### 总线

![总线的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5kdhmitxwic0.webp "总线的分类")

##### 外部设备

![计算机和外设间的数据交互方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5zlfwjwdgg40.webp "计算机和外设间的数据交互方式")

##### 指令

![计算机指令的组成和执行过程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6qdek30lpc80.webp "计算机指令的组成和执行过程")

![计算机指令的寻址方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.ou2ih4m6j5s.webp "计算机指令的寻址方式")

![计算机指令的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.733cz61t52g0.webp "计算机指令的分类")

![指令流水线](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5t6g10ok4v40.webp "指令流水线")

##### 校验码

![奇偶校验码](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1pgi3nxmcx4w.webp "奇偶校验码")

![CRC 循环冗余校验码1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.24v5f4oszysg.webp "CRC 循环冗余校验码1")
![CRC 循环冗余校验码2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1elsprl1sue8.webp "CRC 循环冗余校验码2")

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

#### 操作系统

##### 相关概念

###### 操作系统

![操作系统的定义](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4ta08p68eug0.webp "操作系统的定义")

![操作系统的功能](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4ozf20qqg6g0.webp "操作系统的功能")

![操作系统的分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1hfphfzgmusg.webp "操作系统的分类")

###### 进程管理

![进程的组成和状态](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1qa522vuo20w.webp "进程的组成和状态")

![前趋图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4cxaged0yjq0.webp "前趋图")

![进程资源图](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.39n1vb9hou20.webp "进程资源图")

![进程同步与互斥](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.u47c4pdg4uo.webp "进程同步与互斥")

![PV 操作](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6i8o5hlsafk0.webp "PV 操作")

![生产者消费者问题](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5hiw1kyeeug0.webp "生产者消费者问题")

![进程调度方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6c2qe0jxwls0.webp "进程调度方式")

![进程调度算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2ty2cv623b60.webp "进程调度算法")

![死锁](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2wqhyeh9wvq0.webp "死锁")

![线程](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6lmden7uo1g0.webp "线程")

###### 存储管理

![分区存储方式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.qmuxffsi1n4.webp "分区存储方式")

![分区适应法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.32xww0kvkcy0.webp "分区适应法")

![分页存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2scnsm54dvc0.webp "分页存储")

![页面置换算法](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.727k1ckq7ms0.webp "页面置换算法")

![快表](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3iiym37nnks0.webp "快表")

![分段存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.18syec51w934.webp "分段存储")

![段页式存储](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4tqudwbw0om0.webp "段页式存储")

###### 设备管理

![设备管理概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1g5x73h6fyqo.webp "设备管理概述")

![I/O 设备](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.34mylt9dmqw0.webp "I/O 设备")

![设备管理技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1maz233knxk0.webp "设备管理技术")

#### 文件系统

##### 相关概念

![文件管理概述](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7gs2ocqkw480.webp "文件管理概述")

![文件结构分类](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3xwfe8q9sgu0.webp "文件结构分类")

![索引文件结构](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6hs13ibogkg0.webp "索引文件结构")

![文件目录](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.24huvvajhps0.webp "文件目录")

![文件存储空间管理1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5pr9lq294js0.webp "文件存储空间管理1")
![文件存储空间管理2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.67e5ut4ovnc0.webp "文件存储空间管理2")

#### 嵌入式系统及软件

![嵌入式操作系统的特点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7089o6hoe840.webp "嵌入式操作系统的特点")

## 数据库设计基础知识

### 相关概念

#### 数据库基本概念

![数据库的基本特征](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.191f8qq6f1kw.webp "数据库的基本特征")

![数据库系统与数据库管理系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.37h9jxeop740.webp "数据库系统与数据库管理系统")

![三级模式两级映像](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.4xrvqgybsj80.webp "三级模式两级映像")

![数据模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1t4qn0udkou8.webp "数据模型")

![E-R 模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3zjeo8s5jem0.webp "E-R 模型")

![关系模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5c5pc1fefds0.webp "关系模型")

![关系模型优缺点](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.1pvv2q4g0xk0.webp "关系模型优缺点")

![E-R 模型转关系模型](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3ht5wfvcgt20.webp "E-R 模型转关系模型")

![数据库安全1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3cv1j4ljnny0.webp "数据库安全1")

![数据库安全2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3tqyj91k41o0.webp "数据库安全2")

![分布式数据库](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5fjzuunsuas0.webp "分布式数据库")

![数据仓库技术1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5a5firz8ynw0.webp "数据仓库技术1")

![数据仓库技术2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7kpdbrrtbn40.webp "数据仓库技术2")

![数据仓库技术3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2cadqwnfv30g.webp "数据仓库技术3")

![大数据](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7b421s6py9c0.webp "大数据")

#### 关系数据库

![关系代数并、交、差](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.r05gox34s1c.webp "关系代数并、交、差")

![关系代数笛卡尔积、投影、选择](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.53od7g3d1cg0.webp "关系代数笛卡尔积、投影、选择")

![关系代数自然连接](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2p08mdqw7u20.webp "关系代数自然连接")

![函数依赖规则](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6ekmpcoz8380.webp "函数依赖规则")

![函数依赖的公理系统](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.76imy2qc0wc0.webp "函数依赖的公理系统")

![并发控制1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2i75upllyj40.webp "并发控制1")

![并发控制2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6g3ytt1vz1g0.webp "并发控制2")

![封锁协议1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.55ujp9qldz00.webp "封锁协议1")

![封锁协议2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3bsu6p7e8wo0.webp "封锁协议2")

![封锁协议3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.yy6tuoni09c.webp "封锁协议3")

#### 数据库设计

![数据库设计](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5dzoaaxpfaw0.webp "数据库设计")

![键与约束](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.64h6x2fudc4.webp "键与约束")

![第一范式1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5qei5j4x6tw0.webp "第一范式1")

![第一范式2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2m933rm0do80.webp "第一范式2")

![第二范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.2sw5n9mldvo0.webp "第二范式")

![第三范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.6twirr83ghc0.webp "第三范式")

![BC范式](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.3yni6tbwn540.webp "BC范式")

![模式分解1](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.7j4ghkffvi40.webp "模式分解1")

![模式分解2](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.682z4d6u4gg0.webp "模式分解2")

![模式分解3](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.omahc7zk2uo.webp "模式分解3")

![反规范化技术](https://jsd.cdn.zzko.cn/gh/Humble-Xiang/picx-images@master/Development/image.5kt1osw7mwg0.webp "反规范化技术")
