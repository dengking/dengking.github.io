# Abstraction and model

本文讨论abstraction(抽象) 和 model(建模)，作为software engineer，我们需要解决现实世界中的各种问题，这个过程其实是: abstraction(抽象) 并 model(建模)，然后使用programming language来实现/描述model，最后将此model应用于实际，从而使实际问题得解；

> NOTE: 关于model的实现，在[Abstract-and-concrete](./Abstract-and-concrete.md) 中进行了讨论。

按照Wikipedia中的说法，这里本段所述的model是[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)，下面是我的总结:

[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model) 是对concept（通过abstraction创建的）和其relation的描述（其实它本身就是一个抽象的过程），它是对原理的描述，它没有达到实现层面，它指导着实现。在计算机科学的各个领域，有着非常多著名的[conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)。其实我们可以回顾学习生涯，教材往往是先从理论模型（其实就是概念模型）开始讲起，后面再来讲述实现，因为理论模型剔除了很多细节，而抽象出来最最本质的内容，易于理解，也就是[Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)使我们能够更加轻松地 [understand](https://en.wikipedia.org/wiki/Understanding)。



## wikipedia [Conceptual model](https://en.wikipedia.org/wiki/Conceptual_model)

A **conceptual model** is a representation of a system, made of the composition of [concepts](https://en.wikipedia.org/wiki/Concept) which are used to help people [know](https://en.wikipedia.org/wiki/Knowledge), [understand](https://en.wikipedia.org/wiki/Understanding), or [simulate](https://en.wikipedia.org/wiki/Simulation) (模拟) a subject(主题) the model represents. In contrast, [physical models](https://en.wikipedia.org/wiki/Physical_model) are [physical objects](https://en.wikipedia.org/wiki/Physical_object); 

> NOTE: 上面这段话中，"the model represents"是一个定语从句，修饰 "subject" 。
>
> science 和 technology的发展总是遵循: 从theory到implementation，即先创建theory然后根据theory来进行implement；

*Conceptual model* may refer to models which are formed after a [conceptualization](https://en.wiktionary.org/wiki/concept#Noun) or [generalization](https://en.wikipedia.org/wiki/Generalization) process.[[1\]](https://en.wikipedia.org/wiki/Conceptual_model#cite_note-MWCD-1)[[2\]](https://en.wikipedia.org/wiki/Conceptual_model#cite_note-2) Conceptual models are often abstractions of things in the real world, whether physical or social. 

> NOTE: 上述  "[conceptualization](https://en.wiktionary.org/wiki/concept#Noun) or [generalization](https://en.wikipedia.org/wiki/Generalization)", 其实都是抽象的过程；

### Modelling techniques

> NOTE: 建模技术，原文这一段这样描述的是computer science中的model technique。因此有必要了解一下；
>
> 可以看到，本节描述的各种technique都有对应的diagram，这些diagram是programmer原来描述这些conceptual model的；

*Main article:* [Conceptual model (computer science)](https://en.wikipedia.org/wiki/Conceptual_model_(computer_science))

#### Data flow modeling

**Data flow modeling** (DFM) is a basic **conceptual modeling technique** that graphically represents elements of a system. DFM is a fairly simple technique, however, like many conceptual modeling techniques, it is possible to construct higher and lower level representative diagrams. The [data flow diagram](https://en.wikipedia.org/wiki/Data_flow_diagram) usually does not convey complex system details such as parallel development considerations or timing information, but rather works to bring the major system functions into context. Data flow modeling is a central technique used in systems development that utilizes the [structured systems analysis and design method](https://en.wikipedia.org/wiki/Structured_systems_analysis_and_design_method) (SSADM).

> NOTE: 图: [data flow diagram](https://en.wikipedia.org/wiki/Data_flow_diagram)。

#### Entity relationship modeling

[Entity–relationship modeling](https://en.wikipedia.org/wiki/Entity–relationship_model) (ERM) is a conceptual modeling technique used primarily for software system representation. Entity-relationship diagrams, which are a product of executing the ERM technique, are normally used to represent database models and information systems. The main components of the diagram are the entities and relationships. The entities can represent independent functions, objects, or events. The relationships are responsible for relating the entities to one another.

> NOTE: 图: entity-relationship diagram。

#### Event-driven process chain

The [event-driven process chain](https://en.wikipedia.org/wiki/Event-driven_process_chain) (EPC) is a conceptual modeling technique which is mainly used to systematically improve business process flows. 

#### State transition modeling

State transition modeling makes use of [state transition diagrams](https://en.wikipedia.org/wiki/State_transition_diagram) to describe system behavior. These state transition diagrams use distinct states to define system behavior and changes. Most current modeling tools contain some kind of ability to represent state transition modeling. The use of state transition models can be most easily recognized as logic state diagrams and directed graphs for [finite-state machines](https://en.wikipedia.org/wiki/Finite-state_machine).

> NOTE: 图  [state transition diagrams](https://en.wikipedia.org/wiki/State_transition_diagram) 

### Statistical models

*Further information:* [Statistical model](https://en.wikipedia.org/wiki/Statistical_model)*,* [Parametric model](https://en.wikipedia.org/wiki/Parametric_model)*,* [Nonparametric statistics](https://en.wikipedia.org/wiki/Nonparametric_statistics)*, and* [Model selection](https://en.wikipedia.org/wiki/Model_selection)

> NOTE: 这是AI中非常重要的概念

## Models

本节介绍我总结的一些model。

### Task model

参见工程software-engineering的`Software-design\Design-pattern\Architecture-pattern\Task-model`章节。

### Event-driven model

参见工程parallel-computing的`Application\Message-processing-system\Event-driven-model`章节。

### 使用event-driven model和task model可以描述太多太多的software

比如：OS kernel对hardware的管理可以使用event-driven model来进行描述；OS kernel实现multitasking可以使用task model来进行描述。



### Model of computation

参见:

1) 工程discrete的`Relation-structure-computation\Computation\Theory-of-computation\Model-of-computation`章节。

2) wikipedia [Model of computation](https://en.wikipedia.org/wiki/Model_of_computation)



## Model是一种简化

model是一种简化，现实的问题往往更加复杂，往往需要综合多个model。

### Run-time environment

[龙书](https://dengking.github.io/compiler-principle/)的[第七章](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/)中所定义的run-time environment是一个简化模型，它忽略了一些细节，比如multi-thread，而仅仅关注于部分内容。在对其进行实现的时候，需要考虑其他的诸多因素，参见工程[Linux-OS](https://dengking.github.io/Linux-OS/)的[Process mode: run time environment](https://dengking.github.io/Linux-OS/Kernel/Guide/Linux-OS's-multitasking/01-Process-mode-run-time-environment/)，其中描述了实现的细节。

### wikipedia [Statistical model](https://en.wikipedia.org/wiki/Statistical_model)

> As Burnham & Anderson state, "A model is a simplification or approximation of reality and hence will not reflect all of reality"—whence the saying "[all models are wrong](https://en.wikipedia.org/wiki/All_models_are_wrong)".



## Mathematical model，一种更加高效的描述方式

在各个学科，建立[mathematical model](https://en.wikipedia.org/wiki/Mathematical_model)让描述更加便捷、更加容易被人理解。

下面是[mathematical model](https://en.wikipedia.org/wiki/Mathematical_model)的一些例子：

Stochastic process：https://en.wikipedia.org/wiki/Stochastic_process

Statistical model：https://en.wikipedia.org/wiki/Statistical_model

Markov model：

- https://en.wikipedia.org/wiki/Markov_model
- https://en.wikipedia.org/wiki/Hidden_Markov_model



## 模型与实现

一个model，可以有多种实现。

### Example

在龙书的[第七章](https://dengking.github.io/compiler-principle/Chapter-7-Run-Time-Environments/)中所讲述的logical address space是一个概念模型，对于这个概念模型不同的操作系统有不同的时候，目前主流的实现方式是paged virtual address space。



## See also

- [Database model](https://en.wikipedia.org/wiki/Database_model)
- [Data model](https://en.wikipedia.org/wiki/Data_model)



