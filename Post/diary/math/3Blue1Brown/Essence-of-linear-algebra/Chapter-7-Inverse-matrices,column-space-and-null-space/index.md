# Inverse matrices, column space and null space | Chapter 7, Essence of linear algebra

https://www.youtube.com/watch?v=uQhTuRlWMxw



As you can probably tell by now, the bulk of this series is on understanding matrix and vector operations through that more visual lens(镜头) of **linear transformations**. This video is no exception, describing the concepts of **inverse matrices**, **column space**, **rank**, and **null space** through that lens.

> NOTE:
>
> 一、翻译如下:
>
> "这个系列的大部分旨在透过直观的线性变换来理解矩阵与向量运算，这个视频也不例外，我们要透过线性变换来了解逆矩阵、列空间、秩和零空间的概念"

A forewarning though: I'm not going to talk about the methods for actually computing these things, and some would argue that that's pretty important. There are a lot of very good resources for learning those methods outside this series.

Keywords: "Gaussian elimination" and "Row echelon form."

I think most of the value that I actually have to add here is on the intuition half. Plus, in practice, we usually get software to compute this stuff for us anyway.

First, a few words on the usefulness of **linear algebra**. By now, you already have a hint for how it's used in describing the the manipulation of space, which is useful for things like **computer graphics** and **robotics**, but one of the main reasons that **linear algebra** is more broadly applicable, and required for just about any technical discipline, is that it lets us solve certain **systems of equations**.

When I say "**system of equations**," I mean you have a list of variables, things you don't know, and a list of equations relating them.

In a lot of situations, those equations can get very complicated, but, if you're lucky, they might take on a certain special form.

Within each equation, the only thing happening to each variable is that it's scaled by some **constant**, and the only thing happening to each of those scaled variables is that they're added to each other. So, no exponents or fancy functions, or multiplying two variables together; things like that.

The typical way to organize this sort of special system of equations is to throw all the variables on the left, and put any lingering constants on the right. It's also nice to vertically line up the common variables, and to do that you might need to throw in some zero coefficients whenever the variable doesn't show up in one of the equations.

This is called a "**linear system of equations**." You might notice that this looks a lot like matrix vector multiplication. In fact, you can package all of the equations together into a single vector equation, where you have the matrix containing all of the constant coefficients, and a vector containing all of the variables, and their matrix vector product equals some different constant vector.

Let's name that constant matrix A, denote the vector holding the variables with a boldface x, and call the constant vector on the right-hand side v. This is more than just a notational trick to get our **system of equations** written on one line. It sheds light on a pretty cool geometric interpretation for the problem. The matrix A corresponds with some **linear transformation**, so solving Ax = v means we're looking for a vector x which, after applying the transformation, lands on v.

> NOTE:
>
> 一、翻译如下: 这不仅仅是将方程组写进一行的书写技巧，它还阐明了这个问题中优美的几何直观部分
>



Think about what's happening here for a moment. You can hold in your head this really complicated idea of multiple variables all intermingling with each other just by thinking about squishing and morphing space and trying to figure out which vector lands on another. Cool, right?

> NOTE:
>
> 一、翻译: 你完全可以只考虑对空间变形，以及变换前后向量的重叠，就将多个未知量相互混合的复杂方程组印入脑中，很酷，对吧？
>

To start simple, let's say you have a system with two equations and two unknowns. This means that the matrix A is a 2x2 matrix, and v and x are each two dimensional vectors. Now, how we think about the solutions to this equation depends on whether the transformation associated with A squishes all of space into a lower dimension, like a line or a point, or if it leaves everything spanning the full two dimensions where it started. In the language of the last video, we subdivide into the case where A has zero determinant, and the case where A has nonzero determinant.

> NOTE:
>
> 一、翻译: 先举一个简单的例子，你有两个方程和两个未知量构成的方程组，意味着A是一个2×2的矩阵，v和x都是二维向量，现在，这个方程的解依赖于矩阵A所代表的变换，是将空间挤压到一条线或一个点等低维空间，还是保持像初始状态一样的完整二维空间
>

In the language of the last video, we subdivide into the case where A has zero determinant, and the case where A has nonzero determinant.

> NOTE:
>
> 一、翻译: "用上期视频中的语言来说，我们将它们分为两种情况：A的行列式为零和A的行列式不为零"
>

Let's start with the most likely case, where the determinant is nonzero, meaning space does not get squished into a zero area region. In this case, there will always be one and only one vector that lands on v, and you can find it by playing the transformation
in reverse.

> NOTE:
>
> 

Following where v goes as we rewind the tape
like this,

you'll find the vector x such that A times
x equals v.

When you play the transformation in reverse,
it actually corresponds to a separate linear

transformation,

commonly called "the inverse of A"

denoted A to the negative one.

For example, if A was a counterclockwise rotation
by 90º

then the inverse of A would be a clockwise
rotation by 90º.

If A was a rightward shear that pushes j-hat
one unit to the right,

the inverse of a would be a leftward shear
that pushes j-hat one unit to the left.

In general, A inverse is the unique transformation
with the property that if you first apply

A,

then follow it with the transformation A inverse,

you end up back where you started.

Applying one transformation after another
is captured algebraically with matrix multiplication,

