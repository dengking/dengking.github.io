# Abstraction principle

我们需要遵循abstraction principle，具体来说它包括: 

## Design to abstraction

参见:

1) 工程`software-engineering`的`Software-design\Principle\Abstraction`章节

## Program to abstraction

参见: 

1) 工程`programming-language`的`Theory\Programming-paradigm\Abstraction-and-polymorphism\Program-to-abstraction`章节

2) 工程`programming-language`的`Theory\Programming-paradigm\Object-oriented-programming\Design-pattern\Principle`章节



## 优势/为什么这样做？

需要论述这样做的原因，参考内容:

1) 《Book-Designing-Data-Intensive-Applications》



### 隐藏细节，以 generic 的方式来建立模型(model)

这是我想到在Book 《Designing-Data-Intensive-Applications》中提出的观点而联想到的OOP中其实有类似的描述，显然，这是abstraction的一个优势。

在OOP中，将此成为encapsulation。

下面是一些素材:

`std::declval` 隐藏了各种Type的construction细节；

trait 提供了查询type的attribute的consistent interface；



### 解耦(Decouple)

各部分依赖的是抽象的接口，而不是具体；

### Information hiding and transparency

> NOTE: 关于"transparency"，参见工程software-engineering的`Software-design\Principle\Information-hiding`章节

内部实现可以灵活调整，上层无需变动，这其实是transparency；

其实这是 **隐藏细节** 所带来的。



### Clean client code

> NOTE: 这其实也是隐藏细节所带来的

遵循 abstraction principle，能够实现clean client code: clean client code 是abstract的，隐藏了concrete/细节，它是conceptual model；

这是我在阅读 eli.thegreenplace [A polyglot's guide to multiple dispatch](https://eli.thegreenplace.net/2016/a-polyglots-guide-to-multiple-dispatch/) 时，其中给出的，我觉得它能够是体现 abstraction principle 的优势的。

在 refactoring.guru [Visitor](https://refactoring.guru/design-patterns/visitor) 中，给出了一个具体的对比案例:

cumbersome(笨拙的):  

```C++
foreach (Node node in graph)
    if (node instanceof City)
        exportVisitor.doForCity((City) node)
    if (node instanceof Industry)
        exportVisitor.doForIndustry((Industry) node)
    // ...
}
```

clean:

```C++
// Client code
foreach (Node node in graph)
    node.accept(exportVisitor)
```



#### 容易理解

遵循 abstraction principle，能够实现clean client code，这样的code是容易理解的；



### Conceptual advantage

这是在阅读 wikipedia [Software transactional memory # Conceptual advantages and disadvantages](https://en.wikipedia.org/wiki/Software_transactional_memory#Conceptual_advantages_and_disadvantages) 时，其中提及的一个点:

> In addition to their performance benefits[*[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)*], STM greatly simplifies conceptual understanding of multithreaded programs and helps make programs more maintainable by working in harmony with existing high-level abstractions such as objects and modules. 

### Code reuse

遵循abstraction principle能够实现code reuse，`N*M`，通过抽象的接口可以将各个模块进行组合。