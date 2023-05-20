# The determinant | Chapter 6, Essence of linear algebra

https://www.youtube.com/watch?v=Ip3X9LOh2dk&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=6

https://www.bilibili.com/video/BV1ys411472E?p=7



So, moving forward I will be assuming you have a visual understandingof **linear transformations** and how they're represented with matrices the way I have been talking about in the last few videos.



If you think about a couple of these linear transformations you might notice how some of them seem to stretch space out while others squish it on in. One thing that turns out to be pretty useful to understanding one of these transformations is to measure exactly how much it stretches or squishes things. More specifically to measure the factor by which the given region increases or decreases.

## example 1

For example look at the matrix with the columns 3, 0 and 0, 2 It scales i-hat by a factor of 3 and scales j-hat by a factor of 2 Now, if we focus our attention on the one by one square whose bottom sits on i-hat and whose left side sits on j-hat. After the transformation, this turns into a 2 by 3 rectangle. Since this region started out with area 1, and ended up with area 6 we can say the linear transformation has scaled it's area by a factor of 6.

## example 2

Compare that to a shear whose matrix has columns 1, 0 and 1, 1. Meaning, i-hat stays in place and j-hat moves over to 1, 1. That same unit square determined by i-hat and j-hat gets slanted and turned into a parallelogram(平行四边形). But, the area of that parallelogram is still 1 since it's base and height each continue to each have length 1. So, even though this transformation smushes things about it seems to leave areas unchanged.



## 规律

At least, in the case of that one unit square. Actually though if you know how much the area of that one single unit square changes it can tell you how any possible region in space changes.

For starters notice that whatever happens to one square in the grid has to happen in any other square in the grid, no matter the size. This follows from the fact that grid lines remain parallel and evenly spaced. Then, any shape that is not a grid square can be approximated by grid squares really well. With arbitrarily good approximations if you use small enough grid squares. So, since the areas of all those tiny grid squares are being scaled by some single amount the area of the blob as a whole will also be scaled also by that same single amount.

## 2 dimension determinant

This very special scaling factor the factor by which a linear transformation changes any area is called the determinant of that transformation.

I'll show how to compute the determinate of a transformation using it's matrix later on in the video but understanding what it is, trust me, much more important than understanding the computation.

For example the determinant of a transformation would be 3 if that transformation increases the area of the region by a factor of 3.

The determinant of a transformation would be 1/2 if it squishes down all areas by a factor of 1/2. And, the determinant of a 2-D transformation is 0 if it squishes all of space onto a line. Or, even onto a single point. Since then, the area of any region would become 0.



That last example proved to be pretty important it means checking if the determinant of a given matrix is 0 will give away if computing weather or not the transformation associated with that matrix squishes everything into a smaller dimension. You will see in the next few videos why this is even a useful thing to think about. But for now, I just want to lay down all of
the visual intuition which, in and of itself, is a beautiful thing to think about.

> NOTE:
>
> 一、降维
>
> 二、第二句话的意思是: "但是就现在而言，我只想让你留下直观的印象，这种直觉本身也是非常美妙的"
>



Ok, I need to confess(承认) that what I've said so far is not quite right. The full concept of the **determinant** allows for negative values. But, what would scaling an area by a negative amount even mean? This has to do with the idea of **orientation**. For example notice how this transformation gives the sensation(感觉) of flipping space over(翻转). If you were thinking of 2-D space as a sheet of paper a transformation like that one seems to turn over that sheet onto the other side. Any transformations that do this are said to "invert the orientation of space."

> NOTE:
>
> 一、翻译如下:
>
> 举个例子，注意这个变换在感觉上将整个平面翻转了，如果你将二维空间想象为一张纸，这个变换像是将纸翻转到了另一面，我们称类似这样的"变换改变了空间的定向"
>



Another way to think about it is in terms of i-hat and j-hat. Notice that in their starting positions, j-hat is to the left of i-hat. If, after a transformation, j-hat is now on the right of i-hat the orientation of space has been inverted.

Whenever this happens whenever the orientation of space is inverted the determinant will be negative.

