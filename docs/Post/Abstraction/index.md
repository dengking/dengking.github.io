# Abstraction

> 注意：本文所讨论的[Abstraction](https://en.wikipedia.org/wiki/Abstraction)是广义的，而不仅仅局限于[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))。



## What is abstraction? 

> NOTE: 其实我们每天都在进行着抽象，但是如果问: 什么是抽象？很多人都会陷入"可意会而难言传"的境地；

维基百科[Abstraction](https://en.wikipedia.org/wiki/Abstraction)给出了Abstraction的大量描述，有些是比较难以理解，下面是我认为其中比较好的描述：

> **Abstraction** in its main sense is a conceptual process where general [rules](https://en.wikipedia.org/wiki/Rule_of_inference) and [concepts](https://en.wikipedia.org/wiki/Concept) are derived from the usage and classification of specific examples, literal ("real" or "[concrete](https://en.wikipedia.org/wiki/Abstract_and_concrete)") signifiers, [first principles](https://en.wikipedia.org/wiki/First_principle), or other methods.

这段话的简单来说是：抽象是 从"specific example"中，创建 [concepts](https://en.wikipedia.org/wiki/Concept) 和 general [rules](https://en.wikipedia.org/wiki/Rule_of_inference) 的过程。那何为concept呢？这个问题是比较“抽象”的，难以进行准确描述的，后面的 [创造抽象概念](#创造抽象概念) 章节会结合具体案例来进行说明。

> "An abstraction" is the outcome of this process—a concept that acts as a common noun for all subordinate（从属） concepts, and connects any related concepts as a *group*, *field*, or *category*.

这段话的意思和上面的意思类似，在 [创造抽象概念](#创造抽象概念) 章节，会结合具体实例对这段话所表述的意思进行详细分析。

> Conceptual abstractions may be formed by filtering the [information](https://en.wikipedia.org/wiki/Information) content of a [concept](https://en.wikipedia.org/wiki/Concept) or an observable [phenomenon](https://en.wikipedia.org/wiki/Phenomenon), selecting only the aspects which are relevant for a particular subjectively valued purpose. 

> The essence of abstractions is preserving information that is relevant in a given context, and forgetting information that is irrelevant in that context.
>
> – John V. Guttag

抽象是概括的过程，抽象是提取公共特征的过程，它所概括的、所提取的公共特征，可以使用 [concepts](https://en.wikipedia.org/wiki/Concept) 来进行表示(representation)，当然也有其它的表示方式。



## 创造抽象概念

通过创造抽象的 [concept](https://en.wikipedia.org/wiki/Concept)（概念）来使表述更加便利的做法是在各种学科非常普遍的，关于此的例子有：

### Kernel control path

在《[Understanding the Linux Kernel, 3rd Edition](https://dengking.github.io/Linux-OS/Kernel/Book-Understanding-the-Linux-Kernel/)》的[chapter 1.6.3. Reentrant Kernels](https://dengking.github.io/Linux-OS/Kernel/Book-Understanding-the-Linux-Kernel/Chapter-1-Introduction/1.6.3-Reentrant-Kernels/)中，作者创造了kernel control path概念来概括kernel中由system call由触发的kernel control path（后面简称为system call kernel control path）、由interrupt handler触发的kernel control path（后面简称interrupt handler kernel control path）以及后续随着kernel发展可能会新增的触发kernel control path。显然kernel control path概念概括了system call kernel control path、interrupt handler kernel control path的**common feature**（公共特征），如它们都能够被suspend、resume。

显然当一个表述中使用kernel control path的时候，我们就知道它可以是system call kernel control path、也可以是interrupt handler kernel control path，这就使我们的表述非常地便利。显然，system call kernel control path、interrupt handler kernel control path和kernel control path之间是[Is-a](https://en.wikipedia.org/wiki/Is-a)关系。



### [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)

在[Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)中创造了task概念，它表示的是computer能够并发执行的，它可以是process也可以是thread，具体是什么则由具体的实现而定。

### Book-Designing-Data-Intensive-Applications

在这本书中，作者反复强调了abstraction，可以说，其中对abstraction使用涵盖了所有我们需要掌握的abstraction思想。下面是一个简单的例子，在工程`Parallel-computing`的`Distributed-computing\Theory\Abstraction\Abstraction-in-distributed-computing.md`进行了详细的总结。

#### Data system

在Book-Designing-Data-Intensive-Applications的"CHAPTER 1Reliable, Scalable, and Maintainable Applications"中，创造了data system的概念。

> If that sounds painfully obvious, that’s just because these data systems are such a successful **abstraction**: we use them all the time without thinking too much. 

"data system"的实例有:

- databases

- caches

- search indexes

- ......

  

### Some abstraction in software engineering

在Book-Designing-Data-Intensive-Applications中，作者已经强调了创造抽象的思想，下面是我所总结的在software engineering中一些比较成功的abstraction:

| abstraction | 说明            | 章节                                                         |
| ----------- | --------------- | ------------------------------------------------------------ |
| stream      | stream-based IO | - 工程Linux-OS的`Programming\IO\IO-流派\Stream`章节 <br>- 工程programming language的`C-family-language\C++\Library\Standard-library\IO-library`章节 |
| iterator    | STL中的iterator | 工程programming language的`C-family-language\C++\Library\Standard-library\STL\Iterator-library` |
| object      | OOP             | 工程programming language的`Theory\Programming-paradigm\Object-oriented-programming`章节 |

### Everything is an object and everything is a file

在python中，有着everything in python is an object，显然，object是最大的抽象，是最最顶级的抽象。

在linux中，有着everything is a file，显然file是最大的抽象，是最最顶级的抽象。

### 总结

关于创造抽象概念的例子数不胜数，我们学习的所有concept其实都是抽象的结果。



## Conceptual/abstraction/theory model

> NOTE: 本节标题的含义是: 概念模型、抽象模型、理论模型

参见文章 [Abstraction-and-model](./Abstraction-and-model.md)。



## Abstract and concrete

与abstract相对的是concrete，两者是**互相依存**的关系，存在着**转换**过程，在解决一个问题时，往往是**双向**的，这个话题在文章 [Abstract-and-concrete](./Abstract-and-concrete.md) 中进行讨论。



## Abstraction在各个学科中的应用

Abstraction是科学的基础，它在各个学科中都有着广泛的应用，作为software engineer，我们重点关注的是"Abstraction in computer science"。



## Abstraction in computer science

Abstraction在computer science中有着深远的影响，本节将开始对此从多个方面进行剖析。

维基百科的[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))总结了计算机科学中的abstraction。虽然维基百科的[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))对计算机科学中的Abstraction有了不同的描述，但是我觉得计算机科学中的abstraction本质上和前面所述的广义的abstraction是相同的，即**创建concept的过程**。



### 描述抽象概念的语言

在computer science，我们需要考虑的是如何来描述concept。

Concept在计算机科学的不同领域有着不同的描述方式，比如：

1) 在 [object-oriented programming](http://en.wikipedia.org/wiki/Object-oriented_programming) 中，使用`class`来描述concept，concept之间的relation就转换为`class`之间的关系了。

2) 在 [Entity–relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model) 中，使用`entity`来描述concept。与此相关的概念有：[Relational model](https://en.wikipedia.org/wiki/Relational_model)、[Relational database](https://en.wikipedia.org/wiki/Relational_database)、[Relational algebra](https://en.wikipedia.org/wiki/Relational_algebra)。

连接上述两者的就是[Object-relational mapping](https://en.wikipedia.org/wiki/Object-relational_mapping)。

3) [Instruction set architecture](https://en.wikipedia.org/wiki/Instruction_set_architecture)是对 [computer](https://en.wikipedia.org/wiki/Computer) 的抽象，它描述了一个computer的功能，特性等，它使用instruction来描述。

另外一个更加常用的来描述抽象概念的是[interface (computing)](https://en.wikipedia.org/wiki/Interface_(computing))，即接口。

本质上来说，上述**描述方式**都是 [语言](../Language/Language.md) 。

> NOTE: 以abstraction来作为切入点描述abstraction在各个工程中的应用。



### Abstraction in software design

参见工程software-engineering的`Software-design\Principle\Abstraction`章节。



### Abstraction in programming language

参见工程programming-language的`Theory\Programming-paradigm\Abstraction`章节。



### Abstraction in distributed computing

参见工程`Parallel-computing`的`Distributed-computing\Theory\Abstraction`章节。



