# Abstraction and virtual

virtual是计算机科学中常常会出现的一个词，比如：

- [Virtual memory](https://en.wikipedia.org/wiki/Virtual_memory)
- [Virtual method](https://en.wikipedia.org/wiki/Virtual_function)
- virtual machine（abstraction machine，比如cppreference中描述的virtual machine）

经过本文前面的分析，我们可以很快地知道：virtual也是一种抽象，一种分层，这种分层所带来的价值就是解耦。下面以virtual address来进行说明：

process在运行的时候使用virtual memory address，由OS根据page table将virtual address翻译为physical address；与process直接使用physical address相比，这种设计多添加了一层：转换层。这种设计带来的价值是：它解耦了process的page和page的存储位置，具体来讲就是按照这种设计，page既可以位于RAM，也可以位于disk，而如果直接使用physical address的话，则process的page只能够位于RAM中。所以可以看出，virtual address解耦了process的page和page的存储位置。

在[Paged virtual memory](https://en.wikipedia.org/wiki/Virtual_memory#Paged_virtual_memory)中，由[Page tables](https://en.wikipedia.org/wiki/Page_table)来记录映射关系：the data structures maps linear to physical addresses.

在[Virtual function](https://en.wikipedia.org/wiki/Virtual_function)中，由[Dispatch table](https://en.wikipedia.org/wiki/Dispatch_table)来记录映射关系。

这种一对多是需要一个table来记录映射关系的。



See also:

[Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))



## thoughts

由virtual到physical。

由abstract到concrete。

比如：

- virtual address到physical address
- abstract machine到physical machine