# 系统架构设计师最后冲刺


## 选择

### 数据库

### **架构风格**

- 软件架构为软件系统提供了一个**结构、行为和属性**的高级抽象
- 软件架构风格是特定应用领域的**惯用模式**，架构定义一个**词汇表**和一组**约束**
- 数据流：面向数据流，按照一定的顺序从前向后执行程序
  - 批处理：以**整体**为单位
  - 管道-过滤器：优点是模块复用、模块独立、可维护性和可扩展行较强、具有并发性；缺点是**不适用于交互性较强的应用**
- 调用/返回：构件之间存在互相调用的关系，一般是显式调用
  - 主程序/子程序
  - 面向对象：优点是模块化、封装、代码共享性好、易维护、可扩充性好；缺点是增加了对象之间的依赖关系
  - 层次结构：支持系统设计过程中的逐级抽象、可扩展性好、支持软件复用；缺点是不同层次之间耦合度高的系统很难实现
- 独立构件：构件之间是相互独立的，不存在显式调用，而是通过事件触发，异步执行
  - 进程通信
  - 事件驱动（隐式调用）：容易实现**并发处理和多任务**、可扩展性好、具有类层次结构、简化代码；缺点是因为是树形结构所以削弱了对系统计算的控制能力、各个**对象间的关系复杂**
- 虚拟机：自定义了一套规则供提供者使用，使用者基于规则来**灵活**开发构件
  - 解释器
  - 规则系统：适用场景为 DSS、人工智能、专家系统
- 仓库：以数据为中心，所有的操作都是围绕数据中心进行的
  - 数据库
  - 超文本
  - 黑板：适用场景为语音识别、知识推理
- 闭环控制：软件与硬件之间可以粗略的表示为一个反馈循环。适用场景为定速巡航、空调温度调节
- C2：通过连接件绑定在一起的按照一组规则运作的并行构件网络

### **质量属性**

- 性能
  - 指系统的响应能力，即要经过多长时间能对某个事件作出响应，或者在某段时间内系统所能处理的事件个数。如**响应时间、吞吐量**
  - **优先级队列、增加计算资源、减少计算开销、引入并发机制、采用资源调度**等
- 可用性
  - 是系统能够正常运行的时间比例，经常用**故障间隔时间**表示
  - **心跳、Ping/Echo、冗余、选举**
- 可靠性
  - 指软件系统在应用或系统错误面前，在意外或错误使用的情况下维持软件系统功能特性的基本能力。如 MTTF、MTBF、MTTR
  - 心跳、Ping/Echo、冗余、选举
  - 与可用性同时出现时选可用性
- 安全性
  - 是指系统在向合法用户提供服务的同时能够阻止非授权用户使用的企图或拒绝服务的能力。如保密性、完整性、不可抵赖性、可控性
  - **入侵检测、用户认证、用户授权、追踪审计**
- 可修改性
  - 指能够快速的以较高的性价比对系统进行变更的能力
  - 接口实现分离、抽象、信息隐藏
- 可变性
  - 指体系结构经扩充或变更而成为新的体系结构的能力
  - 与可修改性同时出现时选可修改性
- 功能性
  - 指系统所能完成所期望的工作的能力
- 互操作性
  - 指作为系统组成部分的软件不是独立存在的，经常与其他系统或自身环境相互作用

### 软件过程模型

- 瀑布模型
  - 从上一项开发活动接受该活动的工作对象作为输入
  - 实施该项活动完成对应的工作内容
  - 工作成果作为输出
  - 对工作成果进行评审，通过进行下一项，否则返回前一项
- 原型模型
  - 第一步就是创建一个快速原型，与客户讨论弄清楚当前系统的需求
  - 对用户的需求是动态响应、逐步纳入的
- 螺旋模型
  - 是一个演化过程模型
  - 将原型模型和瀑布模型结合起来
  - 四个阶段分别为：制定计划、风险分析、实施工程、客户评估
  - **强调了风险分析，适用于庞大复杂的高风险系统**
- V 模型
  - 每个步骤有对应的测试
  - 用于需求明确和需求变更不频繁的情况
- 增量模型
  - 首先开发核心模块功能，然后与用户确认，每次开发一部分功能，并于用户确认
  - 优先级最高的服务最先交付
  - **不利于模块划分**，难点在于如何将客户需求划分为多个增量
  - 与原型模型不同的是增量模型每个增量版本都是独立可操作的作品
