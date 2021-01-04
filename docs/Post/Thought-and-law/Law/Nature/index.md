# Nature/abstraction

## 观点

本文标题"nature"的含义是"本质"。本文的观点是: 探寻问题的本质，对于本质上相同的问题，可以使用相同的技术来进行实现，使用相同的model来进行描述。

### draft

在本质上相同的问题、追寻相同的目标、具备相同的结构，可以使用相同的技术、相同的思想、相同的概念、相同的algorithm；这就出现了同一个概念在不同层次、领域的相互借用；同一技术在不同层次、领域的相互借用；同一model可以使用于不同层次、领域；

> NOTE: model

### draft

同一思想/技术在computer science各个领域中的运用，与此相关的是: 一些model可以用于computer science的各个领域，比较典型的是consistency model；同一个概念在computer science的各个领域中被用不同的language来进行描述；

我是在阅读 https://en.wikipedia.org/wiki/Speculative_execution 时，其中的一段话 "This approach is employed in a variety of areas "给出的提示

### draft

在不同的层级、范围都要考虑看似相同的问题，比如在distributed computing、DBMS中，都需要考虑原子性，这就要求建立模型，它们的实现方式是可以相互借鉴的。

## Example

下面是一些example。

### 使用asynchronous programming来optimization

这是为了**追寻相同的目标**(optimization)，而使用类似的技术(asynchronous programming)的例子。

asynchronous/non-blocking operation: 启动，不阻塞主调线程/main loop，下面是一些例子:
1) Redis中，fork一个process来处理copy entire data to file，在这种情况下，main loop并未被阻塞而是不断地运行，处理其他的request
2) CPU asynchronous operation: CPU对于耗时的instruction，并不阻塞主流程
3) 



### Atomicity/atomic概念

在`./Atomic`进行了介绍。

### Synchronization

| 层次 | distributed system    | standalone                      | instruction      |
| ---- | --------------------- | ------------------------------- | ---------------- |
|      | distributed lock      | lock                            | lock instruction |
|      | barrier               | barrier                         | memory barrier   |
|      | message communication | IPC、inter-thread communication |                  |
|      | 共识                  |                                 |                  |

