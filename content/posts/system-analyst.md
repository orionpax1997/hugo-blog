---
title: "软考-系统分析师"
date: 2022-04-24T19:37:52+08:00
---

## 介绍

- 考试时间：5 月下旬
- 考核标准：75 分总分，45 分合格，所有科目统一
- 综合知识：客观题 75 道 150 分钟
- 案例分析：第一道必答，后面四道选答两道 90 分钟
- 论文写作：四选一 120 分钟

## 综合知识

范围广，把时间用于重要的知识点，各个击破，混合练习。

![52781650886538_](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/52781650886538_.7jbclpbzfjk0.webp "综合知识知识点分布")

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

#### 编码及浮点数预算

##### 码制

- 真值: 带正负号的原数被叫做**真值**。
- 机器数: 把正负号给**数字化**后的数值，被称为**机器数**。
- 原码: **原码就是符号位和真值的绝对值组成的**。它和真值之间仅仅是正负号被换成了`0`和`1`。
- 补码: 正数的补码和原码相同；负数是符号位为 `1`，其它位是**原码取反，未位加 `1`**。
- 反码: 正数的反码和原码相同；负数是符号位为 `1`，其它位是**原码取反**，主要用于原码和补码的相互转换，反码作为中间数过度使用。
- 移码: 移码就是将**按补码符号为进行取反**，可以比较大小，但是判断不了正负。

{{< card "https://segmentfault.com/a/1190000024426172" >}}

###### 补数和模

- 负数的绝对值，和它的补数相加，就是模。
- 负数和模相加，就是负数的补数。
- 正数的补数，就是正数本身。(指的是正数的补码表示和原码一致)

##### 浮点数

浮点数的表示：N = 尾数 \* 基数<sup>阶码(指数)</sup>

浮点数的运算过程：对阶 -> 尾数计算 -> 结果格式化

1. 一般尾数用补码，阶码(指数)用移码
2. 阶码(指数)的位数决定数的表示范围
3. 尾数的位数决定数的有效精度
4. 对阶时，小数向大数看齐
5. 对阶是通过较小数尾数右移实现的

{{< card "https://segmentfault.com/a/1190000024485146" >}}

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

| 指令系统类型         | 指令                                                                                     | 寻址方式         | 实现方式                                             | 其他                       |
| -------------------- | ---------------------------------------------------------------------------------------- | ---------------- | ---------------------------------------------------- | -------------------------- |
| CISC（复杂指令系统） | 数量多，使用频率差别大，可变长格式                                                       | 支持多种寻址方式 | 微程序控制技术(微码)                                 | 研制周期长                 |
| RISC（精简指令系统） | 数量少，使用频率接近，定长格式，大部分为单周期指令，操作寄存器，只有 Load/Store 操作内存 | 支持方式少       | 增加了通用寄存器；硬布线逻辑控制为主；适合采用流水线 | 优化编译，有效支持高级语言 |

#### **流水线**

流水线是指在程序执行时，多条指令重叠进行操作的一种准并行处理的实现技术。各种部件同时处理是针对不同指令而言的，它们同时为多条指令的不同部分进行工作，以提高各部件的利用率和指令的平均执行速度。

- `流水线理论执行时间 = 完成第一条指令需要的时间(一条指令正常执行的耗时) + (指令条数 - 1) * 流水线周期(流水线周期为执行时间最长的一段)`

- `流水线实践执行时间 = 执行一条指令的步骤数 * 流水线周期(流水线周期为执行时间最长的一段) + (指令条数 - 1) * 流水线周期(流水线周期为执行时间最长的一段)`

- `流水线吞吐率(TP) = 指令条数 / 流水线执行时间`

- `流水线最大吞吐率 = 1 / 流水线周期(流水线周期为执行时间最长的一段)`

- `加速比 = 不使用流水线的执行时间 / 使用流水线的执行时间`

- 超标量流水线: `指令条数 / 超标量流水线的度数` 的结果向上取整得到每条流水线的指令条数，带入到流水线执行时间公式计算。

{{< card "https://segmentfault.com/a/1190000039201150" >}}

#### 计算机组成

##### CPU 的组成

###### 运算器

- 算术逻辑单元(ALU)
  - ALU:算术逻辑单元，是运算器的主要组成
  - 常见的位运算（左右移，与或非等）
  - 算术运算（加减乘除等）
- 累加寄存器(AC)
  - 为 ALU 提供一个工作区
  - 可保存 ALU(算术逻辑单元)的运算中间结果