The absolute value of the determinant though still tells you the factor by which areas have been scaled.

For example the matrix with columns 1, 1 and 2, -1 encodes a transformation that has determinant Ill just tell you -3. And what this means is that, space gets flipped over and areas are scaled by a factor of 3. 

So why would this idea of a negative area scaling factor be a natural way to describe orientation flipping? Think about the seres of transformations you get by slowly letting i-hat get closer and closer to j-hat.

As i-hat gets closer all the areas in space are getting squished more and more meaning the determinant approaches 0. once i-hat lines up perfectly with j-hat, the determinant is 0. Then, if i-hat continues the way it was going doesn't it kinda feel natural for the determinant to keep decreasing into the negative numbers?

## 3 dimension determinant

So, that is the understanding of determinants in 2 dimensions what do you think it should mean for 3 dimensions?

It [determinant of 3x3 matrix] also tells you how much a transformation scales things but this time it tells you how much volumes get scaled.

Just as in 2 dimensions where this is easiest to think about by focusing on one particular square with an area 1 and watching only what happens to it in 3 dimensions it helps to focus your attention on the specific 1 by 1 by 1 cube whose edges are resting on the basis vectors i-hat, j-hat, and k-hat.

After the transformation that cube might get warped into some kind of slanty slanty cube this shape by the way has the best name ever parallelepiped.

A name made even more delightful when your professor has a nice thick Russian accent.

Since this cube starts out with a volume of 1 and the determinant gives the factor by which any volume is scaled you can think of the determinant as simply being the volume of that parallelepiped that the cube turns into.

A determinate of 0 would mean that, all of space is squished onto something with 0 volume meaning ether a flat plane, a line, or in the most extreme case onto a single point.

Those of you who watched chapter 2 will recognize this as meaning that the columns of the matrix are linearly dependent.

Can you see why? What about negative determinants? What should that mean for 3 dimensions? One way to describe orientation in 3-D is with the right hand rule.

Point the forefinger of your right hand in the direction of i-hat stick out your middle finger in the direction of j-hat and notice how when you point your thumb up it is in the direction of k-hat.

If you can still do that after the transformation orientation has not changed and the determinant is positive.

Otherwise if after the transformation it only makes since to do that with your left hand orientation has been flipped and the determinant is negative.

## How to compute the determinant?

So if you haven't seen it before you are probably wondering by now "How do you actually compute the determinant?"

For a 2 by 2 matrix with entries a, b, c, d the formula is `(a * d) - (b * c)`.

Here's part of an intuition for where this formula comes from lets say the terms b and c both happed to be 0. Then the term a tells you how much i-hat is stretched in the x direction and the term d tells you how much j-hat is stretched in the y direction.

So, since those other terms are 0 it should make sense that `a * d` gives the area of the rectangle that our favorite unit square turns into. Kinda like the 3, 0, 0, 2 example from earlier. even if only one of b or c are 0 you'll have a parallelogram with a base a and a height d.

So, the area should still be a times d.

Loosely speaking if both b and c are non-0 then that `b * c` term tells you how much this parallelogram is stretched or squished in the diagonal direction.

For those of you hungry for a more precipice description of this `b * c` term here's a helpful diagram if you would like to pause and ponder.

Now if you feel like computing determinants by hand is something that you need to know the only way to get it down is to just practice it with a few.

There's not really that much I can say or animate that is going to drill in the computation.

This is all tripply true for 3-rd dimensional determinants.

There is a formula [for that] and if you feel like that is something you need to know you should practice with a few matrices or you know, go watch Sal Kahn work through a few.

Honestly though I don't think those computations fall within the essence of linear algebra but I definitely think that knowing what the determinate represents falls within that essence.

Here's kind of a fun question to think about before the next video if you multiply 2 matrices together the determinant of the resulting matrix is the same as the product of the determinants of the original two matrices if you tried to justify this with numbers it would take a really long time but see if you can explain why this makes sense in just one sentence.

Next up I'll be relating the idea of linear transformations covered so far to one of the areas where linear algebra is most useful **linear systems of equations**

see ya then!
