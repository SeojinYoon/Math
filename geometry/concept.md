
# Geometry

Geometry is a branch of mathematics concerned with the properties, relationships, and measurements of points, lines, angles, surfaces, and solids, as well as the nature of space itself.

## The etymology of geometry

- **Etymology**: The word originates from the Greek words geo (earth) and metron (measure). It initially developed as a practical technique in ancient Egypt and Mesopotamia for surveying agricultural land after river floods and calculating crop yields or taxes.
- **Axiomatic Foundation**: In ancient Greece, Euclid systematized these empirical surveying rules in his Elements. He turned geometry into a rigorous deductive science built on explicit definitions, postulates, and logical proofs.
- **Algebraic Geometry**: In the 17th century, René Descartes connected geometry with algebra by inventing the coordinate system. This allowed geometric curves to be expressed as algebraic equations ($x, y$), laying the groundwork for calculus and analytic geometry.
- **Modern Space and Curvature**: During the 19th and 20th centuries, mathematicians moved beyond flat Euclidean space into non-Euclidean geometry (spherical and hyperbolic surfaces) and differential geometry, which became the mathematical language Albert Einstein used to describe curved spacetime in general relativity.

## Transform

In geometry, a transformation is a mapping that takes points from one space to another. According to Felix Klein's Erlangen Program, geometry is defined as the study of properties that remain invariant under a group of transformations. In other words, the hierarchy and classification of geometries are determined by what remains preserved when a transformation is applied.

Below is a hierarchy ordered by increasing degrees of freedom, starting from the most constrained transformation:

1. Euclidean / Rigid Transformation
2. Similarity Transformation
3. Linear Transformation
4. Affine Transformation
5. Projective Transformation / Homography
6. Diffeomorphism / Non-linear Deformation

### Euclidean / Rigid Transformation

It is a transformation that changes an object's position and orientation only—as in a rigid body—without warping or scaling it.

- Definition: A mapping that preserves the exact distance between any pair of points.
- Preserved Invariants: Euclidean distance (lengths), angles, areas, and overall shape.
- Mathematical Representation:$$\mathbf{x}' = R\mathbf{x} + \mathbf{t}$$where $R$ is an orthogonal matrix with $\det(R) = 1$ (rotation in $\mathrm{SO}(n)$) and $\mathbf{t} \in \mathbb{R}^n$ is a translation vector. If reflections ($\det(R) = -1$) are included, it forms the full Euclidean group $\mathrm{E}(n)$.

### Similarity Transformation

It is a rigid transformation combined with uniform scaling, allowing an object to expand or shrink uniformly across all dimensions.

- Definition: A mapping that scales all Euclidean distances by a single, positive constant factor.
- Preserved Invariants: Angles, geometric shapes, and ratios between distances (absolute lengths and areas are not preserved).
- Mathematical Representation:$$\mathbf{x}' = sR\mathbf{x} + \mathbf{t}$$where $s > 0$ is an isotropic scale factor, $R \in \mathrm{SO}(n)$, and $\mathbf{t} \in \mathbb{R}^n$.

### Linear Transformation

It is a transformation that fixes the origin while mapping straight lines to straight lines. Geometrically, any linear transformation can be decomposed into a combination of rotation, scaling, and shear.

- Key Components:
    - Non-uniform Scaling: Stretches or compresses space along coordinate axes by independent factors, deforming circles into ellipses.
    - Shear: Slides parallel layers of space relative to one another in proportion to their perpendicular distance, deforming orthogonal frames into parallelograms while preserving area ($\det = 1$).
- Preserved Invariants: The origin ($\mathbf{0} \mapsto \mathbf{0}$), collinearity of points, and parallelism of straight lines.
Mathematical Representation:$$\mathbf{x}' = A\mathbf{x}$$where $A \in \mathrm{GL}(n, \mathbb{R})$ is an invertible $n \times n$ matrix.

### Affine Transformation

It is a linear transformation followed by a translation—effectively allowing the origin to move while preserving the parallelism of lines.

- Definition: A mapping that preserves parallel lines and ratios of distances along parallel lines.
- Preserved Invariants: Parallelism, straightness of lines, and the ratio of division of line segments (midpoints remain midpoints).
- Mathematical Representation:$$\mathbf{x}' = A\mathbf{x} + \mathbf{t}$$In homogeneous coordinates, it is expressed as a single matrix multiplication:$$\begin{bmatrix} \mathbf{x}' \\ 1 \end{bmatrix} = \begin{bmatrix} A & \mathbf{t} \\ \mathbf{0}^T & 1 \end{bmatrix} \begin{bmatrix} \mathbf{x} \\ 1 \end{bmatrix}$$

### Projective Transformation (Homography / Collineation)

It is a transformation that models perspective projection, mapping straight lines to straight lines without preserving parallelism.

- Definition: An invertible mapping in projective space that preserves collinearity. Parallel lines in the physical world converge toward vanishing points under this projection (as seen in pinhole camera geometry).
- Preserved Invariants: Collinearity (straight lines remain straight) and the cross-ratio of four collinear points (parallelism and angle measurements are lost).
- Mathematical Representation:$$\tilde{\mathbf{x}}' = H \tilde{\mathbf{x}}$$where $\tilde{\mathbf{x}}$ denotes homogeneous coordinates in $\mathbb{P}^n$, and $H$ is a non-singular $(n+1) \times (n+1)$ matrix defined up to an arbitrary non-zero scalar.

### Diffeomorphism / Non-linear Deformation

It is a smooth, invertible mapping between manifolds whose inverse is also smooth. Rather than being represented by a single global matrix, space is warped locally and continuously.
- Definition: A bijective map $f: M \to N$ such that both $f$ and $f^{-1}$ are infinitely differentiable ($C^\infty$).
- Local Approximation: While straight lines generally curve globally, the transformation can be locally linearized at any point $\mathbf{x}_0$ via its Jacobian matrix:$$f(\mathbf{x}) \approx f(\mathbf{x}_0) + J_f(\mathbf{x}_0)(\mathbf{x} - \mathbf{x}_0)$$where the Jacobian $J_f$ locally acts as an affine transformation (incorporating local rotation, scaling, and shear).
- Preserved Invariants: Topological properties (continuity, connectivity, boundaries, number of holes) and smooth differential structure.