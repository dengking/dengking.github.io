# 分层思想

计算机科学领域的[layers of abstraction](https://en.wikipedia.org/wiki/Abstraction_layer)思想的可谓由来已久且影响深远，在计算机科学的方方面面我们都能够看到它的身影和影响，后面为了描述便利，将[layers of abstraction](https://en.wikipedia.org/wiki/Abstraction_layer)思想简称为**分层思想**。最能够体现**分层思想**的一个词是：hierarchy（层级），维基百科的[hierarchy](https://en.wikipedia.org/wiki/Hierarchy)对hierarchy的总结是非常详细的，非常值得一读，从中我们可以看到，hierarchy在各个学科中有着广泛的应用：

> Hierarchy is an important concept in a wide variety of fields, such as [philosophy](https://en.wikipedia.org/wiki/Philosophy), [mathematics](https://en.wikipedia.org/wiki/Mathematics), [computer science](https://en.wikipedia.org/wiki/Computer_science), [organizational theory](https://en.wikipedia.org/wiki/Organizational_theory), [systems theory](https://en.wikipedia.org/wiki/Systems_theory), and the [social sciences](https://en.wikipedia.org/wiki/Social_sciences) (especially [political philosophy](https://en.wikipedia.org/wiki/Political_philosophy)).

其实从这上诉论断中我们也可以倒推出：分层思想在各个学科中有着广泛的应用，其实如果往更深层次去思考的话，分层思想其实是一种结构化的思维，关于这个还需要进行一些阅读。

下面是我所总结的计算机科学的各个领域中分层的应用：

## architecture

作为软件工程师，我们常常听到architecture（架构）这个词，并且有一个高端职位叫做architect（架构师）。软件或系统的架构为我们描述的系统的结构、组成部分、各部分之间的接口。分层思想对architecture影响体现在各种各样的**层次化结构**，比如

### architecture of [computing system](https://en.wikipedia.org/wiki/Computing)

reference

### architecture of compiler

reference

#### 中间表示
编译器分为前段和后端，中间表示理解前段与后端。也可以说中间表示是两者之间的接口。





## [Communication protocol](https://en.wikipedia.org/wiki/Communication_protocol)

各种各样的通信协议可以说是最最能够体现分层思想的了，在[Communication protocol](https://en.wikipedia.org/wiki/Communication_protocol)的[Protocol design](https://en.wikipedia.org/wiki/Communication_protocol#Protocol_design)章节中就总结了协议涉及的思想：[Layering](https://en.wikipedia.org/wiki/Communication_protocol#Layering)。除此之外，参加：[Hierarchical internetworking model](https://en.wikipedia.org/wiki/Hierarchical_internetworking_model)。

下面列举了几个常见协议，它们都能非常好地体现了分层思想：

### [OSI model](https://en.wikipedia.org/wiki/OSI_model)

[OSI model](https://en.wikipedia.org/wiki/OSI_model)可以说是分层思想的最佳体现，下面是摘自[OSI model](https://en.wikipedia.org/wiki/OSI_model)：

> The **Open Systems Interconnection model** (**OSI model**) is a [conceptual model](https://en.wikipedia.org/wiki/Conceptual_model) that characterizes and standardizes the communication functions of a [telecommunication](https://en.wikipedia.org/wiki/Telecommunication) or computing system without regard to its underlying internal structure and technology. Its goal is the interoperability of diverse communication systems with standard [communication protocols](https://en.wikipedia.org/wiki/Communication_protocols). The model partitions a communication system into [abstraction layers](https://en.wikipedia.org/wiki/Abstraction_layer). The original version of the model had seven layers.
>
> A layer serves the layer above it and is served by the layer below it. 

上面这段话其实描述了**分层**所带来的好处：interoperability ，各层之间互相透明（隐藏内部结构和技术），通过约定好的[communication protocols](https://en.wikipedia.org/wiki/Communication_protocols)进行交互。

OSI model by [layer](https://en.wikipedia.org/wiki/Abstraction_layer)

|      |   [layer](https://en.wikipedia.org/wiki/Abstraction_layer)   |
| :--: | :----------------------------------------------------------: |
|  7   | [Application layer](https://en.wikipedia.org/wiki/Application_layer) |
|  6   | [Presentation layer](https://en.wikipedia.org/wiki/Presentation_layer) |
|  5   | [Session layer](https://en.wikipedia.org/wiki/Session_layer) |
|  4   | [Transport layer](https://en.wikipedia.org/wiki/Transport_layer) |
|  3   | [Network layer](https://en.wikipedia.org/wiki/Network_layer) |
|  2   | [Data link layer](https://en.wikipedia.org/wiki/Data_link_layer) |
|  1   | [Physical layer](https://en.wikipedia.org/wiki/Physical_layer) |



### [Internet protocol suite](https://en.wikipedia.org/wiki/Internet_protocol_suite)





## [Database abstraction layer](https://en.wikipedia.org/wiki/Database_abstraction_layer)

这段描述非常好：

> A **database abstraction layer** (**DBAL** or **DAL**) is an [application programming interface](https://en.wikipedia.org/wiki/Application_programming_interface) which unifies the communication between a computer application and [databases](https://en.wikipedia.org/wiki/Database) such as [SQL Server](https://en.wikipedia.org/wiki/MSSQL), [DB2](https://en.wikipedia.org/wiki/IBM_DB2), [MySQL](https://en.wikipedia.org/wiki/MySQL), [PostgreSQL](https://en.wikipedia.org/wiki/PostgreSQL), [Oracle](https://en.wikipedia.org/wiki/Oracle_database) or [SQLite](https://en.wikipedia.org/wiki/SQLite). 



## 以层次思想来思考

**层次思想**是计算机科学中的重要思想，它潜移默化地影响这计算机科学，在计算机科学中，如果我们以**层次思想**来思考，来分析各种系统，则问题会变得清晰。

### 问题出现在哪个层次

在多层次中，当出现问题是，就需要进行这样的考虑。

### 不同层次相互借用概念

当我们站在计算机系统的不同层次来思考，我们会发现不同层次之间会存在着大量的相互概念借用。比如：

#### Example one

不同层次描述本质上非常类似的事务有着不同的说法，比如在《[How-OS-run-01-OS-kernel-is-event-driven](https://github.com/dengking/Unix-like-operating-system/docs/Kernel/book-Understanding-the-Linux-Kernel/Summary/How-OS-run-01-OS-kernel-is-event-driven.md)》中鄋总结的：

我们惊喜的发现站在计算机科学的不同的层次来描述本质上非常类似的事务有着不同的说法，下面对此进行了对比：

| Hardware                                                     | Software                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Interrupt-driven](https://en.wikipedia.org/wiki/Interrupt)  | [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture) / [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming) |
| [Interrupt](https://en.wikipedia.org/wiki/Interrupt)         | [Event (computing)](https://en.wikipedia.org/wiki/Event_(computing)) |
| [Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)/[Interrupt service routine](https://en.wikipedia.org/wiki/Interrupt_handler) | [Event handler](https://en.wikipedia.org/wiki/Event_(computing)#Event_handler)/[Callback function](https://en.wikipedia.org/wiki/Callback_(computer_programming)) |

各种interrupt就是所谓的event。

#### Example two

linux的[epoll](https://en.wikipedia.org/wiki/Epoll)的[triggering mode](https://en.wikipedia.org/wiki/Epoll#Triggering_mode)借用了[Interrupt](https://en.wikipedia.org/wiki/Interrupt)的[triggering methods](https://en.wikipedia.org/wiki/Interrupt#Triggering_methods)概念。

#### Example three

在[Understanding.The.Linux.kernel.3rd.Edition](https://www.oreilly.com/library/view/understanding-the-linux/0596005652/)的Chapter 4. Interrupt定义了Synchronous interrupt的概念，它是Hardware层的概念，在OS层，它对应的是[Signal](http://en.wikipedia.org/wiki/Signal_(IPC))。



正在不同的层次来看待计算机科学=》不同层次相互借用相同概念-》不同层次相互透明（隐藏内部细节），通过接口来进行交互

### 不同层次使用不同语言

不同层次使用不同的语言：[Very high-level programming language](https://en.wikipedia.org/wiki/Very_high-level_programming_language)、高级编程语言（[High-level programming language](https://en.wikipedia.org/wiki/High-level_programming_language)）、低级编程语言（[Low-level programming language](https://en.wikipedia.org/wiki/Low-level_programming_language)）



#### 不同层次的语言之间的转换

比如compiler就是执行这个目的的。

## 总结

分层，抽象，接口，这些是三个同义词。它们是贯穿了computer science和software engineering的思想

### 抽象层

[Abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)



### 分层带来的价值

#### [Separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)

#### [Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))

#### [Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))



#### [Portability](https://en.wikipedia.org/wiki/Software_portability)

如

- [Diversity of operating systems and portability](https://en.wikipedia.org/wiki/Operating_system#Diversity_of_operating_systems_and_portability)

抽象层带来移植性

#### 分层带来安全

在[Kernel (operating system)](https://en.wikipedia.org/wiki/Kernel_(operating_system))中有这样的描述：

> [kernel space](https://en.wikipedia.org/wiki/Kernel_space). [user space](https://en.wikipedia.org/wiki/User_space). 
>
> This separation prevents user data and kernel data from interfering with each other and causing instability and slowness, as well as preventing malfunctioning application programs from crashing the entire operating system.

分层带来隔离，进而带来安全

#### 分层带来[modularity](https://en.wikipedia.org/wiki/Modular_programming)

在[Kernel (operating system)](https://en.wikipedia.org/wiki/Kernel_(operating_system))中有这样的描述



## 分层与栈、pipeline

一般，会将按照分层设计的系统称为栈，比如协议栈。有时候也会称为pipeline

### [Solution stack](https://en.wikipedia.org/wiki/Solution_stack)



## virtual

virtual是计算机科学中常常会出现的一个词，比如：

- [Virtual memory](https://en.wikipedia.org/wiki/Virtual_memory)
- [Virtual method](https://en.wikipedia.org/wiki/Virtual_function)

经过本文前面的分析，我们可以很快地知道：virtual也是一种抽象，一种分层，这种分层所带来的价值就是解耦。下面以virtual address来进行说明：

process在运行的时候使用virtual memory address，由OS根据page table将virtual address翻译为physical address；与process直接使用physical address相比，这种设计多添加了一层：转换层。这种设计带来的价值是：它解耦了process的page和page的存储位置，具体来讲就是按照这种设计，page既可以位于RAM，也可以位于disk，而如果直接使用physical address的话，则process的page只能够位于RAM中。所以可以看出，virtual address解耦了process的page和page的存储位置。

在[Paged virtual memory](https://en.wikipedia.org/wiki/Virtual_memory#Paged_virtual_memory)中，由[Page tables](https://en.wikipedia.org/wiki/Page_table)来记录映射关系：the data structures maps linear to physical addresses.

在[Virtual function](https://en.wikipedia.org/wiki/Virtual_function)中，由[Dispatch table](https://en.wikipedia.org/wiki/Dispatch_table)来记录映射关系。

这种一对多是需要一个table来记录映射关系的。

