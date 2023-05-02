# youtube [Vectors | Chapter 1, Essence of linear algebra](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab)

"The introduction of numbers as coordinates is an act of violence."

—Hermann Weyl

The fundamental, root-of-it-all building block for linear algebra is the vector, so it's worth making sure that we're all on the same page about what exactly a vector is.

You see, broadly speaking there are three distinct but related ideas about vectors, which I'll  call 

1、the physics student perspective, 

2、the computer science student perspective, and 

3、the mathematician's perspective.

## The physics student perspective

The physics student perspective is that vectors are arrows pointing in space. What defines a given vector is its **length**, and the **direction** it's pointing in, but as long as those two facts are the same, you can move it all around and it's still the same vector.

Vectors that live in the flat plane are two-dimensional, and those sitting in broader space that you and I live in are three-dimensional.

## The computer science perspective

The computer science perspective is that vectors are ordered lists of numbers. For example, let's say that you were doing some analytics about house prices, and the only features you cared about were square footage(面积) and price. You might model each house with a pair of numbers: the first indicating square footage, and the second indicating price. Notice that the order matters here. In the lingo, you'd be modelling houses as two-dimensional vectors, where in this context, "vector" is pretty much just a fancy word for "list", and what makes it two-dimensional is the fact that the length of that list is 2.

## The mathematician perspective

The mathematician, on the other hand, seeks to generalise both of these views, basically saying that a vector can be anything where there's a sensible notion of adding two vectors, and multiplying a vector by a number, operations that I'll talk about later on in this video. The details of this view are rather abstract, and I actually think it's healthy to ignore it until the last video of this series, favoring a more concrete setting in the interim, but the reason that I bring it up here is that it hints at the fact that ideas of vector addition and multiplication by numbers will play an important role throughout linear algebra.

> NOTE:
>
> 一、下面是一点翻译:
>
> "这种观点的细节相当抽象，我认为在本系列的最后一个视频之前忽略它是健康的，在此期间更倾向于更具体的背景"

## 统一的看待vector的角度:  coordinate system(坐标系)

But before I talk about those operations, let's just settle in on a specific thought to have in mind when I say the word "vector".

Given the geometric focus that I'm shooting for here, whenever I introduce a new topic involving vectors, I want you to first think about an arrow—and specifically, think about that arrow inside a **coordinate system**, like the x-y plane, with its tail sitting at the origin(坐标原点). This is a little bit different from the physics student perspective, where vectors can freely sit anywhere they want in space. In linear algebra, it's almost always the case that your vector will be rooted at the origin. Then, once you understand a new concept in the context of arrows in space, we'll translate it over to the list-of-numbers point-of-view, which we can do by considering the coordinates of the vector.

> NOTE:
>
> 一、翻译如下:
>
> "这与物理专业学生的看法略有不同，因为在他们眼中，向量可以在空间中自由落脚，但是在线性代数中，向量经常以原点作为起点。一旦你理解了“向量是空间中的箭头”这种观点，我们就来看看“向量是有序的数字列表”这种观点，我们可以通过向量坐标来理解它。"
>

Now while I'm sure that many of you are familiar with this coordinate system, it's worth walking through explicitly, since this is where all of the important back-and-forth happens between the two perspectives of linear algebra.

> NOTE:
>
> 一、翻译如下:
>
> "我很清楚，你们当中的大部分都已经很熟悉坐标系这个概念了，但是这也值得再详细叙述一遍，因为这两种观点之间的碰撞，恰恰形成了线性代数中的重要概念"
>

Focusing our attention on two dimensions for the moment, you have a horizontal line, called the x-axis, and a vertical line, called the y-axis. The place where they intersect is called the origin, which you should think of as the center of space and the root of all vectors.

After choosing an arbitrary length to represent 1, you make tick-marks on each axis to represent this distance.

When I want to convey the idea of 2-D space as a whole, which you'll see comes up a lot in these videos, I'll extend these tick-marks to make grid-lines, but right now they'll actually get a little bit in the way.

The coordinates of a vector is a pair of numbers that basically give instructions for how to get from the tail of that vector—at the origin—to its tip. The first number tells you how far to walk along the x-axis—positive numbers indicating rightward motion, negative numbers indicating leftward motion—and the second number tell you how far to walk parallel to the y-axis after that—positive numbers indicating upward motion, and negative numbers indicating downward motion.

> NOTE:
>
> 一、从原点出发如何到达vector的tail

To distinguish vectors from **points**, the convention is to write this pair of numbers vertically with square brackets around them.

Every pair of numbers gives you one and only one vector, and every vector is associated with one and only one pair of numbers.

What about in three dimensions? Well, you add a third axis, called the z-axis, which is perpendicular to both the x- and y-axes, and in this case each vector is associated with an ordered triplet of numbers: the first tells you how far to move along the x-axis, the second tells you how far to move parallel to the y-axis, and the third one tells you how far to then move parallel to this new z-axis.

Every triplet of numbers gives you one unique vector in space, and every vector in space gives you exactly one triplet of numbers.

So back to vector addition, and multiplication by numbers.

After all, every topic in linear algebra is going to center around these two operations.

Luckily, each one is pretty straightforward to define.

## Vector addition

Let's say we have two vectors, one pointing up, and a little to the right, and the other one pointing right, and down a bit.