- 数据缓冲寄存器：DR
  - 分为输入缓冲和输出缓冲
  - 输入缓冲暂时存放外设送过来的数据
  - 输出缓冲暂时存放送往外设的数据
- 状态字寄存器：PSW
  - 存放运算状态（条件码、进位、溢出、结果正负等）
  - 存放运算控制信息（调试跟踪标记为、允许中断位等）

###### 控制器

- 程序计数器（PC）
  - 程序计数器用来存储下一条指令的地址
  - CPU 会循环从程序计数器中拿出指令
  - 当指令被拿出时，指向下一条指令
- 指令寄存器（IR）
  - 指令寄存器是控制器的主要部件之一
  - 缓存从主存或高速缓存取的计算机指令
- 地址寄存器（AR）
  - 保存当前 CPU 正要访问的内存单元的地址
- 指令译码器（ID）
  - 指令译码器是控制器的主要部件之一
  - 计算机指令由操作码和地址码组成
  - 翻译操作码对应的操作以及控制传输地址码对应的数据
- 时序发生器
  - 电气工程领域，用于发送时序脉冲
  - CPU 依据不同的时序脉冲有节奏的进行工作

##### 计算机组成结构

###### 冯•诺依曼结构

冯•诺依曼结构也称普林斯顿结构，是一种将程序指令存储器和数据存储器合并在一起的存储器结构。

- 一般用于 PC 处理器，如 I3，I5，I7 处理器
- 指令与数据存储器合并在一起
- 指令与数据都通过相同的数据总线传输

###### 哈佛结构

哈佛结构是一种将程序指令存储和数据存储分开的存储器结构。哈佛结构是一种并行体系结构，它的主要特点是将程序和数据存储在不同的存储空问中，即程序存储器和数据存储器是两个独立的存储器，每个存储器独立编址、独立访问。

- **一般用于嵌入式系统处理器(DSP)数字信号处理(DSP, Digital Signal Processing)**
- 指令与数据分开存储，可以并行读取，有较高数据的吞吐率
- 有 4 条总线：指令和数据的数据总线与地址总线

##### 嵌入式芯片

![嵌入式芯片](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.qe6zlvkn47k.webp "嵌入式芯片")

#### **存储系统**

##### 层次化存储结构

![层次化存储结构](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.86mck5yn4es.webp "层次化存储结构")

##### Cache

![Cache](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.770czk63ej40.webp "Cache")
![时空局部性](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.49j70lwd6ug0.webp "时空局部性")
![Cache 平均周期计算公式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1x5rzea2tl9c.webp "Cache 平均周期计算公式")
![Cache 映像方式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6v6b1wl63f80.webp "Cache 映像方式")

- FIFO(First in First out): 先进先出
- LRU(Least recently used): 最近最少使用
- LFU(Least-frequently used): 最近不经常使用

![Cache 页面淘汰](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3ve1cnue7z00.webp "Cache 页面淘汰")

##### 主存编址

编址内容:

- 按字编址：存储体的存储单元是字存储单元，即最小寻址单位是一个字。
- 按字节编址：存储体的存储单元是字节存储单元，即最小寻址单位是一个字节，一个字节固定为 8bit/1B。

主存编址相关计算公式:

- 存储单元个数 = 最大地址 + 1 - 最小地址
- 总容量 = 存储单元个数 \* 编址内容
- 总片数 = 总容量 / 每片的容量

##### 磁盘基本结构与存取过程

![平均存取时间计算公式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4r0yy09kxew0.webp "平均存取时间计算公式")

##### 磁盘优化分布存储

- 最大等待时间 = 磁盘旋转周期 - 单个物理块的旋转时间

##### 磁盘单缓冲区与双缓冲区读取

单缓冲区与双缓冲区读取:

- 单缓冲区: 读写不能同时进行
- 双缓冲区: 读缓冲区一的时候，可以写缓冲区二

##### 磁盘移臂调度算法

![磁盘移臂调度算法](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.7i6za6uicms0.webp "磁盘移臂调度算法")

#### 总线

![总线](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3tulolsdd3c0.webp "总线")

#### 校验码

![校验码](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3dokxqnwr0y0.webp "校验码")

##### 奇偶校验

![奇偶校验](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1816sb5pkw2k.webp "奇偶校验")

##### 循环校验码 CRC

![循环校验码CRC](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2k3w1ufbkba0.webp "循环校验码CRC")

##### 海明校验

校验码位数计算公式： 2<sup>r</sup> >= m(信息位位数) + r(校验码位数) + 1
求 r 的最小值

### 操作系统

