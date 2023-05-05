# Linear combinations, span, and basis vectors | Chapter 2, Essence of linear algebra

https://www.youtube.com/watch?v=k7RM-ot2NWY&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=2

https://www.bilibili.com/video/BV12s411k7S5/?spm_id_from=333.788.recommend_more_video.-1

## basis vectors

In the last video, along with the ideas of **vector addition** and **scalar multiplication**, I described vector coordinates, where's this back and forth between, for example, pairs of numbers and two-dimensional vectors.

Now, I imagine that vector coordinates were already familiar to a lot of you, but there's another kind of interesting way to think about these coordinates, which is pretty central to linear algebra.

When you have a pair of numbers that's meant to describe a vector, like [3, -2], I want you to think about each coordinate as a scalar, meaning, think about how each one stretches or squishes vectors,

In the xy-coordinate system, there are two very special vectors:

the one pointing to the right with length 1, commonly called "i-hat", or the unit vector in the x-direction, and 

the one pointing straight up, with length 1, commonly called "j-hat", or the unit vector in the y-direction.

Now, think of:

the x-coordinate of our vector as a scalar that scales i-hat, stretching it by a factor of 3, and 

the y-coordinate as a scalar that scales j-hat, flipping it and stretching it by a factor of 2.

In this sense, the vectors that these coordinates describe is the sum of two scaled vectors. That's a surprisingly important concept, this idea of adding together two scaled vectors.

> NOTE:
>
> 一、上面所描述的其实就是span的概念。

Those two vectors, i-hat and j-hat, have a special name, by the way.

Together, they're called the basis of a coordinate system, What this means, basically, is that when you think about coordinates as scalars, the **basis vectors** are what those scalars actually, you know, scale. There's also a more technical definition, but I'll get to that later.

By framing our coordinate system in terms of these two special basis vectors, it raises a pretty interesting, and subtle, point:

We could've chosen different basis vectors, and gotten a completely reasonable, new coordinate system.

For example, take some vector pointing up and to the right, along with some other vector pointing down and to the right, in some way.

Take a moment to think about all the different vectors that you can get by choosing two scalars, using each one to scale one of the vectors, then adding together what you get.

Which two-dimensional vectors can you reach by altering the choices of scalars?

The answer is that you can reach every possible two-dimensional vector, and I think it's a good puzzle to contemplate why.

A new pair of **basis vectors** like this still gives us a valid way to go back and forth between pairs of numbers and **two-dimensional vectors**, but the association is definitely different from the one that you get using the more **standard basis of i-hat and j-hat**.

This is something I'll go into much more detail on later, describing the exact relationship between different coordinate systems, but for right now, I just want you to appreciate the fact that any time we describe vectors numerically, it depends on an implicit choice of what **basis vectors** we're using.

## linear combination

So any time that you're scaling two vectors and adding them like this, it's called a **linear combination** of those two vectors.

## Where does this word "linear" come from?

Where does this word "linear" come from? Why does this have anything to do with lines?

Well, this isn't the etymology, but one way I like to think about it is that if you fix one of those scalars, and let the other one change its value freely, the tip of the resulting vector draws a straight line.

> NOTE:
>
> 一、"etymology"的意思是 "词源学"
>
> 二、"tip"的意思是 "末端"

Now, if you let both scalars range freely, and consider every possible vector that you can get, there are two things that can happen: For most pairs of vectors, you'll be able to reach every possible point in the plane; every two-dimensional vector is within your grasp.

## basis vectors 共线

However, in the unlucky case where your two original vectors happen to line up, the tip of the resulting vector is limited to just this single line passing through the origin.

Actually, technically there's a third possibility too: both your vectors could be zero, in which case you'd just be stuck at the origin.

## span of two vectors

Here's some more terminology: The set of all possible vectors that you can reach with a **linear combination** of a given pair of vectors is called the **span of those two vectors**.

So, restating what we just saw in this lingo, the span of most pairs of 2-D vectors is all vectors of 2-D space, but when they line up, their span is all vectors whose tip sits on a certain line.

Remember how I said that linear algebra revolves around vector addition and scalar multiplication? Well, the span of two vectors is basically a way of asking, "What are all the possible vectors you can reach using only these two fundamental operations, **vector addition** and **scalar multiplication**?"