- 敏捷模型
  - 核心思想是**适应性、以人为本、迭代增量**
- **统一过程模型 RUP**
  - 9 个核型工作流：业务建模、需求、分析与设计、实现、测试、部署、配置与变更管理、项目管理、环境
  - 特点：用例驱动、以体系结构为中心
  - 四个阶段
    - 初始阶段：定义最终产品视图和业务模型，并**确定系统范围**
    - 细化阶段：**设计及确定系统的体系结构**，制订工作计划及资源要求
    - 构造阶段：**构造产品并继续演进需求**、体系结构、计划直到产品提交
    - 移交阶段：把产品提交给**用户使用**
  - 4+1 视图模型
    - 用例视图，分析人员和测试人员关注
    - 逻辑视图，最终用户关注
    - 实现视图，程序员关注
    - 进程视图，系统集成人员关注
    - 部署视图，系统工程师关注

### 结构化的需求分析

- 结构化的特点：**自顶向下、逐步分解、面向数据**
- 三大模型及数据字典：**功能模型（数据流图）、行为模型（状态转换图）、数据模型（E-R 图）**
  - 数据流图 DFD：数据流、加工、数据存储、外部实体
    - 数据的流向必须经过加工
  - 状态转换图 STD：状态、事件
  - 实体联系图 ER：实体、联系
  - 数据字典：数据元素、数据结构、数据流、数据存储、加工逻辑、外部实体
    - 数据字典就是为数据流中的每个数据流、文件、加工以及组成数据流或文件的数据项作出说明

### 面向对象的需求分析

- 五个活动：认定对象、组织对象、描述对象间的相互作用、确定对象的操作、定义对象的内部信息
- 分析模型
  - 顶层架构图
  - 用例与用例图
  - 领域（分析）概念模型
- 设计模型
  - 软件体系结构图：包图表示
  - 用例实现图：交互图表示
  - 类图
  - 状态图：针对复杂对象
  - 活动图：描述流程化处理过程

### 统一建模语言 UML

- 可视化的建模语言，而非程序设计语言
- 结构包括**构造块（事物、关系、图）、规则和公共机制**
- 关系
  - 关联：没啥特殊的；实线
  - 组合：部分和整体，手和人；实线带菱形实心箭头
  - 聚合：部分和整体，大雁和雁群；实线带另菱形空心箭头
  - 依赖：一个事物的语义依赖于另一个事物的语义的变化而变化；虚线带实心三角箭头
  - 泛化：一般/特殊的关系，子类和父类；实线带空心三角箭头
  - 实现：一个类元指定了另一个类元保证的契约；虚线带空心三角箭头
- 静态图
  - 类图：展现一组对象、接口、协作和它们之间的关系
  - 对象图：展现某一时刻一组对象及它们之间的关系，为类图的快照
  - 用例图：展现一组用例、参与者以及它们之间的关系
  - 构件（组件）图：展现一组构件之间的组织和依赖
  - 部署图：展现物理模块的节点分布，通常一个节点包含一个或多个构件
- 动态图
  - 序列（顺序）图：描述以时间顺序组织的对象之间的交互活动
  - 通信（协作）图：强调参加交互对象的组织
  - 状态图：展现一个状态机，描述单个对象在多个用例中的行为，包括简单的状态和组合状态。转换可以通过事件触发器触发，事件触发后相应的监护条件会进行检查。
  - 活动图：一种特殊的状态图，展现了系统内从一个活动到另一个活动的流程

### 设计模式

- 创建型
  - 抽象工厂(Abstract Factory)：提供一个接口，可以创建一系列相关或互相依赖的对象，而**无需指定它们具体的类**
  - 构建器(Builder)：将一个复杂类的**表示与其构造相分离**，使得相同的构建过程能得出不同的表示
  - 工厂方法(Factory Method)：定义一个创建对象的接口，但**由子类决定需要实例化哪一个类**，使得子类实例化过程推迟
  - 原型(Prototype)：用原型实例指定创建对象的类型，并且**通过拷贝这个原型来创建新的对象**
  - 单例(Singleton)：保证**一个类只有一个实例**，并且提供一个访问它的全局访问点
