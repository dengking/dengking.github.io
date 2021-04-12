# Atomic



## What is atomic/atomicity?

### 直观理解

"atomic/atomicity"，"atomicity"即"原子性"，它借用了物理学中"[atom(原子)](http://en.wiki.sxisa.org/wiki/Atom)"的概念: 

> An **atom** is the smallest unit of ordinary [matter](http://en.wiki.sxisa.org/wiki/Matter) that forms a [chemical element](http://en.wiki.sxisa.org/wiki/Chemical_element). 

意味着最小unit，是不可分割的。

在不同的层级都可以使用这个概念，提供atomic primitive/interface，比如:

1、instruction level: X86 `cmpxchg`

2、OS level: Linux `openat`

### Formal definition

关于atomic的形式化定义，参见工程parallel-computing的相关章节。

## Atomic primitive/interface

1、Instruction 层： instruction就是atomic的

2、OS level: Linux `openat`

3、Application层，也有atomic的概念，也可以实现atomic

cppreference [Atomic operations library](https://en.cppreference.com/w/cpp/atomic)



## Atomic and unit 

一般最小unit是Atomic ，关于unit，参见文章《Unit》。

## 实现思路

### Bottom-up analysis

从最最底层(nstruction 层)开始，自底向上进行分析，显然如果底层能够保证atomic，那么能够为高层实现atomic提供较好的支持，下面是一些level:  

1、Instruction level

2、OS level

3、Application  level

### Assemble as atomic primitive

在系统层进行集成: 将多个操作在系统层/实现层进行集成，提供原子特性的接口，从而达到原子性的目的，下面是典型的例子：

1、instruction level: X86 `cmpxchg`

2、OS level: Linux `openat`

3、......

我们将这种思路称为: "assemble as atomic primitive"。