## Think about vectors as points

This is a good time to talk about how people commonly think about vectors as points.

It gets really crowded to think about a whole collection of vectors sitting on a line, and more crowded still to think about all
two-dimensional vectors all at once, filling up the plane.

So when dealing with collections of vectors like this, it's common to represent each one with just a point in space. The point at the tip of that vector, where, as usual, I want you thinking about that vector with its tail on the origin. That way, if you want to think about every possible vector whose tip sits on a certain line, just think about the line itself. Likewise, to think about all possible two-dimensional vectors all at once, conceptualize each one as the point where its tip sits. So, in effect, what you'll be thinking about is the infinite, flat sheet of two-dimensional space itself, leaving the arrows out of it.

> NOTE:
>
> 一、"flat sheet"的含义是"平面"

In general, if you're thinking about a vector on its own, think of it as an arrow, and if you're dealing with a collection of vectors, it's convenient to think of them all as points.

> NOTE:
>
> 一、上面这段话是作者提供的一种看待vector的思路:
>
> 1、 if you're thinking about a vector on its own, think of it as an arrow
>
> 2、if you're dealing with a collection of vectors, it's convenient to think of them all as points

So, for our span example, the span of most pairs of vectors ends up being the entire infinite sheet of two-dimensional space, but if they line up, their span is just a line.

## Span in three-dimensional space

The idea of span gets a lot more interesting if we start thinking about vectors in three-dimensional space.

For example, if you take two vectors, in 3-D space, that are not pointing in the same direction, what does it mean to take their span?

Well, their span is the collection of all possible linear combinations of those two vectors, meaning all possible vectors you get by scaling each of the two of them in some way, and then adding them together.

You can kind of imagine turning two different knobs(把手) to change the two scalars defining the linear combination, adding the scaled vectors and following the tip of the resulting vector. That tip will trace out some kind of **flat sheet**, cutting through the origin of three-dimensional space.

> NOTE:
>
> 一、"flat sheet"的意思是"水平面"

This flat sheet is the span of the two vectors, or more precisely, the set of all possible vectors whose tips sit on that flat sheet is the span of your two vectors.

Isn't that a beautiful mental image? So what happens if we add a third vector and consider the span of all three of those guys?

A **linear combination** of three vectors is defined pretty much the same way as it is for two; you'll choose three different scalars, scale each of those vectors, and then add them all together. And again, the span of these vectors is the set of all possible linear combinations.

Two different things could happen here: If your third vector happens to be sitting on the span of the first two, then the span doesn't change; you're sort of trapped on that same flat sheet. In other words, adding a scaled version of that third vector to the linear combination doesn't really give you access to any new vectors.

But if you just randomly choose a third vector, it's almost certainly not sitting on the span of those first two. Then, since it's pointing in a separate direction, it unlocks access to every possible three-dimensional vector.

One way I like to think about this is that as you scale that new third vector, it moves around that span sheet of the first two, sweeping it through all of space.

Another way to think about it is that you're making full use of the three, freely-changing scalars that you have at your disposal to access the full three dimensions of space.

> NOTE:
>
> 一、翻译如下:
>
> 另一种思考方式是，你完全利用了你掌握的自由变化的三个标量，从而得到空间中所有的三维向量
>

## linearly dependent、linearly independent

Now, in the case where the third vector was already sitting on the span of the first two, or the case where two vectors happen to line up, we want some terminology to describe the fact that at least one of these vectors is redundant—not adding anything to our span.

Whenever this happens, where you have multiple vectors and you could remove one without reducing the span, the relevant terminology is to say that they are "**linearly dependent**".

Another way of phrasing(表达) that would be to say that one of the vectors can be expressed as a linear combination of the others since it's already in the span of the others.

On the other hand, if each vector really does add another dimension to the span, they're said to be "linearly independent".

So with all of that terminology, and hopefully with some good mental images to go with it, let me leave you with puzzle before we go.

The technical definition of a basis of a space is a set of linearly independent vectors that span that space.

Now, given how I described a basis earlier, and given your current understanding of the words "span" and "linearly independent", think about why this definition would make sense.

In the next video, I'll get into matrices and transforming space.

See you then!