![操作系统](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.44dam5wxqvq0.webp "操作系统")

#### 进程管理

##### 进程的基本概念

![进程的概念](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2zz9ywmx9ao0.webp "进程的概念")
![PCB](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.wj1re53fys0.webp "PCB")
![进程与程序](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.ah4t7hwdgw4.webp "进程与程序")
![进程与线程](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6zirl6agpoo0.webp "进程与线程")

##### 进程的状态

![进程的状态](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.15kyqc7z781s.webp "进程的状态")

##### 信号量与 PV 操作

![进程的同步与互斥](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.247blhg9dshs.webp "进程的同步与互斥")
![PV操作](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2zjwzuj4t3u0.webp "PV操作")

##### 前趋图

![前趋图](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3jbt7g07ch20.webp "前趋图")
![前趋图和PV操作](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.43l8di6uhnk0.webp "前趋图和PV操作")

##### 死锁

死锁的资源数计算：至少需要多少个资源不可能出现死锁 >= 进程数 \* (每个进程需要的资源数 - 1) + 1

![死锁](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.5uvotunfu8w0.webp "死锁")

##### 银行家算法

![银行家算法](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.46h41dbhrjs0.webp "银行家算法")

#### 存储管理

##### 页式存储

![页式存储](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4jenedgxgyo0.webp "页式存储")
![页式存储淘汰顺序](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.74tal9m2na80.webp "页式存储淘汰顺序")

##### 段式存储

![段式存储](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.kchncnkmp74.webp "段式存储")

##### 段页式存储

![段页式存储](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1jl75thkf01s.webp "段页式存储")

##### 快表

![快表](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.52if5ohcwrg0.webp "快表")

##### 页面置换算法

![页面置换算法](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2mvjaiiu8ey0.webp "页面置换算法")

#### 文件管理

##### 索引文件结构

磁盘索引块个数 = 磁盘索引块大小 / 每个地址项大小

一级索引能表示的最后一个逻辑块号 = 磁盘索引块个数 + 起始逻辑块号 - 1

二级索引能表示的最后一个逻辑块号 = 磁盘索引块个数<sup>2</sup> + 起始逻辑块号 - 1

单个文件表示的最大长度 = (最后一个逻辑块号 + 1) \* 磁盘索引块大小

![索引文件结构](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3zcm30q6gu40.webp "索引文件结构")

##### 位示图

空闲为”0“，占用为“1”。

位示图大小(字) = 物理块的总个数 / 字长

(磁盘编号 + 1) / 字长 = 字号 余 (位号 + 1)

![位示图](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1m93pbwycsow.webp "位示图")

##### 树形目录结构

![树形目录结构](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.o5cscp7ihgg.webp "树形目录结构")

#### 微内核操作系统

![微内核操作系统](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.646da1d0umg0.webp "微内核操作系统")

#### 嵌入式系统

![嵌入式系统](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6msi2vptk7g.webp "嵌入式系统")

![嵌入式操作系统](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.69oa4tvzm3s0.webp "嵌入式操作系统")

![实时操作系统调度算法](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3qmih72szya0.webp "实时操作系统调度算法")

### 数据库系统

![数据库系统](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4dgho1om5gg0.webp "数据库系统")

#### 数据库模式

![数据库模式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4rozupkziig0.webp "数据库模式")

![关系表类型](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1ulwrx1c75uo.webp "关系表类型")

![数据库视图](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.z0qzioj7v1s.webp "数据库视图")

#### 分布式数据库

![分布式数据库特点](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3bismdbizho0.webp "分布式数据库特点")

![分布式数据库架构](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.8uqsvf5ttio.webp "分布式数据库架构")

![分布透明性](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.37q8482rzxq0.webp "分布透明性")

![分布式数据库事务处理](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.numexot8ae8.webp "分布式数据库事务处理")

#### 数据库设计过程

![数据库设计过程](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.45ao9qxhfvy0.webp "数据库设计过程")

#### 概念结构设计

![概念结构设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4tdy0wbrioa0.webp "概念结构设计")

#### 逻辑结构设计

![完整性约束](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.nkdrl2ttcds.webp "完整性约束")

![逻辑结构设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.5sevi8yomxo0.webp "逻辑结构设计")

![关系模式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.11j1hbbibci8.webp "关系模式")

#### 关系代数

关系代数中包括了：并、交、差、乘、选择、投影、联接、除、自然联接等操作。

五个基本操作：并(∪)、差(-)、笛卡尔积(×)、投影(π)、选择(σ)

四个组合操作：交(∩)、联接(等值联接)、自然联接(⋈)、除法(÷)

