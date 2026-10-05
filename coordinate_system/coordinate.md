
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

## The Cartesian Coordinate System and the Notation of Function Values

We commonly represent a function using the familiar notation:$$y = f(x)$$

From the dual perspectives of coordinate geometry and function theory, the role of $y$ often introduces subtle confusion. By definition, the coordinate axes of the Cartesian plane are orthogonal, meaning they represent geometrically independent degrees of freedom—traversing along the $x$-axis has no inherent effect on the $y$-coordinate. In stark contrast, the definition of a function posits that $y$ is strictly dependent on $x$.

To resolve this apparent contradiction, we must distinguish between the geometric space and the algebraic rule:
1. The Coordinate Pair $(x, y)$ as a Geometric Canvas:

    The Cartesian plane $\mathbb{R}^2$ provides a two-dimensional, unconstrained state space defined by two orthogonal, mutually independent axes: an abscissa ($x$) and an ordinate ($y$). Prior to introducing any function, $x$ and $y$ are completely independent variables representing spatial positions.

2. The Output $f(x)$ as an Operational Mapping:

    The symbol $f$ denotes an algorithmic rule or mapping that transforms an input $x$ into a specific value $f(x)$. The function exists purely as an input-output relation and does not inherently require a spatial coordinate system to be defined.

3. The Equation $y = f(x)$ as a Constraint:

    The equal sign in $y = f(x)$ does not declare that $y$ and $f(x)$ are ontologically identical; rather, it acts as an assignment constraint. It dictates that the vertical coordinate $y$ is assigned to match the output value $f(x)$ for each chosen $x$.

By imposing $y = f(x)$, we restrict the two-dimensional freedom of the plane down to a one-dimensional manifold—the curve of the graph. The axes themselves remain orthogonal and independent, but the locus of points that satisfy the relation forms a dependent trajectory within that space.

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

    Think of a thermometer reading, a bank account balance, or a train locked onto a straight track. To pinpoint the state, you only need one number (e.g., $25^\circ\text{C}$, $\$500$, or kilometer mark $45$). Drawing a chart on 2D graph paper—with time along the bottom and temperature going up—is just a visual record of history. The temperature itself is never moving across a surface; it only moves up and down along a single line.
- 2-Dimensional System (A Surface):

    Think of an ant crawling on a tabletop or a ship on the ocean.Knowing just one number leaves you completely lost. You must provide two separate, independent numbers at the exact same instant (e.g., latitude and longitude, or $x$ and $y$). Changing your left-and-right position tells you nothing about your forward-and-backward position; they are two genuinely independent directions.

# Exponential function

## Essential characteristic: Compound Interest limit

The exponential function is defined as the limit of an infinitesimal change multiplied infinitely:$$e^z = \lim_{n \to \infty} \left( 1 + \frac{z}{n} \right)^n$$
- Base state: $1$ (current position/magnitude)
- Step-wise increment: $\frac{z}{n}$ (infinitesimal change per step)
- Multiplier applied at every step: $\left( 1 + \frac{z}{n} \right)$
- Accumulation: Compounded $n$ times as $n \to \infty$

## Real vs. Imaginary compounding: The 90° turn

1. Real compounding: $z = x$ (Linear scaling)
- Step multiplier: $\left( 1 + \frac{x}{n} \right)$
- Direction of increment: The increment $\frac{x}{n}$ points along the same line ($0^\circ$) as the current position.
- Outcome: The magnitude expands or shrinks along a 1D real line.
2. Imaginary compounding: $z = j\omega$ (Uniform circular rotation)
- Step multiplier: $\left( 1 + j\frac{\omega}{n} \right)$
- Direction of increment: Because the imaginary unit $j$ operates as a $90^\circ$ counter-clockwise rotator, the increment $j\frac{\omega}{n}$ is added strictly perpendicular (90°) to the current position vector.
- Why the radius does not grow (Magnitude preservation):
    By the Pythagorean theorem, the magnitude of a single step is:$$\left\vert{} 1 + j\frac{\omega}{n} \right\vert{} = \sqrt{1^2 + \left(\frac{\omega}{n}\right)^2} = \left( 1 + \frac{\omega^2}{n^2} \right)^{1/2}$$

    Compounding this over $n$ steps yields:$$\lim_{n \to \infty} \left\vert{} 1 + j\frac{\omega}{n} \right\vert{}^n = \lim_{n \to \infty} \left( 1 + \frac{\omega^2}{n^2} \right)^{n/2} = e^{\lim\limits_{n \to \infty} \frac{\omega^2}{2n}} = e^0 = \mathbf{1}$$
    - The orthogonal displacement $\frac{\omega}{n}$ is a first-order infinitesimal that contributes directly to angle rotation.
    - The hypotenuse stretch is a second-order infinitesimal $\left(\frac{\omega^2}{n^2}\right)$, which vanishes entirely in the limit.
- Accumulated angle:$$\Theta = \lim_{n \to \infty} n \cdot \arctan\left(\frac{\omega}{n}\right) = \lim_{n \to \infty} n \cdot \frac{\omega}{n} = \boldsymbol{\omega} \text{ [rad]}$$

Core Insight: Infinitely compounding a steering input that is always directed at 90° to the current vector preserves length perfectly, resulting in pure rotation along the unit circle by an arc length of $\omega$.

## Continuous formulation: Instantaneous 90° constraint

The differential equation counterpart makes this geometric orthogonality explicit:$$\frac{d}{dt} e^{j\omega t} = j\omega \cdot e^{j\omega t}$$

Setting $z(t) = e^{j\omega t}$:$$\frac{dz}{dt} = j\omega \cdot z(t)$$
- Position vector $z(t)$: Radial vector from the origin to the current point.
- Velocity vector $\frac{dz}{dt}$: Scaled by $j$, forcing velocity to stay strictly orthogonal (90°) to the position vector at every instant.
- Radius conservation:$$\frac{d}{dt} \vert{}z(t)\vert{}^2 = \frac{dz}{dt}\bar{z} + z\frac{d\bar{z}}{dt} = (j\omega z)\bar{z} + z(-j\omega \bar{z}) = 0$$

## Generalization: $e^s = e^{\sigma + j\omega}$

When decoupled into real and imaginary parts:$$e^s = \underbrace{e^\sigma}_{\text{Real compounding (Magnitude)}} \cdot \underbrace{e^{j\omega}}_{\text{Imaginary compounding (90° Rotation)}} = e^\sigma (\cos\omega + j\sin\omega)$$

- Constant $\sigma$, varying $\omega$:
    - The radial scale factor $e^\sigma$ remains fixed.
    - The continuous $90^{∘}$ orthogonal compounding drives the output point along a circle of radius $e^{σ}$ at an angular rate of 1 rad per unit of ω.