so the core property of this transformation
A inverse is that A inverse times A

equals the matrix that corresponds to doing
nothing.

The transformation that does nothing is called
the "identity transformation."

It leaves i-hat and j-hat each where they
are, unmoved,

so its columns are one, zero, and zero, one.

Once you find this inverse, which, in practice,
you do with a computer,

you can solve your equation by multiplying
this inverse matrix by v.

And again, what this means geometrically is
that you're playing the transformation in

reverse, and following v.

This nonzero determinant case, which for a
random choice of matrix is by far the most

likely one,

corresponds with the idea that if you have
two unknowns and two equations,

it's almost certainly the case that there's
a single, unique solution.

This idea also makes sense in higher dimensions,

when the number of equations equals the number
of unknowns.

Again, the system of equations can be translated
to the geometric interpretation

where you have some transformation, A,

and some vector, v,

and you're looking for the vector x that lands
on v.

As long as the transformation A doesn't squish
all of space into a lower dimension,

meaning, its determinant is nonzero,

there will be an inverse transformation, A
inverse,

with the property that if you first do A,

then you do A inverse,

it's the same as doing nothing.

And to solve your equation, you just have
to multiply that reverse transformation matrix

by the vector v.

But when the determinant is zero, and the
transformation associated with this system

of equations

squishes space into a smaller dimension, there
is no inverse.

You cannot un-squish a line to turn it into
a plane.

At least, that's not something that a function
can do.

That would require transforming each individual
vector

into a whole line full of vectors.

But functions can only take a single input
to a single output.

Similarly, for three equations in three unknowns,

there will be no inverse if the corresponding
transformation

squishes 3D space onto the plane,

or even if it squishes it onto a line, or
a point.

Those all correspond to a determinant of zero,

since any region is squished into something
with zero volume.

It's still possible that a solution exists
even when there is no inverse,

it's just that when your transformation squishes
space onto, say, a line,

you have to be lucky enough that the vector
v lives somewhere on that line.

You might notice that some of these zero determinant
cases feel a lot more restrictive than others.

Given a 3x3 matrix, for example, it seems
a lot harder for a solution to exist

when it squishes space onto a line compared
to when it squishes things onto a plane,

even though both of those are zero determinant.

We have some language that's a bit more specific
than just saying "zero determinant."

When the output of a transformation is a line,
meaning it's one-dimensional,

we say the transformation has a "rank" of
one.

If all the vectors land on some two-dimensional
plane,

We say the transformation has a "rank" of
two.

So the word "rank" means the number of dimensions
in the output of a transformation.

For instance, in the case of 2x2 matrices,
rank 2 is the best that it can be.

It means the basis vectors continue to span
the full two dimensions of space, and the

determinant is nonzero.

But for 3x3 matrices, rank 2 means that we've
collapsed,

but not as much as they would have collapsed
for a rank 1 situation.

If a 3D transformation has a nonzero determinant,
and its output fills all of 3D space,

it has a rank of 3.

This set of all possible outputs for your
matrix,

whether it's a line, a plane, 3D space, whatever,

is called the "column space" of your matrix.

You can probably guess where that name comes
from.

The columns of your matrix
tell you where the basis vectors land,

and the span of those transformed basis
vectors gives you all possible outputs.

In other words, the column space is the
span of the columns of your matrix.

So, a more precise definition of rank
would be that

it's the number of dimensions in the column
space.

When this rank is as high as it can be,

meaning it equals the number of columns, we
call the matrix "full rank."

Notice, the zero vector will always be
included in the column space,

since linear transformations must keep the
origin fixed in place.

For a full rank transformation, the only vector
that lands at the origin is the zero vector

itself,

but for matrices that aren't full rank,
which squish to a smaller dimension,

you can have a whole bunch of vectors that
land on zero.

If a 2D transformation squishes space onto
a line, for example,

there is a separate line in a different direction,

full of vectors that get squished onto the
origin.

If a 3D transformation squishes space onto
a plane,

there's also a full line of vectors that
land on the origin.

If a 3D transformation squishes all the space
onto a line,

then there's a whole plane full of vectors
that land on the origin.

This set of vectors that lands on the
origin is called the "null space" or the "kernel"

of your matrix.

It's the space of all vectors that become
null,

in the sense that they land on the zero vector.

In terms of the linear system of
equations, when v happens to be the zero vector,

the null space gives you all of
the possible solutions to the equation.

So that's a very high-level overview

of how to think about linear systems of equations
geometrically.

Each system has
some kind of linear transformation associated

with it,

and when that
transformation has an inverse,

you can use that inverse to solve your system.

Otherwise, the idea of column space lets
us understand when a solution even exists,

and the idea of a null space
helps us to understand what the set of

all possible solutions can look like.

Again there's a lot that I haven't
covered here,

most notably how to compute these things.

I also had to limit my scope to examples where
the number of equations

equals the number of unknowns.

But the goal here is not to try to teach everything;

it's that you come away with
a strong intuition for inverse matrices, column

space, and null space,

and that those intuitions make any future
learning that you do more fruitful.

Next video, by popular request, will be a
brief footnote about nonsquare matrices.

Then, after that, I'm going to give you my
take on dot products,

and something pretty cool that
happens when you view them

under the light of linear transformations.

See you then!