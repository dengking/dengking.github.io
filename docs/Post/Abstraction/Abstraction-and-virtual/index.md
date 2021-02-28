# Abstraction and virtual

virtual是计算机科学中常常会出现的一个词，比如：

1、[Virtual memory](https://en.wikipedia.org/wiki/Virtual_memory)

2、[Virtual method](https://en.wikipedia.org/wiki/Virtual_function)

3、 virtual machine（abstraction machine，比如cppreference中描述的virtual machine）

4、 .....

## Why use virtual?

经过本文前面的分析，我们可以很快地知道：

1、virtual也是一种抽象，一种分层，这种分层所带来的价值就是解耦

2、它们都能够进行 透明，从而允许**实现**进行大量的optimization

3、进行了简化

在下面章节中也讨论了这个问题:

1、virtual memory，参见 工程Linux-OS的 `Kernel\Guide\Memory-management\Virtual-memory` 章节

2、tombstone，参见工程programming language的`Theory\Resource-management\Handle`章节

## Virtual is a kind of dynamic polymorphism

从目前接触的几种virtual来看，它们都是dynamic polymorphism，在工程programming-language的`Theory\Programming-paradigm\Abstraction-and-polymorphism\Polymorphism\Implementation\Static-and-dynamic-polymorphism`章节中讨论了实现dynamic polymorphism的策略: 

> Dynamic polymorphism的dispatch发生于runtime，显然是late binding；因此，如果采用这种实现方式，则它需要存储**abstraction**和所有的**candidate**、**concrete**、**implementation**之间的**映射关系**。
>
> 由于dispatch发生于runtime，则必然存在overhead。

下面是结合具体的案例来进行说明: 

1) 在[Paged virtual memory](https://en.wikipedia.org/wiki/Virtual_memory#Paged_virtual_memory)中，由[Page tables](https://en.wikipedia.org/wiki/Page_table)来记录映射关系：the data structures maps linear to physical addresses.

2) 在[Virtual function](https://en.wikipedia.org/wiki/Virtual_function)中，由[Dispatch table](https://en.wikipedia.org/wiki/Dispatch_table)来记录映射关系。

可以看到，它们都是使用一个table来记录映射关系的。



See also:

[Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))



### Thoughts

由virtual到physical。

由abstract到concrete。

比如：

- virtual address到physical address
- abstract machine到physical machine