注 2：等值连接表示先做笛卡尔积(×)之后，对相应列进行选择或等值关联后的结果(仅筛选行、不筛选列)

注 2：自然连接表示两个关系中若有相同名称的属性，则自动作为关联条件，且仅列出一列

#### 规范化理论

##### 非规范化可能存在的问题

非规范化的关系模式，可能存在的问题包括：数据冗余、更新异常、插入异常、删除异常

##### 规范化理论基本概念

![键](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.ethsvxqj4ow.webp "键")

![求候选键](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.558alejw2pw0.webp "求候选键")

![函数依赖](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6flulj7aqz80.webp "函数依赖")

##### Armstrong 公理

![Armstrong 公理1](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6ieodi9ec340.webp "Armstrong 公理1")

![Armstrong 公理2](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.g3o9o6yxds0.webp "Armstrong 公理2")

##### 范式判断

![范式](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3unjtsj6hcw0.webp "范式")

1NF 是对属性的`原子性`，要求属性具有原子性，不可再分解；

> 表：字段 1、 字段 2(字段 2.1、字段 2.2)、字段 3 ......

如学生（学号，姓名，性别，出生年月日），如果认为最后一列还可以再分成（出生年，出生月，出生日），它就不是一范式了，否则就是；

2NF 是对记录的`唯一性`，要求记录有唯一标识，即实体的唯一性，即**不存在部分依赖**；

> 表：学号、课程号、姓名、学分;

这个表明显说明了两个事务:学生信息, 课程信息;由于非主键字段必须依赖主键，这里**学分依赖课程号**，**姓名依赖与学号**，所以不符合二范式。

**可能会存在问题：**

- `数据冗余:`，每条记录都含有相同信息；
- `删除异常：`删除所有学生成绩，就把课程信息全删除了；
- `插入异常：`学生未选课，无法记录进数据库；
- `更新异常：`调整课程学分，所有行都调整。

**正确做法:**

> 学生：`Student`(学号, 姓名)；
> 课程：`Course`(课程号, 学分)；
> 选课关系：`StudentCourse`(学号, 课程号, 成绩)。

**如果一个关系属于第二范式**,并且在`两个(或多个)非主键属性之间不存在函数依赖`。(非主键属性之间的函数依赖也称为传递依赖),那么这个关系属于第三范式。

3NF 是对字段的`冗余性`，要求任何字段不能由其他字段派生出来，它要求字段没有冗余，即**不存在传递依赖**；

> 表: 学号, 姓名, 年龄, 学院名称, 学院电话

**注意** 上表属于第二范式，因为主键由单个属性组成（学号）

因为存在**依赖传递**: (学号) → (学生)→(所在学院) → (学院电话) 。

**可能会存在问题：**

- `数据冗余:`有重复值；
- `更新异常：`有重复的冗余信息，修改时需要同时修改多条记录，否则会出现**数据不一致的情况** 。

**正确做法：**

> 学生：(学号, 姓名, 年龄, 所在学院)；
>
> 学院：(学院，学院名称， 电话)。

BC 范式（BCNF）是 Boyce-Codd 范式的缩写，其定义是：在关系模式中每一个决定因素都包含候选键，也就是说，只要属性或属性组 A 能够决定任何一个属性 B，则 A 的子集中必须有候选键。BCNF 范式排除了任何属性(不光是非主属性，2NF 和 3NF 所限制的都是非主属性)对候选键的传递依赖与部分依赖。

比如我们有一个学生导师表，其中包含字段：学生 ID，专业，导师，专业 GPA，这其中学生 ID 和专业是联合主键。

| StudentId | Major    | Advisor | MajGPA |
| --------- | -------- | ------- | ------ |
| 1         | 人工智能 | Edward  | 4.0    |
| 2         | 大数据   | William | 3.8    |
| 1         | 大数据   | William | 3.7    |
| 3         | 大数据   | Joseph  | 4.0    |

这个表的设计满足三范式，有主键，不存在主键的部分依赖，不存在非主键的传递依赖。但是这里存在另一个依赖关系，“专业”函数依赖于“导师”，也就是说每个导师只做一个专业方面的导师，只要知道了是哪个导师，我们自然就知道是哪个专业的了。

所以这个表的部分主键依赖于非主键部分，那么我们可以进行以下的调整，拆分成 2 个表：

学生导师表：

| StudentId | Advisor | MajGPA |
| --------- | ------- | ------ |
| 1         | Edward  | 4.0    |
| 2         | William | 3.8    |
| 1         | William | 3.7    |
| 3         | Joseph  | 4.0    |