- 结构型
  - 适配器(Adapter)：将一个类的接口**转换**成用户希望得到的另一种接口，它是原本不**兼容**的接口得以协同工作
  - 桥接(Bridge)：将类的**抽象部分和它的实现部分分离**开来，使得它们可以独立变化
  - 组合(Composite)：将对象组合成**树形结构**以表示“整体-部分”的层次结构，使得用户对单个对象和组合对象的使用具有一致性
  - 装饰(Decorator)：动态的给一个对象**添加一些额外的职责**。提供了用子类扩展功能的一个灵活的替代
  - 外观(Facade)：定义一个**对外统一的高层接口**，为子系统中的一组接口提供一个一致的外观，从而简化了该子系统的使用
  - 享元(Flyweight)：提供支持大量**细粒度对象共享**的有效方法
  - 代理(Proxy)：为其他对象提供一种**代理控制**这个对象的访问
- 行为型
  - 职责链(Chain of Responsibility)：传递请求、职责链接
  - 命令(Command)：日志记录、可撤销
  - 解释器(Interpreter)：解释器、虚拟机
  - 迭代器(Iterator)：顺序访问、不暴露内部
  - 中介者(Mediator)：不直接引用
  - 备忘录(Memento)：保存、恢复
  - 观察者(Observer)：通知、自动更新
  - 状态(State)：状态改变行为
  - 策略(Strategy)：算法替换
  - 模版方法(Template Method)：算法骨架、步骤延迟、子类实现
  - 访问者(Visitor)：数据和操作分离

## 案例

### 考点分析

1. **架构**: 2023 之前案例的第一题是稳定的考架构风格+质量属性送分，教材改版后应该是下篇的八大架构中出题了，所以新版教材中的**八大架构的特点和架构图**是重中之重。
2. **建模（需求分析）**：结构化建模（需求分析）和面向对象的建模（需求分析）轮流来，结构化建模主要考**数据流图+数据字典**，面向对象的建模主要考**用例图、类图、活动图、状态图**。
3. **数据库**：主要是数据库实际应用中面临的问题，基本和数据库面试题差不多，还比较喜欢考 Redis。
4. Web：偏理论的居多，主要是 Java 方向，撞到了枪口上再选。
5. 嵌入式/新技术：尽量不选。

总体来说的选题思路：架构强制选，建模必选，数据库 > WEB，嵌入式/新技术不要选。

### 八大架构

### 建模（需求分析）

#### 结构化建模（需求分析）

- 结构化特点：**自顶向下，逐步分解，面向数据**。
- 三大模型：功能模型（数据流图）、行为模型（状态转换图）、数据模型（E-R 图）以及数据字典。
- 数据字典：数据字典是在 DFD 的基础上，对 DFD 中出现的所有命名元素都加以定义，使得每个图形元素的名字都有一个确切的解释。DFD 和数据字典等工具相配合，就可以从图形和文字两个方面对系统的逻辑模型进行完整的描述。是所有人员工作的依据，统一的标准。它可以确保数据在系统中的完整性和一致性。数据字典中一般有 6 类条目，分别是数据元素、数据结构、数据流、数据存储、加工逻辑和外部实体。不同类型的条目有不同的属性需要描述。

![结构化建模](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.13lle6ur3n.webp)

##### **功能模型（数据流图）**

- 作用：分析阶段，建立系统的功能模型，从而完成需求分析。设计阶段，为模块划分与模块之间接口设计提供依据。
- 数据流：由一组固定成分的数据组成，表示数据的流向。在 DFD 中，数据流的流向必须经过加工。
- 加工：描述了输入数据流到输出数据流之间的变换。
  - 有输入但是没有输出，称之为“黑洞”。
  - 有输出但没有输入。称之为“奇迹”。
  - 输入不足以产生输出，我们称之为“灰洞”。
- 数据存储：用来存储数据。
- 外部实体（外部主体）：是指存在于软件系统之外的人员或组织，它指出系统所需数据的发源地（源）和系统所产生的数据的归宿地（宿）。
- 数据流图的平衡原则
  - 父图（上层数据流图）与子图（下层数据流图）平衡：
    - 个数一致：两层数据流图中的数据流个数一致
    - 方向一致：两层数据流图中的数据流方向一致
  - 子图内部的平衡
    - 黑洞：加工只有输入没有输出
    - 奇迹：加工只有输出没有输入
    - 灰洞：加工中输入不足以产生输出

![数据流图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.4uaqzemrck.webp "数据流图")
![分层数据流图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.pf5narre5.webp "分层数据流图")

##### 数据模型（E-R 图）

