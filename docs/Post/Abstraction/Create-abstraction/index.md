# Create concept

我们需要不断地create concept。

## Create larger concept

当问题越来越复杂，需要考虑的问题越来越多，就需要进行更多的抽象，创造更大的概念，创造更加大的框架，来容纳不断扩展的、不断复杂的问题。引入更大的概念势必导致引入更多的[indirection](https://en.wikipedia.org/wiki/Indirection)。

必须要有足够强大的框架来满足不断地扩展 不断创造更加大的概念来解决，包容问题。



### Example

1、design pattern

关于此的一个典型的例子就是[Software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern)，在维基百科[Software design pattern#Practice](https://en.wikipedia.org/wiki/Software_design_pattern#Practice)中有这样的描述:

> In order to achieve flexibility, design patterns usually introduce additional levels of [indirection](https://en.wikipedia.org/wiki/Indirection), which in some cases may complicate the resulting designs and hurt application performance.

design pattern中一种典型的思想就是创造更大的抽象，引入更多的levels of indirection。

2、写书

在编写各个工程的内容过程中，有如下感悟: 要将computer science中的内容组织起来，需要不断地创造更加抽象的概念，来容纳更多的知识；

## Create good abstraction

"Create good abstraction"有着非常重要的价值，关于此的描述，我觉得最好的Book-Designing-Data-Intensive-Applications，这部分内容收录在了工程Parallel-computing的"Distributed-computing\Theory\Abstraction"章节。

### Some good abstraction in software engineering

在Book-Designing-Data-Intensive-Applications中，作者已经强调了创造抽象的思想，下面是我所总结的在software engineering中一些比较成功的abstraction:

| abstraction    | 说明                                              | 章节                                                         |
| -------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| stream         | stream-based IO、...                              | - 工程Linux-OS的`Programming\IO\IO-流派\Stream`章节 <br>- 工程programming language的`C-family-language\C++\Library\Standard-library\IO-library`章节 |
| iterator       | STL中的iterator                                   | 工程programming language的`C-family-language\C++\Library\Standard-library\STL\Iterator-library` |
| object         | OOP                                               | 工程programming language的`Theory\Programming-paradigm\Object-oriented-programming`章节 |
| transaction    | 非常成功的一个abstraction，在很多领域中都有着使用 |                                                              |
| Golang channel |                                                   |                                                              |
| ...            |                                                   |                                                              |

> NOTE: tag good abstraction



## Generalization of concept

将概念进行推广，放松某些限制，下面是一些例子：

- [constexpr – Generalized constant expressions](https://en.wikipedia.org/wiki/C++11#constexpr_%E2%80%93_Generalized_constant_expressions)



