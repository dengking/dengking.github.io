# Language and program

[Language](https://en.wikipedia.org/wiki/Language)是我们与生俱来的天赋，我们使用language可以**描述**（**describes**）世间万物，或者说，语言的功能就是来进行**描述**的：

- 使用语言描述[definition](https://en.wikipedia.org/wiki/Definition)
- 使用语言来描述[算法](https://en.wikipedia.org/wiki/Algorithm)
- ......（此处可以枚举数不清的例子）

在[language](https://en.wikipedia.org/wiki/Language)的大家庭中，有着多个成员，比如：

- 我们日常交流使用[natural language](https://en.wikipedia.org/wiki/Natural_language)，比如Chinese、English
- [Formal language](https://en.wikipedia.org/wiki/Formal_language)，比如[programming language](https://en.wikipedia.org/wiki/Programming_language)
- [Language of mathematics](https://en.wikipedia.org/wiki/Language_of_mathematics)

作为software engineer，我们幸运地已经使用了上面枚举的三种语言。

作为software engineer，我们是在使用[programming language](https://en.wikipedia.org/wiki/Programming_language)来描述世间万物，我们所做的很多工作，就是将人们使用[natural language](https://en.wikipedia.org/wiki/Natural_language)、[language of mathematics](https://en.wikipedia.org/wiki/Language_of_mathematics)等语言的描述，转换为[programming language](https://en.wikipedia.org/wiki/Programming_language)的描述。



## 一切“描述”都是语言？

当谈到**语言**后，那么得说说“描述”这个词了，感觉这个词是一个非常宽泛、非常囊括的词，比如：

在[Language of mathematics](https://en.wikipedia.org/wiki/Language_of_mathematics)的[The meanings of mathematics](https://en.wikipedia.org/wiki/Language_of_mathematics)中就使用了“describes ”这个词（这段话总结的太好以至于我忍不住地把它摘录过来了）：

> **Mathematics describes the real world**: many areas of mathematics originated with attempts to **describe** and solve real world phenomena - from measuring farms ([geometry](https://en.wikipedia.org/wiki/Geometry)) to falling apples ([calculus](https://en.wikipedia.org/wiki/Calculus)) to gambling ([probability](https://en.wikipedia.org/wiki/Probability)). Mathematics is widely used in modern [physics](https://en.wikipedia.org/wiki/Mathematical_physics) and [engineering](https://en.wikipedia.org/wiki/Engineering), and has been hugely successful in helping us to understand more about the universe around us from its largest scales ([physical cosmology](https://en.wikipedia.org/wiki/Physical_cosmology)) to its smallest ([quantum mechanics](https://en.wikipedia.org/wiki/Quantum_mechanics)). Indeed, the very success of mathematics in this respect has been a source of puzzlement for some philosophers (see [The Unreasonable Effectiveness of Mathematics in the Natural Sciences](https://en.wikipedia.org/wiki/The_Unreasonable_Effectiveness_of_Mathematics_in_the_Natural_Sciences) by [Eugene Wigner](https://en.wikipedia.org/wiki/Eugene_Wigner)).
>
> **Mathematics describes abstract structures**: on the other hand, there are areas of pure mathematics which deal with [abstract structures](https://en.wikipedia.org/wiki/Abstract_structure), which have no known physical counterparts at all. However, it is difficult to give any categorical examples here, as even the most abstract structures can be co-opted as models in some branch of physics (see [Calabi-Yau spaces](https://en.wikipedia.org/wiki/Calabi-Yau_spaces) and [string theory](https://en.wikipedia.org/wiki/String_theory)).
>
> **Mathematics describes mathematics**: mathematics can be used reflexively to describe itself—this is an area of mathematics called [metamathematics](https://en.wikipedia.org/wiki/Metamathematics).

那不禁想问：数学是一门语言吗？如果从“描述”的角度来看话，我觉得可以回答“是”，下面是原文中紧跟着的对这个问题的论述：

> Mathematics can communicate a range of meanings that is as wide as (although different from) that of a **natural language**. As [English](https://en.wikipedia.org/wiki/England) mathematician [R.L.E. Schwarzenberger](https://en.wikipedia.org/wiki/Rolph_Ludwig_Edward_Schwarzenberger) says:
>
> > *My own attitude, which I share with many of my colleagues, is simply that **mathematics is a language**. Like English, or Latin, or Chinese, there are certain concepts for which mathematics is particularly well suited: it would be as foolish to attempt to write a love poem in the language of mathematics as to prove the [Fundamental Theorem of Algebra](https://en.wikipedia.org/wiki/Fundamental_Theorem_of_Algebra) using the English language.*

根据上面的论述来看，[English](https://en.wikipedia.org/wiki/England) mathematician [R.L.E. Schwarzenberger](https://en.wikipedia.org/wiki/Rolph_Ludwig_Edward_Schwarzenberger) 认为 数学是一门语言。

让我们沿着这个思路进一步进行推广就得到本小节的标题所描述的问题：“一切“描述”都是语言？”，这个问题我无法给出答案，以我目前的认知水平，我觉得是的。

关于这个问题，在我的工程[automata-and-formal-language](https://dengking.github.io/automata-and-formal-language)的文章[如何来进行描述？](https://dengking.github.io/automata-and-formal-language/Formal-language/Description-and-language/)中对此也进行了讨论。



[English](https://en.wikipedia.org/wiki/England) mathematician [R.L.E. Schwarzenberger](https://en.wikipedia.org/wiki/Rolph_Ludwig_Edward_Schwarzenberger) 的这番言论也向我们揭示了：不同的语言有着各自的优势。

## 语言的结构

在[语言学](https://en.wikipedia.org/wiki/Linguistics)中，使用[**grammar**](https://en.wikipedia.org/wiki/Grammar)来描述语言的结构，关于此，参见[**automata-and-formal-language**](https://dengking.github.io/automata-and-formal-language)的[Language and grammar](https://dengking.github.io/automata-and-formal-language/Formal-language/Language-and-grammar/#language_and_grammar)文章。

## 语言的expressive power

> Mathematics can communicate a range of meanings that is as wide as (although different from) that of a **natural language**.

这段话向我们传达了这样的含义：不同的语言 所能够描述的meaning的范围 是不同的。下面我们使用集合的观点来描述这个含义：如果我们将语言“所能够描述的meaning”放到一个集合中，把这个集合称为 meaning set，那么不同语言的meaning set的大小是不同的。使用我们的自然语言来描述就是：有的语言能够描述的范围更大、有的语言无法描述另外一个语言所表达的。这就是本节标题中的“expressive power”的含义。

关于expressive power，参见：

- 维基百科[Expressive power](https://en.wikipedia.org/wiki/Expressive_power_(computer_science))
- 维基百科[Combinatory categorial grammar](https://en.wikipedia.org/wiki/Combinatory_categorial_grammar) （其中提及了expressive power）



## 使用不同的学科的语言来进行描述

通过前面的内容，我们应该已经对语言有了更加宽泛的认识了。不同的学科创建了各自的理论体系（创建了概念、规则等），这就形成了该学科的特有的**语言**，这就形成了对于同一个事物，各个学科都可以使用自己的语言来对它进行描述，这就好比对于“苹果”，中文、英文、法文有着各自的描述方式。

拥有这样的认知是非常重要的，比如，当我们在阅读维基百科的一些文章的时候，常常会碰到的一种情况是某某概念，数学中怎么描述、计算机科学中怎么描述、语言学中怎么描述。

拥有这样的认知对于软件工程师尤其重要，正如在本文开头做说的：

> 我们所做的很多工作，就是将人们使用[natural language](https://en.wikipedia.org/wiki/Natural_language)、[language of mathematics](https://en.wikipedia.org/wiki/Language_of_mathematics)等语言的描述，转换为[programming language](https://en.wikipedia.org/wiki/Programming_language)的描述



## 我对“语言”的探索

- [NLP](https://dengking.github.io/NLP/)
- [compiler-principle](https://dengking.github.io/compiler-principle/)
- [automata-and-formal-language](https://dengking.github.io/automata-and-formal-language)
