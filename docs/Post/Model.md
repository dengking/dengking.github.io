# 前言

总结一些常见的model，其实也可以将model看做是architecture。

# task model

一些关于task model的内容：

- [Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)
- [Task parallelism](https://en.wikipedia.org/wiki/Task_parallelism)
- [Task (computing)](https://en.wikipedia.org/wiki/Task_(computing))



使用task model的时候，需要考虑task是什么、task的执行者是什么、task的调度者是什么：

比如[Computer multitasking](https://en.wikipedia.org/wiki/Computer_multitasking)中，task是process或thread的执行，它的执行者是CPU，它的调度者是operating system kernel中的scheduler。

比如[celery](https://en.wikipedia.org/wiki/Celery_(software))中，task就是一个一个由用户调用的task function，执行者其实就是process了，调度者其实就是它的[task queue](https://en.wikipedia.org/wiki/Celery_(software))了。

关于调度者，参见：

- [Scheduling (computing)](https://en.wikipedia.org/wiki/Scheduling_(computing))



与task model相关的另外一个概念就是：task manager，比如[Task Manager (Windows)](https://en.wikipedia.org/wiki/Task_Manager_(Windows))。



# event-driven model

一些关乎event-driven model的内容：

- [Event (computing)](https://en.wikipedia.org/wiki/Event_(computing))

- [Event-driven programming](https://en.wikipedia.org/wiki/Event-driven_programming)

- [Event-driven architecture](https://en.wikipedia.org/wiki/Event-driven_architecture)

- [Event handler](https://en.wikipedia.org/wiki/Event_(computing)#Event_handler)

  

- [Interrupt](https://en.wikipedia.org/wiki/Interrupt)

- [Interrupt-driven](https://en.wikipedia.org/wiki/Interrupt)

- [Interrupt handler](https://en.wikipedia.org/wiki/Interrupt_handler)





# 使用event-driven模型和上述的task模型可以描述太多太多的software

