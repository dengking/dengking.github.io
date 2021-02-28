# Software and hardware

将它的tag定义为: tag-hardware and software-Andy and Bill's law

## 谁促进谁？

Q: 是hardware促进software的发展还是software促进hardware的发展？应该是software促进hardware的发展?

A: 应该主要是software促进hardware的发展，example:

1 以Linux OS book中的观点为例来进行说明，OS是CPU的客户

## Andy-bill's law

software需要充分运用hardware的特性以提高自身的性能；software刺激着hardware的不断提高，其实这是就是Andy-bill's law，Andy代表着hardware，bill代表着software

### example

1 likely and unlikely

## Bottom-up analysis(自底向上分析): from hardware to software

对于在software development中遇到的很多问题，以自底向上，从hardware到software的方式来进行分析，能够让我们从根本上找出问题的原因和解决方法；



> 这让我想到了 浪潮之巅 中的 安迪-比尔定律 
>
> https://site.douban.com/189688/widget/notes/11229948/note/251703757/，显然 安迪-比尔定律 的描述是更加精准 。



### Level

Instruction level

OS level

Application  level

> NOTE: 需要将`Software-design\Design-pattern\Architecture-pattern\Multilayered-architecture`中的内容结合起来

### Example

#### Atomic 

参见文章《Atomic》

##### Atomic and thread safe

从instruction 层来分析thread safe

#### Parallel computing and concurrent computing

Multicore->parallel computing、concurrent computing

parallel computing、concurrent computing的兴起的背后推力:

1、CPU超Multicore方向发展

2、network越来越强大

#### likely/unlikely

让我想到这个的是: likely/unlikely->branch prediction->CPU Speculative execution