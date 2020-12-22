# Nature/abstraction

本文标题"nature"的含义是"本质"。本文的观点是: 探寻问题的本质，对于本质上相同的问题，可以使用相同的技术来进行实现。

在本质上相同的问题、追寻相同的目标、具备相同的结构，可以使用相同的技术、相同的思想、相同的概念、相同的algorithm；这就出现了同一个概念在不同层次、领域的相互借用；同一技术在不同层次、领域的相互借用；同一model可以使用于不同层次、领域；





## Optimization principle

最优化原则。



## 使用asynchronous programming来optimization

这是为了**追寻相同的目标**(optimization)，而使用类似的技术(asynchronous programming)的例子。

asynchronous/non-blocking operation: 启动，不阻塞主调线程/main loop，下面是一些例子:
1) Redis中，fork一个process来处理copy entire data to file，在这种情况下，main loop并未被阻塞而是不断地运行，处理其他的request
2) CPU asynchronous operation: CPU对于耗时的instruction，并不阻塞主流程
3) 



## Atomicity概念

"atomicity"即"原子性"，在不同的层级都可以使用这个概念，提供atomic operation/instruction，比如:

X86 `cmpxchg`

Linux `openat`



## Synchronization

| 层次 | distributed system    | standalone                      | instruction      |
| ---- | --------------------- | ------------------------------- | ---------------- |
|      | distributed lock      | lock                            | lock instruction |
|      | barrier               | barrier                         | memory barrier   |
|      | message communication | IPC、inter-thread communication |                  |
|      | 共识                  |                                 |                  |

