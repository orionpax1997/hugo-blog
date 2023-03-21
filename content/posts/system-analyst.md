---
title: "软考-系统分析师"
date: 2022-04-24T19:37:52+08:00
draft: true
---

## 介绍

- 考试时间：5 月下旬
- 考核标准：75 分总分，45 分合格，所有科目统一
- 综合知识：客观题 75 道 150 分钟
- 案例分析：第一道必答，后面四道选答两道 90 分钟
- 论文写作：四选一 120 分钟

## 综合知识

范围广，把时间用于重要的知识点，各个击破，混合练习。

![52781650886538_](https://cdn.jsdelivr.net/gh/Humble-Xiang/picx-images@master/geek/52781650886538_.7jbclpbzfjk0.webp "综合知识知识点分布")

### 计算机组成与体系结构

- 编码及浮点数运算 ⭐️
- Flynn 分类法 ⭐️
- CISC 与 RISC ⭐⭐⭐
- 流水线技术 ⭐⭐⭐
- 计算机组成 ⭐
- **存储系统** ⭐⭐⭐⭐⭐
- 总线 ⭐⭐
- 校验码 ⭐
- 嵌入式系统 ⭐

#### 浮点数

浮点数的表示：N = 尾数 \* 基数<sup>指数</sup>

浮点数的运算过程：对阶 -> 尾数计算 -> 结果格式化

1. 一般尾数用补码，阶码(指数)用移码
2. 阶码(指数)的位数决定数的表示范围
3. 尾数的位数决定数的有效精度
4. 对阶时，小数向大数看齐
5. 对阶是通过较小数尾数右移实现的

#### Flynn 分类法

Flynn 于 1972 年提出了计算平台的 Flynn 分类法，主要根据指令流和数据流来分类，共分为四种类型的计算平台，分别是 SISD、SIMD、MISD、MIMD。

- SISD(Single instruction sigle data): 单指令流单数据流机器
- SIMD(Single instruction multiple data): 单指令流多数据流机器
- MISD(Multiple instruction sigle data): 多指令流单数据流机器
- MIMD(Multiple instruction Multiple data): 多指令流多数据流机器

| 类型 | 结构                           | 特性                       | 代表                                                      |
| ---- | ------------------------------ | -------------------------- | --------------------------------------------------------- |
| SISD | 单控制器、单处理器、单主存储器 | -                          | 单处理器系统                                              |
| SIMD | 单控制器、多处理器、多主存储器 | 各处理器异步执行同一条指令 | 并行处理机、阵列处理机、超级向量处理机、GPU               |
| MISD | 多控制器、单处理器、多主存储器 | 不可能、不实际             | 目前没有，有文献称流水线计算机为此类                      |
| MIMD | 多控制器、多处理器、多主存储器 | 作业、任务、指令全面并行   | 多核处理器（SMP、BMP、MP）、多处理机系统（MPP）、多计算机 |

#### **CISC 与 RISC**

**CISC 的英文全称为“Complex Instruction Set Computer”，即“复杂指令系统计算机”**，从计算机诞生以来，人们一直沿用 CISC 指令集方式。早期的桌面软件是按 CISC 设计的，并一直沿续到现在。目前，桌面计算机流行的 x86 体系结构即使用 CISC。微处理器(CPU)厂商一直在走 CISC 的发展道路，包括 Intel、AMD，还有其他一些现在已经更名的厂商，如 TI(德州仪器)、IBM 以及 VIA(威盛)等。在 CISC 微处理器中，程序的各条指令是按顺序串行执行的，每条指令中的各个操作也是按顺序串行执行的。顺序执行的优点是控制简单，但计算机各部分的利用率不高，执行速度慢。CISC 架构的服务器主要以 IA-32 架构(Intel Architecture，英特尔架构)为主，而且多数为中低档服务器所采用。

**RISC 的英文全称为“Reduced Instruction Set Computer”，即“精简指令集计算机”**，是一种执行较少类型计算机指令的微处理器，起源于 80 年代的 MIPS 主机(即 RISC 机)，RISC 机中采用的微处理器统称 RISC 处理器。这样一来，它能够以更快的速度执行操作(每秒执行更多百万条指令，即 MIPS)。因为计算机执行每个指令类型都需要额外的晶体管和电路元件，计算机指令集越大就会使微处理器更复杂，执行操作也会更慢。

![CISC 与 RISC](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.hd2djkckh5k.webp "CISC 与 RISC")

#### **流水线**

流水线是指在程序执行时多条指令重叠进行操作的一种准并行处理实现技术。各种部件同时处理是针对不同指令而言的，它们可同时为多条指令的不同部分进行工作，以提高各部件的利用率和指令的平均执行速度。

![流水线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.a8dbymhibqg.webp "流水线")

##### 执行时间计算公式

![执行时间计算公式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.330h1nscaay0.webp "执行时间计算公式")
![执行时间计算公式2](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.nedjdbjwclc.webp "执行时间计算公式2")

##### 吞吐量计算公式

![吞吐率计算公式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.7e334y28y6k0.webp "吞吐率计算公式")

##### 加速比计算公式

![加速比计算公式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1rwmlu2jftxc.webp "加速比计算公式")

##### 超标量流水线

![超标量流水线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.41xgqm61fhu0.webp "超标量流水线")

#### 计算机组成

##### CPU 的组成

![CPU的组成](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.7228m8uvlx40.webp "CPU的组成")

##### 计算机组成结构

![计算机组成结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.2d5zlb3vdskk.webp "计算机组成结构")

##### 嵌入式芯片

![嵌入式芯片](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.qe6zlvkn47k.webp "嵌入式芯片")

#### **存储系统**

##### 层次化存储结构

![层次化存储结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.86mck5yn4es.webp "层次化存储结构")

##### Cache

![Cache](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.770czk63ej40.webp "Cache")
![时空局部性](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.49j70lwd6ug0.webp "时空局部性")
![Cache 平均周期计算公式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1x5rzea2tl9c.webp "Cache 平均周期计算公式")
![Cache 映像方式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.6v6b1wl63f80.webp "Cache 映像方式")

- FIFO(First in First out): 先进先出
- LRU(Least recently used): 最近最少使用
- LFU(Least-frequently used): 最近不经常使用

![Cache 页面淘汰](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3ve1cnue7z00.webp "Cache 页面淘汰")

##### 主存编址

编址内容:

- 按字编址：存储体的存储单元是字存储单元，即最小寻址单位是一个字。
- 按字节编址：存储体的存储单元是字节存储单元，即最小寻址单位是一个字节，一个字节固定为 8bit/1B。

主存编址相关计算公式:

- 存储单元个数 = 最大地址 + 1 - 最小地址
- 总容量 = 存储单元个数 \* 编址内容
- 总片数 = 总容量 / 每片的容量

##### 磁盘基本结构与存取过程

![平均存取时间计算公式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.4r0yy09kxew0.webp "平均存取时间计算公式")

##### 磁盘优化分布存储

- 最大等待时间 = 磁盘旋转周期 - 单个物理块的旋转时间

##### 磁盘单缓冲区与双缓冲区读取

单缓冲区与双缓冲区读取:

- 单缓冲区: 读写不能同时进行
- 双缓冲区: 读缓冲区一的时候，可以写缓冲区二

##### 磁盘移臂调度算法

![磁盘移臂调度算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.7i6za6uicms0.webp "磁盘移臂调度算法")

#### 总线

![总线](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3tulolsdd3c0.webp "总线")

#### 校验码

![校验码](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3dokxqnwr0y0.webp "校验码")

##### 奇偶校验

![奇偶校验](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1816sb5pkw2k.webp "奇偶校验")

##### 循环校验码 CRC

![循环校验码CRC](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.2k3w1ufbkba0.webp "循环校验码CRC")

##### 海明校验

校验码位数计算公式： 2<sup>r</sup> >= m(信息位位数) + r(校验码位数) + 1
求 r 的最小值

#### 扩展

##### 进制转换

二进制与十六进制转化使用 8421 法，与八进制转换使用 421 法。

![按权展开法R进制转十进制](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.464ibd74u9k0.webp "按权展开法R进制转十进制")
![除基取余倒记法十进制转R进制](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.27o6a4u1oqf4.webp "除基取余倒记法十进制转R进制")

##### 码制

- 原码：正数是其二进制本身；负数是符号位为 1,数值部分取 X 绝对值的二进制。
- 反码：正数的反码和原码相同；负数是符号位为 1,其它位是原码取反。
- 补码：正数的补码和原码，反码相同；负数是符号位为 1，其它位是原码取反，未位加 1。（或者说负数的补码是其绝对值反码未位加 1）
- 移码：将符号位取反的补码（不区分正负）

### 操作系统

![操作系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.44dam5wxqvq0.webp "操作系统")

#### 进程管理

##### 进程的基本概念

![进程的概念](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.2zz9ywmx9ao0.webp "进程的概念")
![PCB](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.wj1re53fys0.webp "PCB")
![进程与程序](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.ah4t7hwdgw4.webp "进程与程序")
![进程与线程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.6zirl6agpoo0.webp "进程与线程")

##### 进程的状态

![进程的状态](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.15kyqc7z781s.webp "进程的状态")

##### 信号量与 PV 操作

![进程的同步与互斥](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.247blhg9dshs.webp "进程的同步与互斥")
![PV操作](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.2zjwzuj4t3u0.webp "PV操作")

##### 前趋图

![前趋图](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3jbt7g07ch20.webp "前趋图")
![前趋图和PV操作](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.43l8di6uhnk0.webp "前趋图和PV操作")

##### 死锁

死锁的资源数计算：至少需要多少个资源不可能出现死锁 >= 进程数 \* (每个进程需要的资源数 - 1) + 1

![死锁](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.5uvotunfu8w0.webp "死锁")

##### 银行家算法

![银行家算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.46h41dbhrjs0.webp "银行家算法")

#### 存储管理

##### 页式存储

![页式存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.4jenedgxgyo0.webp "页式存储")
![页式存储淘汰顺序](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.74tal9m2na80.webp "页式存储淘汰顺序")

##### 段式存储

![段式存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.kchncnkmp74.webp "段式存储")

##### 段页式存储

![段页式存储](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1jl75thkf01s.webp "段页式存储")

##### 快表

![快表](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.52if5ohcwrg0.webp "快表")

##### 页面置换算法

![页面置换算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.2mvjaiiu8ey0.webp "页面置换算法")

#### 文件管理

##### 索引文件结构

磁盘索引块个数 = 磁盘索引块大小 / 每个地址项大小

一级索引能表示的最后一个逻辑块号 = 磁盘索引块个数 + 起始逻辑块号 - 1

二级索引能表示的最后一个逻辑块号 = 磁盘索引块个数<sup>2</sup> + 起始逻辑块号 - 1

单个文件表示的最大长度 = (最后一个逻辑块号 + 1) \* 磁盘索引块大小

![索引文件结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3zcm30q6gu40.webp "索引文件结构")

##### 位示图

空闲为”0“，占用为“1”。

位示图大小(字) = 物理块的总个数 / 字长

(磁盘编号 + 1) / 字长 = 字号 余 (位号 + 1)

![位示图](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1m93pbwycsow.webp "位示图")

##### 树形目录结构

![树形目录结构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.o5cscp7ihgg.webp "树形目录结构")

#### 微内核操作系统

![微内核操作系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.646da1d0umg0.webp "微内核操作系统")

#### 嵌入式系统

![嵌入式系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.6msi2vptk7g.webp "嵌入式系统")

![嵌入式操作系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.69oa4tvzm3s0.webp "嵌入式操作系统")

![实时操作系统调度算法](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3qmih72szya0.webp "实时操作系统调度算法")

### 数据库系统

![数据库系统](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.4dgho1om5gg0.webp "数据库系统")

#### 数据库模式

![数据库模式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.4rozupkziig0.webp "数据库模式")

![关系表类型](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.1ulwrx1c75uo.webp "关系表类型")

![数据库视图](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.z0qzioj7v1s.webp "数据库视图")

#### 分布式数据库

![分布式数据库特点](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.3bismdbizho0.webp "分布式数据库特点")

![分布式数据库架构](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.8uqsvf5ttio.webp "分布式数据库架构")

![分布透明性](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.37q8482rzxq0.webp "分布透明性")

![分布式数据库事务处理](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.numexot8ae8.webp "分布式数据库事务处理")

#### 数据库设计过程

![数据库设计过程](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.45ao9qxhfvy0.webp "数据库设计过程")

#### 概念结构设计

![概念结构设计](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.4tdy0wbrioa0.webp "概念结构设计")

#### 逻辑结构设计

![完整性约束](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.nkdrl2ttcds.webp "完整性约束")

![逻辑结构设计](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.5sevi8yomxo0.webp "逻辑结构设计")

![关系模式](https://cdn.staticaly.com/gh/Humble-Xiang/picx-images@master/geek/image.11j1hbbibci8.webp "关系模式")

#### 关系代数

关系代数中包括了：并、交、差、乘、选择、投影、联接、除、自然联接等操作。

五个基本操作：并(∪)、差(-)、笛卡尔积(×)、投影(π)、选择(σ)

四个组合操作：交(∩)、联接(等值联接)、自然联接(⋈)、除法(÷)

注 2：等值连接表示先做笛卡尔积(×)之后，对相应列进行选择或等值关联后的结果(仅筛选行、不筛选列)

注 2：自然连接表示两个关系中若有相同名称的属性，则自动作为关联条件，且仅列出一列

## 案例分析

多练历年试题，从简单问题入手。对于技术主题，要有意识的组织语言进行总结。给出倾向的问题，要懂得“顺势而为”的解决问题。

## 论文写作

使用写作技巧，提前选好项目，写好字，提前准备素材，模块化的拼接出来论文。
