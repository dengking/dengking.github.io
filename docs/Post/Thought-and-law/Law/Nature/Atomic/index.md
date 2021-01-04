# Atomic

## What is atomic/atomicity?

"atomic/atomicity"，"atomicity"即"原子性"，它借用了物理学中"[atom(原子)](http://en.wiki.sxisa.org/wiki/Atom)"的概念: 

> An **atom** is the smallest unit of ordinary [matter](http://en.wiki.sxisa.org/wiki/Matter) that forms a [chemical element](http://en.wiki.sxisa.org/wiki/Chemical_element). 

意味着最小unit，是不可分割的。

在不同的层级都可以使用这个概念，提供atomic primitive/interface，比如:

1、instruction level: X86 `cmpxchg`

2、OS level: Linux `openat`

## Atomic primitive/interface

1、Instruction 层： instruction就是atomic的

2、OS level: Linux `openat`

3、Application层，也有atomic的概念，也可以实现atomic

cppreference [Atomic operations library](https://en.cppreference.com/w/cpp/atomic)



## 实现思路

在系统层进行集成: 将多个操作在系统层/实现层进行集成，提供原子特性的接口，从而达到原子性的目的，下面是典型的例子：

1、instruction level: X86 `cmpxchg`

2、OS level: Linux `openat`

3、......

我们将这种思路称为: "assemble as atomic"。