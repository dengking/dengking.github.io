# Abstract(抽象) and concrete(具体)

与abstract相对的是concrete，两者是**互相依存**的关系，存在着**转换**过程，在解决一个问题时，往往是**双向**的。

### 双向

|              | 简介                                                         |
| ------------ | ------------------------------------------------------------ |
| 由具体到抽象 | 设计、理论研究过程中: 从具体的案例案例、问题中进行抽象，创造概念，形成理论，这个过程就是前面描述的"创造抽象概念" |
| 由抽象到具体 | 应用过程中: 将抽象概念/理论，应用于实际                      |



### 一个抽象可能有多个实现/一个抽象对应多个具体

这就是典型的one-to-many(一对多)关系。

### 由抽象到具体



#### Example

既然有抽象，肯定需要有对应的具体的实现，比如compiler就需要使用instruction来实现programming language中的各种抽象，参见龙书 [Chapter 7 Run-Time Environments](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/)。



### 参见

wikipedia [Abstract and concrete](https://en.wikipedia.org/wiki/Abstract_and_concrete)

[Instruction set architecture](https://en.wikipedia.org/wiki/Instruction_set_architecture)也可以作为此的一个例子。

[Abstract data type](https://en.wikipedia.org/wiki/Abstract_data_type)也可以作为此的一个例子，参见[Data abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science)#Data_abstraction)。