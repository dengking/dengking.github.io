# Three-dimensional linear transformations | Chapter 5, Essence of linear algebra



https://www.youtube.com/watch?v=rHLEWRxRGiM&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=5



https://www.bilibili.com/video/BV1ys411472E?p=6



In the last two videos I talked about linear transformations and matrices, but, I only showed the specific case of transformations that take two-dimensional vectors to other two-dimensional vectors. In general throughout the series we'll work mainly in two dimensions.

Mostly because it's easier to actually see on the screen and wrap your mind around, but, more importantly than that once you get all the core ideas in two dimensions they carry over pretty seamlessly to higher dimensions.

## three-dimensional linear transformations

Nevertheless it's good to peak our heads outside of flatland now and then to... you know see what it means to apply these
ideas in more than just those two dimensions. For example, consider a linear transformation with three-dimensional vectors as inputs and three-dimensional vectors as outputs.

We can visualize this by smooshing around all the points in three-dimensional space, as represented by a grid, in such a
way that keeps the grid lines parallel and evenly spaced and which fixes the origin in place.

And just as with two dimensions, every point of space that we see moving around is really just a proxy for a vector who
has its tip at that point, and what we're really doing is thinking about **input vectors** *moving over* to their corresponding **outputs**, and just as with two dimensions, one of these transformations is completely described by where the **basis vectors** go.

But now, there are three standard basis vectors that we typically use: the unit vector in the x-direction, i-hat; the unit vector in the y-direction, j-hat; and a new guy—the unit vector in the z-direction called k-hat.

In fact, I think it's easier to think about these transformations by only following those **basis vectors** since, the for 3-D grid representing all points can get kind of messy By leaving a copy of the original axes in the background, we can think about the coordinates of where each of these three basis vectors lands.

Record the coordinates of these three vectors as the columns of a 3×3 matrix. This gives a matrix that completely describes the transformation using only nine numbers.



As a simple example, consider, the **transformation** that rotate space 90 degrees around the y-axis. So that would mean that it takes i-hat to the coordinates [0,0,-1] on the z-axis, it doesn't move j-hat so it stays at the coordinates [0,1,0] and then k-hat moves over to the x-axis at [1,0,0].



Those three sets of coordinates become the columns of a matrix that describes that rotation transformation. To see where vector with coordinates XYZ lands the reasoning is almost identical to what it was for two dimensions—each of those coordinates can be thought of as instructions for how to scale each basis vector so that they add together to get your vector.



And the important part just like the 2-D case is that this scaling and adding process works both before and after the transformation. So, to see where your vector lands you multiply those coordinates by the corresponding columns of the matrix
and then you add together the three results.

Multiplying two matrices is also similar whenever you see two 3×3 matrices getting multiplied together you should imagine first applying the transformation encoded by the right one then applying the transformation encoded by the left one.

It turns out that 3-D matrix multiplication is actually pretty important for fields like computer graphics and robotics—since things like rotations in three dimensions can be pretty hard to describe, but, they're easier to wrap your mind around if you can break them down as the composition of separate easier to think about rotations

Performing this matrix multiplication numerically, is, once again pretty similar to the two-dimensional case.

In fact a good way to test your understanding of the last video would be to try to reason through what specifically this matrix multiplication should look like thinking closely about how it relates to the idea of applying two successive of transformations in space.

In the next video I'll start getting into the determinant.