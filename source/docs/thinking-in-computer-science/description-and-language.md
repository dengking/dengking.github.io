# 描述

各种学科，在进行研究的时候，往往是使用简洁的公式（表达式）来描述复杂的问题，比如数学表达式。公式（表达式）其实是一种抽象，抽象的过程对于任何学科都是至关重要的，因为抽象的过程是对本质的靠近的过程。那我们使用什么来进行描述呢？在不同的领域，有不同的描述方式，比如：

- 数学中的表达式（[expression](https://en.wikipedia.org/wiki/Expression_(mathematics))）

- 计算机科学中的programming language

上述两种**描述**本质上来说是一种**语言**，更加准确地说是[formal language](https://en.wikipedia.org/wiki/Well-formed_formula)。在语言学中，通常使用[grammar](https://en.wikipedia.org/wiki/Grammar)来描述语言的结构，[formal language](https://en.wikipedia.org/wiki/Well-formed_formula)的grammar是[formal grammar](https://en.wikipedia.org/wiki/Formal_grammar)，比如[context free grammar](https://en.wikipedia.org/wiki/Context-free_grammar)。formal grammar常常采用的描述方式是产生式（[production](https://en.wikipedia.org/wiki/Production_(computer_science))），那production这种描述方式是语言吗？我觉得它应该算是语言，因为它有固定的语法、语义。那能否说：所有的描述都是语言？

在计算机科学中，对于语言（描述）的研究是非常重要的， 简单语言能够带来巨大的好处。

有的语言是general purpose的，如

- python
- c

有些则是special-purpose的，如

- [Zephyr  ASDL](https://www.cs.princeton.edu/research/techreps/TR-554-97)
- [Interface description language](https://en.wikipedia.org/wiki/Interface_description_language)
- [Data modeling languages](https://en.wikipedia.org/wiki/Category:Data_modeling_languages)。

## 递归公式VS产生式

数学中的递归公式（[recurrence relation](https://en.wikipedia.org/wiki/Recurrence_relation)），语言学中的产生式，两者其实有着共同之处：递归。

production可以用来描述所有的具有hierarchy结构的数据，这样的结构是允许具备递归性的。这种hierarchy结构对应着一棵树。

> NOTE: formal grammar是描述具有hierarchy structure的一个非常好的工具

递归公式则描述了问题求解过程的递归性，它并不是像产生式那样描述的是具体实际的结构。但是，如果从计算机程序实现递归公式的角度来看，由于计算机执行过程中使用的是stack，每次函数调用都会new一个栈帧对象，通过以适当的方式将栈帧给摆放起来的话，可以对应一棵树。

从本质上来说，program是对各种描述的计算机实现。



## 描述抽象结构

在论文[The Zephyr Abstract Syntax Description Language](https://www.cs.princeton.edu/research/techreps/TR-554-97)中有这样的总结：

Regular expressions describe lexical structures  of programming languages.

Context free grammars describe syntactic structures of programming languages .

ASDL describes the [abstract syntax](https://en.wikipedia.org/wiki/Abstract_syntax)  of compiler intermediate representations (IRs) and other tree-like data
structures.

[Algebraic data types](https://en.wikipedia.org/wiki/Algebraic_data_type)

## ASDL

## python ASDL

python使用ASDL来描述自己的AST

https://www.usenix.org/legacy/publications/library/proceedings/dsl97/full_papers/wang/wang.pdf

http://www.oilshell.org/blog/2016/12/11.html

https://stackoverflow.com/questions/8873126/zephyr-asdl-abstract-syntax-description-language

https://devguide.python.org/compiler/

https://github.com/python/cpython/blob/master/Parser/Python.asdl

http://asdl.sourceforge.net/

https://www.cs.princeton.edu/research/techreps/TR-554-97

显然，它也可以作为一种树描述语言。

https://en.wikipedia.org/wiki/Algebraic_data_type

https://en.wikipedia.org/wiki/Abstract_syntax



# 理论

在使用维基百科进行检索的时候，发现其实上面所思考的问题属于[Mathematical logic](https://en.wikipedia.org/wiki/Mathematical_logic)理论范轴，这个理论和[Computer science](https://en.wikipedia.org/wiki/Computer_science)是紧密相关的。