- 作用
  - 数据建模与抽象：E-R 图帮助数据库设计师从现实世界中抽象出数据实体和它们之间的关系，将复杂的现实情况转化为易于理解和表达的图形化结构。通过 E-R 图，设计师可以更好地捕捉数据模型的本质，从而准确地定义数据结构。
  - 数据可视化：E-R 图可视化了数据实体、属性和关系之间的联系，使得数据库设计更加直观和易于沟通。设计师和利益相关者可以通过 E-R 图更容易地理解数据库的结构和组织，从而减少沟通误差。
  - 数据规范化：E-R 图可以帮助设计师进行数据规范化，将数据库设计转化为满足数据库范式要求的合理结构。数据规范化是数据库设计的重要原则，有助于减少数据冗余和提高数据的一致性。
  - 数据库系统设计指导：E-R 图是数据库系统设计的蓝图，为开发人员提供了关于数据库结构和关系的指导，从而帮助他们更好地实现数据库系统。
- 用 E-R 图来描述概念数据模型，世界是由一组称作实体的基本对象和这些对象之间的联系构成的。
- 在 E-R 模型中，使用椭圆表示属性（一般没有）、长方形表示实体、菱形表示联系，联系的两端要填写联系类型。
- E-R 模型转关系模型，每个实体都对应一个关系模式；联系分为三种：
  - 1:1 联系中，联系可以放到任意的两端实体中，作为一个属性（要保证 1:1 的两端关联），也可以转换为一个单独的关系模式。
  - 1:N 的联系中，联系可以单独作为一个关系模式，也可以在 N 端中加入 1 端实体的主键。
  - M:N 的联系中，联系必须作为一个单独的关系模式，其主键是 M 和 N 端的联合主键。

![E-R 图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.67xa3i9gk5.webp "E-R 图")
![E-R 图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.92py9avjcu.webp "E-R 图")

##### 行为模型（状态转换图）

![状态转换图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.969k6zvs4n.webp "状态转换图")

![状态转换图图例](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.8ojiierb1g.webp "状态转换图图例")

只能有一个初始状态，可以有多个中间状态和最终状态。中间状态的状态名必须要有，状态变量和行为可选。

#### 面向对象建模（需求分析）

面向对象的分析，是为了**确定问题域，理解问题**。包含五个活动：**认定对象、组织对象、描述对象间的相互作用、确定对象的操作、定义对象的内部信息**。

![面向对象需求建模](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.9nzlvqaym5.webp "面向对象需求建模")

面向对象的分析模型主要由**顶层架构图、用例与用例图、领域概念模型**构成；
面向对象的设计模型则包含**以包图表示的软件体系结构图、以交互图表示的用例实现图、完整精确的类图、针对复杂对象的状态图和用以描述流程化处理过程的活动图**等。

![面向对象的分析模型和设计模型](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.3rb1opx9su.webp "面向对象的分析模型和设计模型")

UML（统一建模语言）：是一种**可视化的建模语言，而非程序设计语言**，支持从需求分析开始的软件开发的全过程。
从总体上来看，UML 的结构包括**构造块、规则和公共机制**三个部分。

1. 构造块。UML 有三种基本的构造块，分别是事物（thing）、关系 （relationship）和图（diagram）。事物是 UML 的重要组成部分，关系把事物紧密联系在一起，图是多个相互关联的事物的集合。
2. 公共机制。公共机制是指达到特定目标的公共 UML 方法。
3. 规则。规则是构造块如何放在一起的规定。

UML 的关系：

1. 依赖：**一个事物的语义依赖于另一个事物的语义的变化而变化**。
2. 关联：是一种结构关系，描述了一组链，链是对象之间的连接。分为**组合和聚合，都是部分和整体的关系**，其中组合事物之间关系更强。两个类之间的关联，实际上是两个类所扮演角色的关联，因此，两个类之间可以有多个由不同角色标识的关联。
3. 泛化：一般/特殊的关系，**子类和父类**之间的关系
4. 实现：一个类元指定了另一个类元保证执行的契约。

![UML 的关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.7w6n0u14yp.webp "UML 的关系")

![UML 图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.3d4lxuyl1s.webp "UML 图")

##### **用例图**

静态图，展现了一组**用例、参与者以及它们之间的关系**。用例图中的参与者是人、硬件或其他系统可以扮演的角色；用例是参与者完成的一系列操作，用例之间的关系有**扩展、包含、泛化**。

![用例图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.839uw9z4ua.webp "用例图")

##### **类图**

静态图，为系统的静态设计视图，展现一组**对象、接口、协作和它们之间的关系**。

![类图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.73trj3qpn3.webp "类图")

