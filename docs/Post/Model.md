# Model

总结一些常见的model，其实也可以将model看做是architecture。



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

比如[Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)中，**管理者**是operating system kernel，是task是process或thread的执行，它的执行者是CPU。

比如[celery](https://en.wikipedia.org/wiki/Celery_(software))中，task就是一个一个由用户定义的task function，执行者其实就是process了，**调度者**其实就是它的[task queue](https://en.wikipedia.org/wiki/Celery_(software))了，显然和OS kernel的调度者相比，它的调度策略是非常简单的。

关于调度者，参见：

- [Scheduling (computing)](https://en.wikipedia.org/wiki/Scheduling_(computing))



### context switch是task模型的必备操作

本节所描述的context switch是广义的context switch，而不是仅仅局限于process的context switch。因为taskmodel中存在着的并发执行的task，并且管理者会进行调度，所以就会发生context switch，比如：

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

比如：OS kernel对hardware的管理可以使用event-driven model来进行描述；OS kernl实现multitasking可以使用task model来进行描述。



## 总结

上述task model和event-driven model都是[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)。

> A **conceptual model** is a representation of a system, made of the composition of [concepts](https://en.wikipedia.org/wiki/Concept) which are used to help people [know](https://en.wikipedia.org/wiki/Knowledge), [understand](https://en.wikipedia.org/wiki/Understanding), or [simulate](https://en.wikipedia.org/wiki/Simulation) a subject the model represents. 

[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)是我们能够更加轻松地 [understand](https://en.wikipedia.org/wiki/Understanding)。