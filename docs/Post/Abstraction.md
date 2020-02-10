# Abstraction

> 注意：本文所讨论的[Abstraction](https://en.wikipedia.org/wiki/Abstraction)是广义的，而不仅仅局限于[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))。

维基百科[Abstraction](https://en.wikipedia.org/wiki/Abstraction)给出了Abstraction的大量描述，有些是比较难以理解，下面是我认为其中比较好的描述：

> **Abstraction** in its main sense is a conceptual process where general [rules](https://en.wikipedia.org/wiki/Rule_of_inference) and [concepts](https://en.wikipedia.org/wiki/Concept) are derived from the usage and classification of specific examples, literal ("real" or "[concrete](https://en.wikipedia.org/wiki/Abstract_and_concrete)") signifiers, [first principles](https://en.wikipedia.org/wiki/First_principle), or other methods.

这段话的简单来说是：抽象是创建 [concepts](https://en.wikipedia.org/wiki/Concept) 和  [rules](https://en.wikipedia.org/wiki/Rule_of_inference) 的过程，那何为concept呢？这个问题是比较“抽象”的，难以进行准确描述的，后面的[创造抽象概念](#创造抽象概念)章节会结合具体案例来进行说明。

> "An abstraction" is the outcome of this process—a concept that acts as a common noun for all subordinate（从属） concepts, and connects any related concepts as a *group*, *field*, or *category*.

这段话的意思和上面的相同，在[创造抽象概念](#创造抽象概念)章节，会结合具体实例对这段话所表述的意思进行详细分析。

> Conceptual abstractions may be formed by filtering the [information](https://en.wikipedia.org/wiki/Information) content of a [concept](https://en.wikipedia.org/wiki/Concept) or an observable [phenomenon](https://en.wikipedia.org/wiki/Phenomenon), selecting only the aspects which are relevant for a particular subjectively valued purpose. 

> The essence of abstractions is preserving information that is relevant in a given context, and forgetting information that is irrelevant in that context.
>
> – John V. Guttag

抽象是概括的过程，抽象是提取公共特征的过程，它所概括的、所提取的公共特征，可以使用 [concepts](https://en.wikipedia.org/wiki/Concept) 来进行表示，当然也有其它的表示方式。

与abstract相对的是concrete，参见[Abstract and concrete](https://en.wikipedia.org/wiki/Abstract_and_concrete)

## 创造抽象概念

通过创造抽象的[concept](https://en.wikipedia.org/wiki/Concept)（概念）来使表述更加便利的做法是在各种学科非常普遍的，关于此的例子有：

### kernel control path

在《Understanding.The.Linux.kernel.3rd.Edition》的chapter 1.6.3. Reentrant Kernels中，作者定义了kernel control path概念来概括kernel中由system call由触发的kernel control path（后面简称为system call kernel control path）、由interrupt handler触发的kernel control path（后面简称interrupt handler kernel control path）以及后续随着kernel发展可能会新增的触发kernel control path。显然kernel control path概念概括了system call kernel control path、interrupt handler kernel control path的**common feature**（公共特征），如它们都能够被suspend、resume。

显然当一个表述中使用kernel control path的时候，我们就知道它可以是system call kernel control path、也可以是interrupt handler kernel control path，这就使我们的表述非常地便利。

显然，system call kernel control path、interrupt handler kernel control path和kernel control path之间是[Is-a](https://en.wikipedia.org/wiki/Is-a)关系。



### [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)

在[Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)中创造了task概念，它表示的是computer能够并发执行的，它可以是process也可以是thread，具体是什么则由具体的实现而定。



## Abstraction在各个学科中的应用

Abstraction是科学的基础，它在各个学科中都有着广泛的应用。



## Abstraction in computer science

Abstraction在computer science中有着深远的影响，本文将开始对此从多个方面进行剖析。

维基百科的[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))总结了计算机科学中的abstraction。虽然维基百科的[Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))对计算机科学中的Abstraction有了不同的描述，但是我觉得计算机科学中的abstraction本质上和前面所述的广义的abstraction是相同的，即创建concept的过程，在computer science，我们需要考虑的是如何来描述concept。

concept在计算机科学的不同领域有着不同的描述方式，比如：

在[object-oriented programming](http://en.wikipedia.org/wiki/Object-oriented_programming)中，使用`class`来描述concept，concept之间的relation就转换为`class`之间的关系了。

在[Entity–relationship model](https://en.wikipedia.org/wiki/Entity%E2%80%93relationship_model)，使用`entity`来描述concept。与此相关的概念有：[Relational model](https://en.wikipedia.org/wiki/Relational_model)、[Relational database](https://en.wikipedia.org/wiki/Relational_database)、[Relational algebra](https://en.wikipedia.org/wiki/Relational_algebra)。

连接上述两者的就是[Object-relational mapping](https://en.wikipedia.org/wiki/Object-relational_mapping)。

[Instruction set architecture](https://en.wikipedia.org/wiki/Instruction_set_architecture)是对 [computer](https://en.wikipedia.org/wiki/Computer) 的抽象，它描述了一个computer的功能，特性等。



### Abstraction and [Object-oriented programming](http://en.wikipedia.org/wiki/Object-oriented_programming)

思考这样的一个问题：如何使用面向对象方式来描述上述kernel control path概念和task概念？

使用`class`来描述[concept](https://en.wikipedia.org/wiki/Concept)，这几个[concept](https://en.wikipedia.org/wiki/Concept)之间是[Is-a](https://en.wikipedia.org/wiki/Is-a)关系，那么可以使用inheritance，下面是一个`c++`实现的demo：

```c++
class KernelControlPath
{
    
}
	

class SystemCallKernelControlPath public: KernelControlPath
{
    
}

class InterruptKernelControlPath public: KernelControlPath
{
    
}

```

kernel control path的一个**特征**就是它能够被suspend、resume，使用面向对象的方式来进行描述就是：

```c++
void suspend(KernelControlPath& kernel_control_path)
{
    
}
	

void resume(KernelControlPath& kernel_control_path)
{
    
}
```

面向对象的[Polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science))（多态性）表明`suspend`和`resume`的入参可以为`SystemCallKernelControlPath`、`InterruptKernelControlPath`类型的对象，这其实就体现了：

> 当一个表述中使用kernel control path的时候，我们就知道它可以是system call kernel control path、也可以是interrupt handler kernel control path



```python
class Task:
	pass

class ProcessTask:
	pass

class ThreadTask:
	pass
```



在计算机科学中存在与上述抽象概念类似的做法：

父类是子类的抽象，接口是抽象

[Virtual function](https://en.wikipedia.org/wiki/Virtual_function)

[Interface (computing)](https://en.wikipedia.org/wiki/Interface_(computing))

[Abstract type](https://en.wikipedia.org/wiki/Abstract_type)

### 抽象与实现

[Instruction set architecture](https://en.wikipedia.org/wiki/Instruction_set_architecture)也可以作为此的一个例子。

[Abstract data type](https://en.wikipedia.org/wiki/Abstract_data_type)也可以作为此的一个例子，参见[Data abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)#Data_abstraction)。



### Abstraction and architecture

abstraction在architecture领域的直接体现就是分层思想，不同层就是一种抽象，分层带来解耦，这在《Philosophy-level.md》中描述

#### [Abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)

#### [Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))



### Conceptual model

Conceptual model则是对concept和其relation的描述，它没有达到实现层面，这在《Model.md》中描述，还需要扩展的model有：

- [Database model](https://en.wikipedia.org/wiki/Database_model)
- [Data model](https://en.wikipedia.org/wiki/Data_model)


