# 想法

## 知识如此繁杂，所以对它们的组织，梳理非常重要

我的写作原则。

### 梳理，而不是抄写

应该坚持如上原则来进行编写，给出所引用的资源的链接。

### 构建big picture

构建理论框架，从更高的角度来思考问题。



## 从更高的角度来思考问题

从具体问题中跳脱出来，从理论的高度来分析它，如从compiler principle扩展到[automata-and-formal-language](https://dengking.github.io/automata-and-formal-language/)，然后扩张到[Theory of computation](https://en.wikipedia.org/wiki/Theory_of_computation)。

一些常用的角度：

从时空的角度

从哲学的角度（比如[Formalism (philosophy of mathematics)](https://en.wikipedia.org/wiki/Formalism_(philosophy_of_mathematics))）

从设计者的角度来思考：

从OS的设计者的角度出发来进行思考（参见工程[Linux-OS](https://dengking.github.io/Linux-OS/)）、从programming language的设计者的角度出发来进行思考（参见工程[programming-language](https://dengking.github.io/programming-language/)），从data-system的设计者的角度出发来进行思考（参见工程parallel-computing），如果以这个角度来进行思考，我们就能够掌握它这样设计的意图，很多问题都变得容易理解。



## 以发展的眼光来看待计算机科学的演进

计算机科学是在不断地演进、不断强大的，今天我们所经历的这些变革（如AI、blockchain等）将称为后世人们眼中的历史，我们需要不断地跟进新的技术，而且在学习的过程中，需要梳理技术的发展脉络，这样我们能够更好地掌握新技术所改变的是什么、发明家、研究员们为什么发明创造它。

比如：

从Apache 到 Nginx

从gcc 到 llvm

从[Monolithic kernel](https://en.wikipedia.org/wiki/Monolithic_kernel)到[Microkernel](https://en.wikipedia.org/wiki/Microkernel)



## 意图决定最终的结果

在阅读[clang](http://clang.llvm.org/)的[Clang vs Other Open Source Compilers](https://clang.llvm.org/comparison.html)时，其中的一段话让我印象深刻：

> The goal of this list is to describe how differences in goals lead to different strengths and weaknesses, not to make some compiler look bad. 

在[Clang vs Other Open Source Compilers](https://clang.llvm.org/comparison.html)中，作者对比了Clang和其它几款compiler的strength和weakness，从中我所领悟到的是：意图决定最终结果，即软件的设计者在开发软件之前的的目标最终决定了他所开发出这软件的strength和weakness，所以，高明的设计者对于软件的重要性。

与此类似的案例还有：

[git](https://en.wikipedia.org/wiki/Git)

## Internal

在阅读git的[1.3 Getting Started - What is Git?](https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F)节时候，其中的这段话令我印象深刻：

> if you understand what Git is and the fundamentals of how it works, then using Git effectively will probably be much easier for you. 


显然，它背后蕴含的道理肯定不仅仅局限于git。现在我们已经过了[Reinventing the wheel](https://zh.wikipedia.org/zh-hans/%E9%87%8D%E9%80%A0%E8%BD%AE%E5%AD%90)的年代，取而代之的是有大量的、可以直接使用的软件，比如operating system，version control system，一个不争的事实是：如果了解软件的实现原理、内部细节，那么就能够高效地使用它。



## 理论 与 实践



学习: 工程师的学习，应该设计下面的两个层面:

- tips and tricks
- philosophy and design

这是我在阅读 https://www.linuxjournal.com/article/10688 时，其中提及的:

> Because my column is generally aimed more at tips and tricks and less on philosophy and design, I'm not going to talk much about overall approaches to problem solving.

这其实和我之前一直强调的 理论 与 实践 非常吻合