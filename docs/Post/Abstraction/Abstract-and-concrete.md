# Abstract(抽象) and concrete(具体)



## 双向

与abstract相对的是concrete，两者是**互相依存**的关系，存在着**转换**过程，在解决一个问题时，往往是**双向**的:

1) 由具体到抽象

2) 由抽象到具体



### 由具体到抽象

设计、理论研究过程中: 从具体的案例案例、问题中进行抽象，创造概念，形成理论，这个过程就是前面章节描述的"抽象"，在"创造抽象概念"章节中给出了具体的案例；本文不对此进行展开。



### 由抽象到具体

下面过程涉及由抽象到具体:

1) 实现抽象模型

2) 应用过程: 其实就是将**抽象模型**应用于实际的过程，这个过程会不断地将具体的案例输入到**抽象模型**中；

> NOTE: 关于**抽象模型**，参见[Abstraction-and-model](./Abstraction-and-model.md)。



## 实现抽象模型/conceptual model

作为software engineer，我们需要思考: 如何来**实现**通过设计/思考而创造的**抽象模型/conceptual model**。这是computer science中的核心问题；



### 一个抽象对应多个具体(concrete)/一个抽象(abstract)可以有多个实现(implementation)

抽象缘于具体，因此一个抽象可以有多个concrete/implementation；这就是典型的one-to-many(一对多)关系:

- **One/single**: abstraction
- **Many**: concrete/implementation

### Dispatch

我们将从abstract到concrete/implementation的过程称为**dispatch**，下面是对它的含义一些解读: 

1) 匹配: 为abstract**匹配**最合适的concrete/implementation

2) 路由: **路由**到最合适的concrete/implementation

3) 选择: 选择最合适的concrete/implementation

在wikipedia [Static dispatch](https://en.wikipedia.org/wiki/Static_dispatch) 中有如下描述:

> It is a form of *method dispatch,* which describes how a language or environment will select which implementation of a method or function to use.

#### Classification

下面的对它的一种简单的分类: 

1) dispatch to **concrete/implementation** **automatically**

自动进行dispatch

2) dispatch to **concrete/implementation** **manually**

手动进行dispatch



### Polymorphism: dispatch to concrete/implementation automatically

> NOTE: dispatch的需求促进了polymorphism的诞生；

"polymorphism"是属于"dispatch to concrete/implementation automatically"，它的这个特性，能够大大提升开发效率，是现代programming language的核心，关于此参见工程programming-language的`Theory\Programming-paradigm\Abstraction-and-polymorphism`章节；



### Examples

#### 一种programming language(abstraction)可以有多种实现

对于能够cross-plateform的programming language，designer往往是design to abstraction: abstract machine；不同plateform，按照programming language的标准，使用compiler/interpreter来实现programming language中的各种抽象，关于此参见

1) 龙书 [Chapter 7 Run-Time Environments](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/)

2) 工程programming language的 `Theory\Programming-language\Design-of-programming-language` 章节



#### 一个Interface(abstraction)有着多种不同的implementation(concrete)；

> TODO: 这能够描述computer science中的非常多的问题，因为很多都可以看做是interface。
>
> 需要添加interface的一些案例





### 参见

wikipedia [Abstract and concrete](https://en.wikipedia.org/wiki/Abstract_and_concrete)

[Instruction set architecture](https://en.wikipedia.org/wiki/Instruction_set_architecture)也可以作为此的一个例子。

[Abstract data type](https://en.wikipedia.org/wiki/Abstract_data_type)也可以作为此的一个例子，参见[Data abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)#Data_abstraction)。