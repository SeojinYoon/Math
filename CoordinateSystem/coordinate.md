
# Polar coordinate

In the polar coordinate system, a point is represented as $(r, \theta)$. This allows us to intuitively grasp a vector's magnitude and direction compared to the Cartesian system. A key advantage is that multiplication and division are significantly simpler: to multiply two vectors, we simply multiply their magnitudes and add their angles. This makes it easy to scale and rotate vectors. However, for addition and subtraction, polar coordinates are less convenient. In most cases, we first convert polar coordinates into Cartesian coordinates, perform the operation, and then convert the result back into polar form.

## Kinematics chain and polar representation

The polar coordinate system is highly advantageous for vector multiplication, which fundamentally represents scaling and rotation. This characteristic allows us to model body movements—specifically joint rotations—more efficiently. Since joint movements are interconnected like a chain, the orientation of each segment is determined by the cumulative rotation of the preceding joints. Thus, the position of any point on the body can be represented as a series of nested rotations in polar form.

In a 2-link arm system, where $p_1$ is the first link and $p_2$ is the second link relative to $p_1 $ stretch out about L2, and rotated about $\theta_2$:
- $p_1 = (L_1, \theta_1)$
- $p_2 = (\alpha, \theta_1 + \theta_2)$: Relative vector of the second link, where $\alpha$ represents the stretched length and $\theta_1 + \theta_2$ represents the cumulative orientation.
    - (Note: While the cumulative angle reflects the chain-like rotation, the total displacement from the origin requires summing these vectors in their Cartesian forms.)

