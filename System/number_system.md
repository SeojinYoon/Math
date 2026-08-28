
# Complex number

I struggled to see the significance of complex numbers because they felt too 'imaginary' to be real. However, the same was once true for negative numbers. While 'two apples plus one' is intuitive, 'two apples plus negative one' seems impossible in the physical world; we can visualize zero apples, but not a negative amount. Yet, negative numbers became essential auxiliary tools to represent concepts like debt or opposite directions.

Similarly, complex numbers serve as an auxiliary system for real numbers. When mathematicians encountered the equation $x^2 = -1$, they realized that no real number could satisfy it, as squaring any real number results in a non-negative value. To resolve this logical gap, they devised the imaginary unit $i$, defined as the number whose square is $-1$.

Furthermore, they discovered that the imaginary unit represents a $90^{\circ}$ rotation. Since multiplying by $-1$ is equivalent to a $180^{\circ}$ rotation on the number line, the act of squaring $i$ to get $-1$ implies that multiplying by $i$ twice results in a $180^{\circ}$ turn. Therefore, a single multiplication by $i$ must correspond to a $90^{\circ}$ rotation, moving the number out of the 1D real line and into a 2D plane. Based on this concept, mathematicians devised the 'Complex Plane', where any number can be expressed in the rectangular form $a+bi$, which is equivalent to the coordinate $(a,b)$.

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
