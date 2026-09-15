
# Vector

## History

The vector concept was developed to treat physical quantities having both magnitude and direction as a single mathematical entity.

Before the 19th century, mathematics primarily dealt with single real numbers. Calculating 3D dynamics was cumbersome because it required formulating separate simultaneous equations for the $x$, $y$, and $z$ axes. This approach became particularly inefficient whenever the reference frame was rotated.

For instance, Newton’s second law—which we now express as a single, coordinate-free entity $\mathbf{F} = m\mathbf{a}$—had to be written as three decoupled equations:$$F_x = m \frac{d^2 x}{dt^2}, \quad F_y = m \frac{d^2 y}{dt^2}, \quad F_z = m \frac{d^2 z}{dt^2}$$This algebraic decoupling posed a major conceptual drawback:
- Obscured Physical Intuition: Although force and acceleration are intrinsically unified physical realities with defined spatial directions, treating them as three independent scalar components obscured their geometric essence behind tedious algebraic manipulation.
- Lack of Coordinate Independence: The governing equations were tied directly to an arbitrarily chosen coordinate frame. Consequently, the intrinsic nature of physical laws—namely, that physical reality remains invariant regardless of the coordinate system chosen—was not self-evident in the mathematical notation itself.

Key Milestones in the Development of Vectors
- Geometric Interpretation of Complex Numbers in 2D

    Caspar Wessel, Carl Friedrich Gauss, and Jean-Robert Argand clarified that a complex number $a + bi$ represents not merely a point, but a directed line segment (having magnitude and direction) from the origin. Furthermore, mathematicians demonstrated that complex addition and multiplication correspond directly to 2D translation and rotation. Naturally, this raised the question: Can complex numbers be extended to 3D space?
- Hamilton’s Quaternions

    William Rowan Hamilton addressed this by inventing the 4-dimensional quaternion system, $q = w + xi + yj + zk$, to handle 3D rotations and transformations. He referred to the real part $w$ as a scalar and the imaginary part $xi + yj + zk$ as a vector (derived from the Latin word for "carrier").

- Separation and Formalization by Gibbs and Heaviside

    Although quaternions were mathematically powerful, 19th-century physicists found their 4D algebra unnecessarily abstract and cumbersome for everyday mechanics. Josiah Willard Gibbs and Oliver Heaviside independently extracted the 3D imaginary part from quaternions, developing modern 3D vector analysis centered around the dot product and cross product.

## Problems Solved by the Introduction of Vectors

- Coordinate System Independence (Expressing the Essence of Physical Laws)

    No matter how an observer rotates the coordinate system, the relationship between the force acting on an object ($\vec{F}$) and its acceleration ($\vec{a}$), $F = ma$, remains invariant. Through vector notation, the geometric invariance of physical laws can be expressed in a single equation, completely independent of the choice of coordinate axes ($x, y, z$).

- Groundbreaking Simplification of Electromagnetism Equations

    Maxwell's equations, as originally published by James Clerk Maxwell, were formulated as a complex system of 20 component-wise differential equations. By applying vector operators—divergence ($\nabla \cdot$) and curl ($\nabla \times$)—Oliver Heaviside compressed them into just four elegant equations, making the propagation of electromagnetic waves through space clearly interpretable.

- Rigorous Calculation of Work, Rotation, and Torque in 3D Space
    - Dot Product ($A \cdot B$): Immediately calculates the actual work done when the direction of force differs from the direction of displacement, as well as the length of projections.
    - Cross Product ($A \times B$): Defines three-dimensional orthogonal interactions as a single operation, including the axis of rotation, torque, angular momentum, and the Lorentz force exerted on a charged particle in a magnetic field.

- Generalization to Multi-Dimensional Data and Modern Linear Algebra

    Originally conceived as geometric arrows, vectors were later abstracted into elements of n-dimensional space, $(x _1, x_2, ..., x_n)$. Consequently, diverse domains—such as state spaces in quantum mechanics (Hilbert spaces), multivariate statistical analysis, and high-dimensional feature embeddings in machine learning—can all be handled within a unified mathematical framework.