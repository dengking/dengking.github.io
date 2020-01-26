# 引言

作为软件工程师，我们常常听到architecture（架构）这个词，并且有一个高端职位叫做architect（架构师）。软件或系统的架构为我们描述的系统的结构、组成部分、各部分之间的接口。下面我总结了我接触的架构：

# architecture of [computing system](https://en.wikipedia.org/wiki/Computing)

需要注意的是一般，提及[Computer architecture](https://en.wikipedia.org/wiki/Computer_architecture)，我们往往讨论的是诸如[Von Neumann architecture](https://en.wikipedia.org/wiki/Von_Neumann_architecture)、[Harvard architecture](https://en.wikipedia.org/wiki/Harvard_architecture)等描述computer硬件的架构，而本节所要描述的内容是从一个更加高的角度来看待[computing](https://en.wikipedia.org/wiki/Computing) system，正如[Computer hardware](https://en.wikipedia.org/wiki/Computer_hardware)中所描述的：

> The progression from levels of "hardness" to "softness" in [computer systems](https://en.wikipedia.org/wiki/Computer_system) parallels a progression of [layers of abstraction](https://en.wikipedia.org/wiki/Abstraction_layer) in computing.
>
> A combination of **hardware** and **software** forms a usable [computing](https://en.wikipedia.org/wiki/Computing) system.

显然，现代 [computing](https://en.wikipedia.org/wiki/Computing) system的整体架构的发展是收到计算机科学领域的[layers of abstraction](https://en.wikipedia.org/wiki/Abstraction_layer) （分层）思想的影响的，一个[computing](https://en.wikipedia.org/wiki/Computing) system可以认为有两层构成：

- **software** 
- **hardware** 

[Instruction set](https://en.wikipedia.org/wiki/Instruction_set_architecture)是software和hardware之间的接口。

现代[computing](https://en.wikipedia.org/wiki/Computing) system的运行是离不开operating system的，operating system所属的是software这一层，下面引入operating system来进行更加精细的分层。

## architecture of operating system

在[Operating system](https://en.wikipedia.org/wiki/Operating_system)中给出了一个典型的operating system的architecture如下：

| Operating systems                                            |
| ------------------------------------------------------------ |
| ![Operating system placement.svg](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Operating_system_placement.svg/165px-Operating_system_placement.svg.png) |

上图中User表示的是用户，不属于OS中，后面的讨论会将其忽视。

在[Advanced Programming in the UNIX® Environment, Third Edition](http://www.apuebook.com/toc3e.html)的1.2 UNIX Architecture节中给出了Architecture of the UNIX operating system，如下：

![](https://github.com/dengking/Unix-like-operating-system/blob/master/docs/architecture/architecture-of-the-Unix-operating-Sysem.png)

上述两个架构图都大体展示OS的architecture，两者都各有利弊，图一包含了hardware，但是忽视了各层之间的interface。图二则正好相反。所以将两者结合起来则正好，后面会按照图二中的表示方式，将interface也看做是一层。充当interface的layer作为它的上下两层之间的interface。



| upper layer |                            layer                             |   role    |      |
| ----------- | :----------------------------------------------------------: | :-------: | ---- |
| software    |                         application                          |           |      |
|             | [system calls](https://en.wikipedia.org/wiki/System_call)&library routines | interface |      |
|             |  [kernel](https://en.wikipedia.org/wiki/Kernel_(computing))  |           |      |
|             | [Instruction set](https://en.wikipedia.org/wiki/Instruction_set_architecture) | interface |      |
| hardware    | [hardware](https://en.wikipedia.org/wiki/Computer_hardware)  |           |      |





# architecture of compiler

## 中间表示
编译器分为前段和后端，中间表示理解前段与后端。也可以说中间表示是两者之间的接口。



# 协议栈
## [OSI model](https://en.wikipedia.org/wiki/OSI_model)



[Hierarchical internetworking model](https://en.wikipedia.org/wiki/Hierarchical_internetworking_model)



# 总结

分层，抽象，接口，这些是三个同义词。它们是贯穿了computer science和software engineering的思想

## 抽象层

[Abstraction layer](https://en.wikipedia.org/wiki/Abstraction_layer)





## [Multitier architecture](https://en.wikipedia.org/wiki/Multitier_architecture)



## 分层带来的价值

### [Separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)

### [Abstraction (computer science)](https://en.wikipedia.org/wiki/Abstraction_(computer_science))

### [Layer (object-oriented design)](https://en.wikipedia.org/wiki/Layer_(object-oriented_design))



### [Portability](https://en.wikipedia.org/wiki/Software_portability)

如

- [Diversity of operating systems and portability](https://en.wikipedia.org/wiki/Operating_system#Diversity_of_operating_systems_and_portability)



# [Solution stack](https://en.wikipedia.org/wiki/Solution_stack)