# 总结

无论是Mathematical induction，还是Structural induction，它们本质上都是[proof method](https://en.wikipedia.org/wiki/Proof_method) （证明方法），它描述的是一种推广。

[Recursive definition](./Recursive-Definition.md)（也叫做**inductive definition**）正如其名，它是definition，是specification，所以需要非常严格，它不涉及实现。



| 递归                                                         | 归纳                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [Recursion](./Recursion.md)                                  | [Induction](./Induction-and-deduction/Induction.md)          |
| [Corecursion](./Corecursion.md)                              | [Coinduction](./Induction-and-deduction/Coinduction.md)      |
| [Structural recursion](./Induction-and-deduction/Structural-induction.md) | [Structural induction](./Induction-and-deduction/Structural-induction.md) |

关于Structural recursion和Structural induction，参见[Structural induction](./Induction-and-deduction/Structural-induction.md)。





## Recursion VS corecursion

recursion 和 corecursion 的计算方向是相反：对于一个 [recurrence relations](https://en.wikipedia.org/wiki/Recurrence_relation) ，如*n! := n × (n - 1)!*.，recursion是从左至右，但是corecursion是从右至左，但是能够殊途同归

- recursion works **analytically** VS corecursion works **synthetically**
- recursion **top-down** VS corecursion **bottom-up**
- recursion **reduce** VS corecursion **produce**

在[Tree traversal](https://en.wikipedia.org/wiki/Tree_traversal)中有如下描述：

**Depth-first search** is easily implemented via a **stack**, including **recursively** (via the **call stack**), while **breadth-first search** is easily implemented via a **queue**, including **corecursively**.

## Recursion VS induction

无论是induction还是recursion，都需要base  case。

Induction本质上都是[proof method](https://en.wikipedia.org/wiki/Proof_method) 。

在维基百科[Structural induction](https://en.wikipedia.org/wiki/Structural_induction)中有这样的描述：

> A structurally recursive function uses the same idea to define a recursive function: "base cases" handle each minimal structure and a rule for recursion. Structural recursion is usually proved correct by structural induction; 

另外参见：https://www.cs.cmu.edu/~rwh/introsml/techniques/indrec.htm ，非常好的一篇文章。