##### **状态图**

动态图，展现了一个状态机，描述**单个对象在多个用例中的行为**，包括简单状态和组合状态。转换可以通过**事件触发器**触发，事件触发后相应的**监护条件**会进行检查。状态图中转换和状态是两个独立的概念，如下：图中方框代表状态，箭头上的代表触发事件，实心圆点为起点和终点。

![状态图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.9kfzy162c4.webp "状态图")

##### **活动图**

动态图，是一种**特殊的状态图**，展现了在系统内**从一个活动到另一个活动的流程**。活动的分岔和汇合线是一条水平粗线。牢记下图中**并发分岔、并发汇合、监护表达式、分支、流**等名词及含义。每个分岔的分支数代表了可同时运行的线程数。活动图中能够并行执行的是在一个分岔粗线下的分支上的活动。

![活动图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.6wqjnoi1yu.webp "活动图")

##### 对象图

静态图，展现**某一时刻一组对象及它们之间的关系**，为类图的某一快照。在没有类图的前提下，对象图就是静态设计视图。

![对象图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.lvjpsx9jh.webp "对象图")

##### 序列/顺序图

动态图，是场景的图形化表示，描述了**以时间顺序组织的对象之间的交互活动**。有同步消息（进行阻塞调用，调用者中止执行，等待控制权返回，需要等待返回消息，用实心三角箭头表示），异步消息（发出消息后继续执行，不引起调用者阳塞，也不等待返回消息，由空心箭头表示）、返回消息（由从右到左的虚线箭头表示）三种。

![序列图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.1aot9tn8zy.webp "序列图")

##### 通信/协作图

动态图，即协作图，**强调参加交互的对象的组织**。

![通信图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.8ojiil9fjk.webp "通信图")

##### 构件图

静态图，为系统静态实现视图，**展现了一组构件之间的组织和依赖**。

![构件图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.2obcdv2csn.webp "构件图")

##### 部署图

静态图，为系统静态部署视图，部署图**物理模块的节点分布**。它与构件图相关，通常一个结点包含一个或多个构件。其依赖关系类似于包依赖，因此部署组件之间的依赖是单向的类似于包含关系。

![部署图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.1hs159fntw.webp "部署图")

#### SysML

SysML 是一种通用图形建模语言，用于指定，分析，设计和验证可能包括硬件，软件，信息，人员， 程序和设施的复杂系统。特别是，该语言提供了图形表示，其具有用于建模系统需求，行为，结构和参数的语义基础，用于与其他工程分析模型集成。

- SysML 比 UML 更好地表达系统工程语义（符号解释）。它减少了 UML 的软件偏差，并为需求管理和性能分析添加了两种新的图表类型：需求图和参数图。
- SysML 比 UML 更小，更容易学习。由于 SysML 删除了许多以软件为中心和无偿的构造，因此在图表类型（9 对 13）和总结构中测量的整体语言较小。
- SySML 和 UML 间存在交集，即 SysML 语言中的部分图是和 UML 中的相应图是一致的，例如用例图。同时，SysML 也有基于 UML 扩展而来的图，例如活动图。另外，还有一部分图是 SysML 所特有的，这些图与 UML 间没有关系，例如需求图。

##### 需求图

SysML提供了需求图 （Requirements Diagram）用于对**系统需求，以及需求与需求及其他元素的追湖关系**进行建模，而在UML中则没有需求图。

用例可以有效地捕获功能需求，但不适合表达非功能需求。将基于文本的需求合并到SysML中可有效适应各种需求。

![需求图](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.5fkelypgy8.webp "需求图") 

SysML规定了七个需求关系，使建模者能够将需求彼此关联以及与其他模型元素关联。这些关系包括定义需求层次结构、派生需求、满足需求、验证需求和细化需求的关系。然而，这些关系的语义并不是在形式上定义的，而是可以解释的。因此，有必要定义一些关于如何使用这些关系的启发式、指南和实践，以便有一个一致的模型。

1. 复合关系：复合需求可以包含需求层次结构中的子需求。复合需求可以声明系统应执行A和B，可以将其分解为系统应执行A和系统应进行B的子需求。
  ![复合关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.2vek9btwsg.webp) 
2. 派生关系：派生的需求通常对应于系统层次结构下一级的需求。一个简单的例子是车辆加速需求，该需求被分析以导出发动机动力等方面的需求。
  ![派生关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.8dwoph3vwq.webp) 
