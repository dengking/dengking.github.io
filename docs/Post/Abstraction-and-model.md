# Abstraction and model

[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)：

> A **conceptual model** is a representation of a system, made of the composition of [concepts](https://en.wikipedia.org/wiki/Concept) which are used to help people [know](https://en.wikipedia.org/wiki/Knowledge), [understand](https://en.wikipedia.org/wiki/Understanding), or [simulate](https://en.wikipedia.org/wiki/Simulation) a subject the model represents. 

[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model) 是对concept（通过abstraction创建的）和其relation的描述（其实它本身就是一个抽象的过程），它是对原理的描述，它没有达到实现层面，它指导着实现。在计算机科学的各个领域，有着非常多著名的[conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)。其实我们可以回顾学习生涯，教材往往是先从理论模型（其实就是概念模型）开始讲起，后面再来讲述实现，因为理论模型剔除了很多细节，而抽象出来最最本质的内容，易于理解，也就是[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)使我们能够更加轻松地 [understand](https://en.wikipedia.org/wiki/Understanding)。



本节总结一些常见的model。

## Task model

一些关于task model的内容：

- [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)
- [Task parallelism](https://en.wikipedia.org/wiki/Task_parallelism)
- [Task (computing)](https://en.wikipedia.org/wiki/Task_(computing))

在task model中，往往有**管理者**（manager）的角色，它负责**控制**整个系统：

- 调度task，具备**调度者**的角色
- 监控task，如对task的resource usage进行监控，具备**监控者**的角色

用户可以向manager请求创建task、操作task等。



使用task model的时候，需要考虑的一些问题：

- task是什么
- **管理者**是什么
- task的**执行者**是什么

下面使用task model来描述一些系统：

- [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)中，**管理者**是operating system kernel，是task是process或thread的执行，它的执行者是CPU。

- [celery](https://en.wikipedia.org/wiki/Celery_(software))中，task就是一个一个由用户定义的task function，执行者其实就是process了，**调度者**其实就是它的[task queue](https://en.wikipedia.org/wiki/Celery_(software))了，显然和OS kernel的调度者相比，它的调度策略是非常简单的。

关于调度者，参见：

- [Scheduling (computing)](https://en.wikipedia.org/wiki/Scheduling_(computing))



### Context switch是task模型的必备操作

本节所描述的context switch是广义的context switch，而不是仅仅局限于process的context switch。因为task model中存在着的并发执行的task，并且管理者会进行调度，所以就会发生context switch，比如：

- git branch，[Frictionless Context Switching](https://git-scm.com/about)

所以，context switch是task模型的必备操作。



与task model相关的另外一个概念就是：task manager，比如[Task Manager (Windows)](https://en.wikipedia.org/wiki/Task_Manager_(Windows))。



## Event-driven model

一些关乎event-driven model的内容：

- [Event (computing)](https://en.wikipedia.org/wiki/Event_(computing))

- [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming)

- [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)

- [Event handler](https://en.wikipedia.org/wiki/Event_(computing)#Event_handler)

  

- [Interrupt](https://en.wikipedia.org/wiki/Interrupt)

- [Interrupt-driven](https://en.wikipedia.org/wiki/Interrupt)

- [Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)





## 使用event-driven model和上述的task model可以描述太多太多的software

比如：OS kernel对hardware的管理可以使用event-driven model来进行描述；OS kernel实现multitasking可以使用task model来进行描述。



## See also

- [Database model](https://en.wikipedia.org/wiki/Database_model)
- [Data model](https://en.wikipedia.org/wiki/Data_model)



