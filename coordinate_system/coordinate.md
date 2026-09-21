
# Polar coordinate

In the polar coordinate system, a point is represented as $(r, \theta)$. This allows us to intuitively grasp a vector's magnitude and direction compared to the Cartesian system. A key advantage is that multiplication and division are significantly simpler: to multiply two vectors, we simply multiply their magnitudes and add their angles. This makes it easy to scale and rotate vectors. However, for addition and subtraction, polar coordinates are less convenient. In most cases, we first convert polar coordinates into Cartesian coordinates, perform the operation, and then convert the result back into polar form.

## Kinematics chain and polar representation

The polar coordinate system is highly advantageous for vector multiplication, which fundamentally represents scaling and rotation. This characteristic allows us to model body movements—specifically joint rotations—more efficiently. Since joint movements are interconnected like a chain, the orientation of each segment is determined by the cumulative rotation of the preceding joints. Thus, the position of any point on the body can be represented as a series of nested rotations in polar form.

In a 2-link arm system, where $p_1$ is the first link and $p_2$ is the second link relative to $p_1 $ stretch out about L2, and rotated about $\theta_2$:
- $p_1 = (L_1, \theta_1)$
- $p_2 = (\alpha, \theta_1 + \theta_2)$: Relative vector of the second link, where $\alpha$ represents the stretched length and $\theta_1 + \theta_2$ represents the cumulative orientation.
    - (Note: While the cumulative angle reflects the chain-like rotation, the total displacement from the origin requires summing these vectors in their Cartesian forms.)

# Cartesian coordinate system

A Cartesian coordinate system consists of multiple orthogonal axes used to specify the position of points using tuples, such as $(x, y)$.

## Real number system and Imaginary number system

In the real 2D plane, an equation like $y = e^{x}$ represents a relation between variables, defining a geometric curve made of infinitely many tuples $(x, y)$.

In the complex plane, on the other hand, an individual tuple $(x, y)$ is packaged into a single algebraic object: $z = x + yi$. Don't be confused by the letter $z$—it does not introduce a third dimension; it simply names the 2D tuple $(x, y)$ as a single number equipped with rotational arithmetic rules.

The advantage of using the complex plane is that rotation is remarkably easy to represent. In the real plane, rotating a point by an angle $\theta$ requires cumbersome $2 \times 2$ matrix multiplication:$$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$

For instance, a $+90^\circ$ rotation requires evaluating the matrix with trigonometric values:$$\begin{pmatrix} \cos 90^\circ & -\sin 90^\circ \\ \sin 90^\circ & \cos 90^\circ \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} -y \\ x \end{pmatrix}$$

In the complex plane, however, rotation by any arbitrary angle $\theta$ collapses into simple multiplication by $e^{i\theta} = \cos\theta + i\sin\theta$:
- For a $+90^\circ$ rotation: we simply multiply by $i$ (since $e^{i 90^\circ} = i$): $$z' = z \cdot i = (x + yi)i = -y + xi \iff (-y, x)$$
- For a $+45^\circ$ rotation: we simply multiply by $e^{i 45^\circ} = \frac{\sqrt{2}}{2} + i\frac{\sqrt{2}}{2}$:$$z' = z \cdot e^{i 45^\circ}$$

No matrices or trigonometry additions are needed; rotation is purely an algebraic multiplication.

# Dimension

The minimum number of independent values needed to pinpoint the exact state or position of a system.

## A Common Pitfall: The Word "Independent"

It is easy to get confused by the word "independent."

In everyday math class, time ($t$) is called an "independent variable" because it ticks forward on its own, like an input clock. However, when defining dimension, "independent" does not mean time. Instead, it asks:

"At one frozen moment, how many unrelated numbers do you need to fully describe where or what the object is?"

**The Snapshot Test: What Dimension Truly Means**

Imagine pausing reality and taking a snapshot:

- 1-Dimensional System (A Line):

    Think of a thermometer reading, a bank account balance, or a train locked onto a straight track.To pinpoint the state, you only need one number (e.g., $25^\circ\text{C}$, $\$500$, or kilometer mark $45$).Drawing a chart on 2D graph paper—with time along the bottom and temperature going up—is just a visual record of history. The temperature itself is never moving across a surface; it only moves up and down along a single line.
- 2-Dimensional System (A Surface):

    Think of an ant crawling on a tabletop or a ship on the ocean.Knowing just one number leaves you completely lost. You must provide two separate, independent numbers at the exact same instant (e.g., latitude and longitude, or $x$ and $y$). Changing your left-and-right position tells you nothing about your forward-and-backward position; they are two genuinely independent directions.
    