3. 细化关系：细化关系可用于描述如何使用模型元素或元素集进一步细化需求。例如，可以使用用例或活动图来细化基于文本的功能需求。或者，可以使用它来显示基于文本的需求如何细化模型元素。在这种情况下，可以使用一些阐述的文本来细化不太精细的模型元素。
  ![细化关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.4xucxe16xs.webp) 
4. 满足关系：满足关系描述了设计或实现模型如何满足一个或多个需求。然后，系统建模者可以指定旨在满足要求的系统设计元素。
  ![满足关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.45hhfnk1qw.webp) 
5. 验证关系：验证关系定义了测试用例或其他模型元素如何验证需求。在SysML中，测试用例或其他元素可以用作表示任何标准检验方法的通用机制，分析，演示或测试。
  ![验证关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.7p3yz88z5.webp) 
6. 复制关系：真正需要跨产品系列和项目重用需求。典型的方案是适用于产品和/或产品系列中重复使用的项目和要求的法定法规或合同要求。SysML引入了从属需求的概念。
  ![复制关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.8dwoph8srq.webp) 
7. 追溯关系：追溯关系提供了需求和任何其他模型元素之间的通用关系。追溯的语义不包含任何实际约束，因此非常弱。但是，追溯关系对于将需求与源文档相关联或在规范树中的规范之间建立关系可能很有用。
  ![追溯关系](https://jsd.cdn.zzko.cn/gh/orionpax1997/picx-images-hosting@master/image.7zq8ylzs0r.webp) 

### 数据库

## 论文

### 整体结构

- 摘要
- 项目背景
- 项目启动时间、岗位、职责、投入、建设周期、项目主要建设内容、技术架构
- **按题目，回应问题，分层结构**
- 开发时间、投入使用后的作用、反馈良好、系统建设困难克服困难、不懈努力后顺利交付

### 分层思路

- 层次式架构
  - 用户界面表示层
    - Vue：组件化、轻量级、双向数据绑定、学习成本低
    - Vuex：状态集中管理、组件间共享
    - Element UI：美观度、主题适合
  - 负载均衡控制层
    - RESTful：简单、松耦合、自文档
    - Spring Web
    - Ngnix：高性能、配置灵活
    - Spring Security
  - 业务逻辑处理层
    - 规则引擎
    - MVEL：可编译、性能
    - Microsoft Language Server Protocol：语法分析、自动完成、调试
    - Monaco Editor
    - 版本控制
  - 数据访问层
    - Redis：高可用、简单
    - DBMS：举例子
- 大数据架构 Kappa
  - 数据采集层
    - Kafka：高吞吐量处理大数据流、持久性、容错、社区支持
    - 数据标准化
    - 历史数据重放
  - 数据处理层
    - Flink：实时处理、事件处理、状态管理、精确一次处理确保数据处理不重复
    - 规则引擎
    - MVEL：可编译、性能
    - Microsoft Language Server Protocol：语法分析、自动完成、调试
    - Monaco Editor
    - 版本控制
    - 举例子
  - 数据存储层
    - Hadoop：分布式海量数据存储、高容错、可伸缩、安全、数据压缩、通过计算和分布式实现容错成本较低
    - Redis：高可用、简单
  - 数据展现层和安全监控层
    - Vue：组件化、轻量级、双向数据绑定、学习成本低
    - Vuex：状态集中管理、组件间共享
    - Element UI：美观度、主题适合
    - Zabbix：全面实时监控、报警、灵活、自动发现
- 面向服务的架构 SOA
  - 服务注册中心
    - ESB：集成了不同协议的不同服务，做了消息的转化、解释以及路由的工作，让不同的服务联通
  - 服务请求者
    - 客户端
  - 服务提供者
    - 各种类型不同实现方式的规则
    - 规则引擎
    - 数据同步
- 论系统建模方法及其应用
  - 结构化的特点：**自顶向下、逐步分解、面向数据**
  - 三大模型及数据字典：**功能模型（数据流图）、行为模型（状态转换图）、数据模型（E-R 图）**
  - 功能模型
    - 质控流程数据流向
  - 行为模型
    - 违规状态变换
  - 数据模型
    - 哪些实体和它们的联系
- 论软件系统架构风格
  - 5 大风格介绍
  - 规则系统
  - 仓库-数据库
  - 批处理
  - 层次化和面向对象
- 论软件架构的评估
  - 场景和需求收集
  - 体系结构视图和场景实现
  - 属性模型构造和分析
  - 折中
