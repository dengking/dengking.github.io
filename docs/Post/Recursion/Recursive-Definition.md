# Recursive definition

软件工程师，对于definition（定义）这个词肯定不会陌生，因为我们每天都在“定义一个函数”、“定义一个类”。维基百科的[definition](https://en.wikipedia.org/wiki/Definition)内容比较深奥，本文将简单地来说definition，定义就是在前文中所提及的“描述”，不过定义有着更多限制。本文重点简述的是[Recursive definition](https://en.wikipedia.org/wiki/Recursive_definition)，在计算机科学中，[recursion](https://en.wikipedia.org/wiki/Recursion)无处不在，软件工程师应该对它保持敏感，对于所有具备[recursion](https://en.wikipedia.org/wiki/Recursion)特性的（包括类型、过程等），都能够给出其[Recursive definition](https://en.wikipedia.org/wiki/Recursive_definition)。

## [Recursive definition](https://en.wikipedia.org/wiki/Recursive_definition)

In [mathematics](https://en.wikipedia.org/wiki/Mathematics) and [computer science](https://en.wikipedia.org/wiki/Computer_science), a **recursive definition**, or **inductive definition**, is used to define the [elements](https://en.wikipedia.org/wiki/Element_(mathematics)) in a [set](https://en.wikipedia.org/wiki/Set_(mathematics)) in terms of other elements in the set ([Aczel](https://en.wikipedia.org/wiki/Peter_Aczel) 1977:740ff). Some examples of recursively-definable objects include [factorials](https://en.wikipedia.org/wiki/Factorial), [natural numbers](https://en.wikipedia.org/wiki/Natural_number), [Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number), and the [Cantor ternary set](https://en.wikipedia.org/wiki/Cantor_set).

> NOTE: 上述对recursive definition的描述使用的是数学中的set的概念，数学中的set表示所有具备某一特性的object的集合，比如我们可以将所有具备相同type的object放到一个set中。下面我将它转换为software engineer更加熟悉的type（类型）的概念：
>
> 规定属于同一个set的所有元素都是具有相同类型的元素，则recursively-definable object是由相同类型的其他object（即这个集合中的其他元素）来进行定义的（构成）。
>
> 可以看到，当我们将set理解为type后，原来的描述就变成了software engineer非常任意理解的了。
>

A [recursive](https://en.wikipedia.org/wiki/Recursive) [definition](https://en.wikipedia.org/wiki/Definition) of a [function](https://en.wikipedia.org/wiki/Function_(mathematics)) defines values of the function for some inputs in terms of the values of the same function for other (usually smaller) inputs. For example, the [factorial](https://en.wikipedia.org/wiki/Factorial) function *n*! is defined by the rules

0! = 1.

(*n* + 1)! = (*n* + 1)·*n*!.

> NOTE: 原文中给出了两种：recursively defined functions and sets

## Recursive definition and [closure](https://en.wikipedia.org/wiki/Closure_(mathematics)) 

按照recursively defined sets的概念，这个set在构造新元素的operation下是closed的（参见 [Closure (mathematics)](https://en.wikipedia.org/wiki/Closure_(mathematics)) ）。



## Recursive definition in computer science

有太多太多的算法、结构都是可以使用recursive definition的。

一般带有“sub”的都是可以进行recursive definition的，比如subtree，sublist

 能够recursive definition的，称它具备递归性。

## Recursive definition and hierachy

可以使用recursive definition进行定义的structure，都具备hierarchy特性。 



## [Recursive data types](https://en.wikipedia.org/wiki/Recursive_data_type)

这在[data-structure](https://dengking.github.io/data-structure/)中会进行讨论。