导师表：

| Advisor | Major    |
| ------- | -------- |
| Edward  | 人工智能 |
| William | 大数据   |
| Joseph  | 大数据   |

##### 模式分解

![保持函数依赖](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6022ydqw60c0.webp "保持函数依赖")

![无损分解](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4otba378myy0.webp "无损分解")

#### 数据库控制技术

##### 并发控制

![事务的特性](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2ygfkj444qa0.webp "事务的特性")

![并发的问题](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.21aghk58m8tc.webp "并发的问题")

![封锁协议1](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1nchl3glex34.webp "封锁协议1")

![封锁协议2](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.484z7vvftg20.webp "封锁协议2")

##### 数据库的安全性

![数据库的安全性](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.9k5c3w903yk.webp "数据库的安全性")

##### 数据库备份与恢复技术

![数据备份1](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.4zrd6pe7kiw0.webp "数据备份1")

![数据备份2](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2bpepyn4p8g0.webp "数据备份2")

![故障与恢复](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.2fhdyh253xa8.webp "故障与恢复")

### 计算机网络

#### 计算机网络概述

![计算机网络概述](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.v1oj5pddjts.webp "计算机网络概述")

#### TCP

##### TCP/IP 协议组

![TCP/IP 协议族1](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.227u54oljb34.webp "TCP/IP 协议族1")
![TCP/IP 协议族2](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.1a98mr0xyw2o.webp "TCP/IP 协议族2")
![TCP 与 UDP](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.5dlhewguex4.webp "TCP 与 UDP")

##### 开放互联参考模型

![OSI/RM 七层模型](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.7i66xd0p2g40.webp "OSI/RM 七层模型")

##### DNS 服务应用

![DNS](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.60guns9rzoc0.webp "DNS")

##### DHCP 服务应用

![DHCP](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.6h795s9nb6w0.webp "DHCP")

#### 网络规划与设计

![网络规划与设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3zxah0czvz60.webp "网络规划与设计")

![逻辑网络设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.7a504pa8irk0.webp "逻辑网络设计")

![物理网络设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.3jzxnrnm3vs0.webp "物理网络设计")

![层次化网络设计](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.5z4enzh338o0.webp "层次化网络设计")

#### 网络存储技术

![网络存储技术分类](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.45tdrjr5wt40.webp "网络存储技术分类")

![Raid](https://raw.githubusercontent.com/orionpax1997/picx-images-hosting/master/geek/image.5hbp9y5cv8s0.webp "Raid")

## 计算公式

### 进制转换

- 二进制 → 八进制: 取三合一法
- 二进制 → 十六进制: 取四合一法
- 八进制 → 二进制: 取一分三法
- 十六进制 → 二进制: 取一分四法

- R 进制 → 十进制: 按权展开法
- 十进制 → R 进制: 除基取余倒记法

从右往左数二进制的 1 代表的值分别为，4096|2048|1024|512|256|128|64|32|16|8|4|2|1 ，因此在十进制和二进制转换的时候可以使用对码的方式进行转换。

- 二进制 → 十进制: 把二进制每位上的 1 对应的十进制数相加。
- 十进制 → 二进制: 从左到右往右减，能减的记 1，不能减的记 0，余数接着往下减。

{{< card "https://www.cnblogs.com/gaizai/p/4233780.html" >}}

### 流水线

- `流水线理论执行时间 = 完成第一条指令需要的时间(一条指令正常执行的耗时) + (指令条数 - 1) * 流水线周期(流水线周期为执行时间最长的一段)`

- `流水线实践执行时间 = 执行一条指令的步骤数 * 流水线周期(流水线周期为执行时间最长的一段) + (指令条数 - 1) * 流水线周期(流水线周期为执行时间最长的一段)`

- `流水线吞吐率(TP) = 指令条数 / 流水线执行时间`

- `流水线最大吞吐率 = 1 / 流水线周期(流水线周期为执行时间最长的一段)`

- `加速比 = 不使用流水线的执行时间 / 使用流水线的执行时间`

- 超标量流水线: `指令条数 / 超标量流水线的度数` 的结果向上取整得到每条流水线的指令条数，带入到流水线执行时间公式计算。

## 案例分析

多练历年试题，从简单问题入手。对于技术主题，要有意识的组织语言进行总结。给出倾向的问题，要懂得“顺势而为”的解决问题。

## 论文写作

使用写作技巧，提前选好项目，写好字，提前准备素材，模块化的拼接出来论文。
