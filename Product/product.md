
# Inner Product

Inner product measures how much one vector contributes to another. To do this, it sums up the products of the vectors' components along each axis.

Interestingly, this axis-wise summation directly corresponds to the geometric angle between two vectors. It reveals how closely their directions align without needing complex trigonometry.

## Definition

- Algebric definition: $ \mathbf{a} \cdot \mathbf{b} = \sum_{i=1}^{n}a_ib_i $
- Geometric definition: $ \mathbf{a} \cdot \mathbf{b} = ||\mathbf{a}||||\mathbf{b}||\cos \theta $

## Equivalence between Algebric & Geometric definition

To show that these two definitions are equivalent, we use a triangle formed by vectors $\mathbf{a}$, $\mathbf{b}$, and $\mathbf{c} = \mathbf{a} - \mathbf{b}$.

According to the Law of Cosines:$$||\mathbf{c}||^2 = ||\mathbf{a}||^2 + ||\mathbf{b}||^2 - 2||\mathbf{a}||||\mathbf{b}||\cos \theta$$By the Geometric Definition, the last term $2||\mathbf{a}||||\mathbf{b}||\cos \theta$ is equal to $2(\mathbf{a} \cdot \mathbf{b}_{geo})$. Thus:$$||\mathbf{c}||^2 = ||\mathbf{a}||^2 + ||\mathbf{b}||^2 - 2(\mathbf{a} \cdot \mathbf{b}_{geo}) \quad \dots \text{ (Eq. 1)}$$

Now, using the Algebraic properties of the norm ($||\mathbf{x}||^2 = \mathbf{x} \cdot \mathbf{x}$):

$$\begin{aligned}||\mathbf{c}||^2 = ||\mathbf{a} - \mathbf{b}||^2 & = (\mathbf{a} - \mathbf{b}) \cdot (\mathbf{a} - \mathbf{b}) \\ 
    & = \mathbf{a} \cdot \mathbf{a} - 2(\mathbf{a} \cdot \mathbf{b}{alg}) + \mathbf{b} \cdot \mathbf{b} \\
    & = ||\mathbf{a}||^2 + ||\mathbf{b}||^2 - 2(\mathbf{a} \cdot \mathbf{b}_{alg}) \quad \dots \text{ (Eq. 2)}\end{aligned}$$
    
Comparing (Eq. 1) and (Eq. 2), we can conclude:$$\mathbf{a} \cdot \mathbf{b}_{geo} = \mathbf{a} \cdot \mathbf{b}_{alg}$$


# Outer Product

While the inner product collapses two vectors into a single measure of alignment, the outer product expands them into a matrix that captures every possible interaction between their components.

Grassmann invented the outer product to treat geometric areas and volumes as calculable algebraic entities. He wanted a way to 'extend' (expand) dimensions—moving from 1D vectors to 2D planes—so that spatial relationships could be solved through pure calculation rather than drawing.
- Geometric areas as "Calculable algebraic entities"

    Before Grassmann, area was merely a 'result' drawn in a geometric figure. However, he wanted to transform it into an independent, calculable entity, just like the variables $x$, $y$, and $z$.
- 'Expend' dimensions

    He set an operational rule for expanding dimensions:
    - First, when we connect two points, it becomes a vector (a 1D line).
        - Note: A position vector is a vector with its tail fixed at the origin.
    - Second, when we take the outer product of a line and a line, it becomes a plane (2D).
    - Third, when we take the outer product of a plane and a line, it becomes a volume (3D).

    In this way, the outer product acts as a 'dimension elevator,' stepping up dimensions one by one. This is why his work is famously known as the Extension Theory.

- Pure calculation rather than drawing
    
    Before Grassmann, mathematicians had to draw complex three-dimensional figures directly to understand how planes or lines interact. Grassmann converted this process into pure calculation. For example, if the outer product result of two plane entities is zero, we can mathematically conclude that the two planes overlap entirely (or are perfectly parallel) without needing a single sketch.