To add these two vectors, move the second one so that its tail sits at the tip of the first one; then if you draw a new vector from the tail of the first one to where the tip of the second one now sits, that new vector is their sum.

This definition of addition, by the way, is pretty much the only time in linear algebra where we let vectors stray away from the origin.

> NOTE:
>
> 一、翻译如下:
>
> "顺便一提，这个向量加法的定义差不多是线性代数中唯一允许向量离开原点的情形"

### 对vector addition对解释

Now why is this a reasonable thing to do?—Why this definition of addition and not some other one?

Well the way I like to think about it is that each vector represents a certain movement—a step with a certain distance and direction in space.

If you take a step along the first vector, then take a step in the direction and distance described by the second vector, the overall effect is just the same as if you moved along the sum of those two vectors to start with.

You could think about this as an extension of how we think about adding numbers on a number line.

> NOTE: 
>
> 一、将向量加法和实数加法进行类比

One way that we teach kids to think about this, say with 2+5, is to think of moving 2 steps to the right, followed by another 5 steps to the right. The overall effect is the same as if you just took 7 steps to the right.

In fact, let's see how vector addition looks numerically.

The first vector here has coordinates (1,2), and the second one has coordinates (3,-1).

When you take the vector sum using this tip-to-tail method, you can think of a four-step path from the origin to the tip of the second vector: "walk 1 to the right, then 2 up, then 3 to the right, then 1 down."

Re-organising these steps so that you first do all of the rightward motion, then do all of the vertical motion, you can read it as saying, "first move 1+3 to the right, then move 2+(-1) up," so the new vector has coordinates `1+3` and `2+(-1)`.

In general, vector addition in this list-of-numbers conception looks like matching up their terms, and adding each one together.

## Vector multiplication by a number

The other fundamental vector operation is multiplication by a number.

Now this is best understood just by looking at a few examples. If you take the number 2, and multiply it by a given vector, it means you stretch out that vector so that it's 2 times as long as when you started.

If you multiply that vector by, say, 1/3, it means you squish it down so that it's 1/3 of the original length.

When you multiply it by a negative number, like -1.8, then the vector first gets flipped around, then stretched out by that factor of 1.8.

This process of stretching or squishing or sometimes reversing the direction of a vector is called "scaling", and whenever you catch a number like 2 or 1/3 or -1.8 acting like this—scaling some vector—you call it a "scalar".

In fact, throughout linear algebra, one of the main things that numbers do is scale vectors, so it's common to use the word "scalar" pretty much interchangeably with the word "number".

Numerically, stretching out a vector by a factor of, say, 2, corresponds to multiplying each of its components by that factor, 2, so in the conception of vectors as lists of numbers, multiplying a given vector by a scalar means multiplying each one of those components by that scalar.

## 总结

You'll see in the following videos what I mean when I say that linear algebra topics tend to revolve around these two fundamental operations: vector addition, and scalar multiplication; and I'll talk more in the last video about how and why the mathematician thinks only about these operations, independent and abstracted away from however you choose to represent vectors.

> NOTE:
>
> 一、在接下来的视频中，你就会明白我之前所说的"线性代数围绕两种基本运算：向量加法与向量数乘”究竟是什么意思了"，我也会在最后一期视频中更详细地讨论为什么数学家只考虑这两种运算，并且又是如何将它们抽象独立出来，不管你选什么代表向量都与之无关
>

In truth, it doesn't matter whether you think about vectors as fundamentally being arrows in space—like I'm suggesting you do—that happen to have a nice numerical representation, or fundamentally as lists of numbers that happen to have a nice geometric interpretation.The usefulness of linear algebra has less to do with either one of these views than it does with the ability to translate back and forth between them. It gives the data analyst a nice way to conceptualise many lists of numbers in a visual way, which can seriously clarify patterns in data, and give a global view of what certain operations do, and on the flip side, it gives people like physicists and computer graphics programmers a language to describe space and the manipulation of space using numbers that can be crunched and run through a computer. When I do math-y animations, for example I start by thinking about what's actually going on in space, and then get the computer to represent things numerically, thereby figuring out where to place the pixels on the screen, and doing that usually relies on a lot of linear algebra understanding.

> NOTE:
>
> 一、翻译如下:
>
> "实际上无论你怎么看待向量都无所谓，或把向量看作空间中的箭头 就像我建议你做的，这种观点恰好有漂亮的数值表示与之对应；或把向量看作数字列表，这种观点又恰好有漂亮的几何意义与之对应；线性代数的效用很少体现在这些观点的其中一个上，而是更多地体现在它能够在这些观点中相互转化。线性代数为数据分析提供了一条将大量数据列表概念化、可视化的渠道，它让数据样式变得非常明晰，并让你大致了解特定运算的意义；另一方面，线性代数给物理学家和计算机图形程序员提供了一种语言，让他们通过计算机能处理的数字来描述并操纵空间，举个例子，当我制作这些动画时，我首先考虑空间中究竟发生了什么，然后在计算机上用数字代表这些变化，从而计算出在屏幕上的哪些地方放置像素，完成这些工作通常需要依靠对线性代数的深厚理解才能完成。"
>

So there are your vector basics, and in the next video I'll start getting into some pretty neat concepts surrounding vectors, like span, bases, and linear dependence.

See you then!

Captioned by Navjivan Pal