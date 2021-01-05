# Unit

"unit"的意思是“单位”，本文对各种unit进行总结。

## Unit and atomic

一般，最小的unit是atomic的，也就是最小的unit是不可分的，没有半个的概念。关于atomic，参见文章《Atomic》。

## Unit of user-defined action

本节标题中的“unit of user-defined action”是我在阅读龙书[Chapter 7.2 Stack Allocation of Space](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/7.2-Stack-Allocation-of-Space/)时遇到的，原文如下：

> Almost all compilers for languages that use procedures, functions, or methods as units of user-defined actions manage at least part of their run-time memory as a stack. 

“action”的意思是“动作”、“运行”、“执行”，“unit of user-defined action”所强调的是运行。受[分层思想](https://dengking.github.io/Post/Abstraction/Glossary#分层思想)的影响，我开始从不同的层次来对比分析，下面总结了各个层次的user-defined action。

### CPU的unit of user-defined action

CPU的unit of user-defined action是[instruction](https://en.wikipedia.org/wiki/Instruction_set_architecture#Instructions)，也可以说CPU的执行单位是[instruction](https://en.wikipedia.org/wiki/Instruction_set_architecture#Instructions)。软件工程师一般不会直接使用[instruction](https://en.wikipedia.org/wiki/Instruction_set_architecture#Instructions)，往往是由compiler将高级语言编写的program翻译为对应的machine language的program。



### Programming language的unit of user-defined action

Programming language（部分）的unit of user-defined action是statement。

维基百科[Statement](https://en.wikipedia.org/wiki/Statement_(computer_science))： 

> In [computer programming](https://en.wikipedia.org/wiki/Computer_programming), a **statement** is a syntactic unit of an [imperative](https://en.wikipedia.org/wiki/Imperative_programming) [programming language](https://en.wikipedia.org/wiki/Programming_language) that expresses some action to be carried out. A program written in such a language is formed by a sequence of one or more statements. A statement may have internal components (e.g., [expressions](https://en.wikipedia.org/wiki/Expression_(computer_science))).

我们在进行编程的时候，使用statement来描述程序的运行逻辑，显然programming language的unit of user-defined action就是statement。

由编译器将statement翻译为instruction，一个statement可能对应多条instruction。

### Process/thread的unit of user-defined action

现代OS中，thread是调度单位，如果不进行multi-thread programming的话，则process只有一个thread，所以标题中也包含了process和thread（关于此，参见工程[Linux-OS](https://dengking.github.io/Linux-OS/)的文章[Process model](https://dengking.github.io/Linux-OS/Kernel/Guide/Linux-OS's-multitasking/01-Process-model/)）。

Thread的unit of user-defined **action**是什么？读者可以思考一下。

需要注意的是，当我们询问这个问题的时候，我们是站在Process层，而不是站在CPU层，所以答案肯定是比instruction更加大（或者说是“高级”）的一个unit（单位）。其实读者即使回到的是instruction，也不能判定你是错的，因为我们的程序最终肯定是需要被编程成machine language program才能够由CPU来执行，但是显然这个答案不是最准确的。

答案是：[函数](https://en.wikipedia.org/wiki/Subroutine)。

这个问题的答案其实在本节标题中已经给出了。

对于这个答案是不需要进行专业、深入的解释，因为这是规定，这是计算机科学发展多年形成的事实，当然这样做的背后肯定有着非常多的原因，在此我们不去追究，如果读者感兴趣，参见[Subroutine](https://en.wikipedia.org/wiki/Subroutine)。下面对这个答案进行一些非专业的解释：

需要注意的是所问的是“**action**”，即**运行**，在各种高级语言的程序，我们是通过**调用函数**来进行**运行**的，一个函数只有被调用，它的函数体中的statement才能够被执行，高级语言程序中，是无法单独执行一个statement的，一个statement只有置入一个function中，才可能被执行到，所以thread的unit of user-defined action是函数。

Process的入口是[main function](https://en.wikipedia.org/wiki/Entry_point)，然后该函数中的语句被依次执行，这说明thread的unit of user-defined action是函数。

函数的另外一个名称是“**callable unit**”，“callable unit”，其实这也说明了它是thread的unit of user-defined action。

[`pthread_create`](http://man7.org/linux/man-pages/man3/pthread_create.3.html)的入参`start_routine`是一个函数指针（线程执行函数），这说明thread的unit of user-defined action是函数。

Linux OS的 [`clone`](http://man7.org/linux/man-pages/man2/clone.2.html)的入参`fn`是一个函数指针，这说明thread的unit of user-defined action是函数。

[`exec`](http://man7.org/linux/man-pages/man3/exec.3.html) 系列函数的参数`pathname`指定一个可执行文件，这个可执行文件的入口是main函数，其实这相当于上面的`pthread_create`和`clone`的入参是一个函数指针。

### 总结

一个函数是由多个statement组成，一个statement有多个instruction组成。thread的运行单位function显然对应了多个instruction。



### Linux OS kernel的unit of user-defined action

Linux OS kernel的unit of user-defined action是函数。

在工程[Linux-OS](https://dengking.github.io/Linux-OS/)的[Linux OS kernel is event-driven](https://dengking.github.io/Linux-OS/Kernel/Guide/Linux-OS's-interaction-with-the-hardware/Linux-OS-kernel-is-event-driven/)中，我们已经分析了：

> 基本上所有的hardware都是通过[interrupt](https://en.wikipedia.org/wiki/Interrupt)来通知OS kernel的，然后其对应的[Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)会被触发执行，也就是OS kernel是[interrupt-driven](https://en.wikipedia.org/wiki/Interrupt)的

[Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)本质上是函数。

关于此的另外一个例证是signal handler，signal handler本质上也是函数，参见[SIGNAL(7)](http://man7.org/linux/man-pages/man7/signal.7.html)。

参见[Linux-OS](https://dengking.github.io/Linux-OS/)工程的文章Conventions。



## CPU access memory的单位是[word](https://en.wikipedia.org/wiki/Computer_word)

参见工程[Hardware](https://dengking.github.io/Hardware/)的[Memory-alignment](https://dengking.github.io/Hardware/CPU/Memory-access/Memory-alignment/)章节。



## Thread是OS kernel调度的单位

维基百科[Thread (computing)](https://en.wikipedia.org/wiki/Thread_(computing))：

> In [computer science](https://en.wikipedia.org/wiki/Computer_science), a **thread** of execution is the smallest sequence of programmed instructions that can be managed independently by a [scheduler](https://en.wikipedia.org/wiki/Scheduling_(computing)), which is typically a part of the [operating system](https://en.wikipedia.org/wiki/Operating_system).

工程[Process-model](https://dengking.github.io/Linux-OS/)的[Process model](https://dengking.github.io/Linux-OS/Kernel/Guide/Linux-OS's-multitasking/01-Process-model/#process-model)

> OS是基于process的resource分配，基于[thread](https://en.wikipedia.org/wiki/Thread_(computing))的调度。



## [Object-oriented programming](https://en.wikipedia.org/wiki/Object-oriented_programming)中object是交互单位



## [Protocol data unit](https://en.wikipedia.org/wiki/Protocol_data_unit)



## Database transaction