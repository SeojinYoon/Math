
# Complex number

I struggled to see the significance of complex numbers because they felt too "imaginary" to be real. However, the same was once true for negative numbers. While "two apples minus one apple" is intuitive, having "negative one apple" feels impossible in the physical world; we can visualize zero apples, but not a negative physical quantity. Yet negative numbers became essential tools to represent relationships like debt or opposite directions.

The true breakthrough came with understanding what an angle actually requires.

On a 1D number line, multiplying by $-1$ is merely an instantaneous sign flip—a reflection across zero. Within the strict confines of a single line, the concept of an angle cannot even exist. An angle requires two intersecting, independent directions—a space between two axes that can be swept through. A 1D world has no such opening; there is only forward and backward, with zero room to turn.

However, the moment we attempt to describe this abrupt sign flip as a smooth, continuous turnaround—a $180^\circ$ rotation—the very concept of an angle forces a brand new axis into existence. To maintain a distance of $1$ from the origin while transitioning from $+1$ to $-1$, the path must swing sideways. Because the original line offers no sideways direction, introducing an angle demands an entirely new, perpendicular dimension.

Under this angle-driven perspective, the algebraic rule $i^2 = -1$ gains an intuitive geometric meaning: if multiplying by $i$ twice carries out a $180^\circ$ turn, then a single multiplication by $i$ must be the halfway point—a $90^\circ$ rotation. The imaginary unit $i$ is not a bizarre phantom number; it is simply the unit marker on that newly erected perpendicular axis born from our need for an angle.

By crossing this perpendicular imaginary axis over the horizontal real line, mathematicians established the Complex Plane. Here, any number can be expressed in rectangular form as $a + bi$, which corresponds directly to the 2D coordinate $(a, b)$.

## Complex conjugate

The complex conjugate of a complex number is a number with an equal real part and an imaginary part equal in magnitude but opposite in sign. For a given complex number $z = a + bi$, the complex conjugate is defined as:$$\bar{z} = a - bi$$

**Note: Why do we use the complex conjugate?**

While complex numbers are mathematically convenient for calculations, physical measurements in the real world must result in real values. The complex conjugate acts as a "filter" that cancels out the imaginary components, allowing us to derive real-numbered properties (such as distance, energy, or probability) from complex systems.

## Complex number and coordinate system

Likewise, just as a point $(x,y)$ in a rectangular coordinate system can be represented as $(r\cos\theta, r\sin\theta)$ using trigonometry, the complex number $(a,b)$ can also be expressed in terms of its distance $r$ from the origin and its rotation angle $\theta$. This results in the polar form: $r(\cos\theta + i\sin\theta)$. This shows that a complex number is not just a value, but a combination of magnitude and direction.

## Norm of a complex number

The norm of a complex number $z = a + bi$ (where $a$ and $b$ are real numbers) is a non-negative real number that represents its "length" or distance from the origin in the complex plane.

The Euclidean norm, denoted by $|z|$, is calculated using the Pythagorean theorem: $$|z| = \sqrt{a^2 + b^2}$$

It can also be expressed using the complex conjugate: $$|z| = \sqrt{z \bar{z}}$$
