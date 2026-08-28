
# References
- https://www.3dgep.com/understanding-quaternions/#Absolute_Value_of_a_Complex_Number

The concept of quarterinions was realized by the Irish mathematician Sir William Rowan Hamilton on Monday October 16th 1843 in Dublin, Ireland. Hamilton was on his way to the Royal Irish Academy with his wife and as he was passing over the Royal Canal on the Brougham Bridge he made a dramatic realization that he immediately carved into the stone of the bridge.

$$ i^2 = j^2 = k^2 = ijk = -1 $$

# Complex numbers

Before we can fully understand quaterions, we must first understand where they came from. The root of quaternions is based on the concept of the complex number system.

In addition to the well-known number sets (Natural, Integer, Real, and Rational), the Complex Number system introduces a new set of numbers called imaginary numbers. Imaginary numbers were invented to solve certain equations that had no solutions such as:

$$ x^2 + 1 = 0 $$

To solve this expression, we must state that 𝑥2=−1
 which we know is not possible because the square of any number (positive or negative) is always positive.

Mathematicians generally can’t accept that an expression does not have a solution so a new term was invented called the imaginary number that can be used to solve such equations.

The imaginary number has the form:

$$ i^2 = -1 $$

Don’t try to actually understand this term as there is no logical reason why it exists. We just have to accept that $i$ is just something that squares to −1.

The set of imaginary numbers can be represented by 𝕀.

The set of complex numbers (represented by the symbol ℂ) is the sum of a real number and an imaginary number and has the form:

$$ z = a + bi,\quad a,b \in \mathbb{R},\quad i^2 = -1 $$

It could also be stated that all Real numbers are complex numbers with $b = 0$ and all imaginary numbers are complex numbers with $a = 0$.

# Rotors

We can also perform arbitrary rotations in the complex plane by defining a complex number of the form:

$$ q = \cos(\theta) + i\sin(\theta) $$

Multiplying any complex number by the rotor $q$ produces the general formula:

$$ p = a + bi $$
$$ q = \cos(\theta) + i\sin(\theta) $$
$$ pq = (a + bi)(\cos(\theta) + i\sin(\theta)) $$
$$ a' + b'i = a\cos(\theta) - b\sin(\theta) + (asin(\theta) + b\cos(\theta))i$$

Which can also be written in matrix form:

$$\begin{bmatrix}
a' & -b' \\
b' & a'
\end{bmatrix}
=
\begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
\begin{bmatrix}
a & -b \\
b & a
\end{bmatrix}$$

Which is the method to rotate an arbitrary point in the complex plane counter-clockwise about the origin.

**Note**: Representing Complex Numbers as Matrices

The reason the text uses a $2 \times 2$ matrix multiplication (instead of a simple vector) is that every complex number can be represented as a specific type of matrix.

In mathematics, there is a structural correspondence (an isomorphism) between a complex number $z = x + iy$ and a $2 \times 2$ real matrix. This is defined by:

- The Real Unit ($1$): maps to the Identity Matrix $\rightarrow \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$
- The Imaginary Unit ($i$): maps to a $90^\circ$ Rotation Matrix $\rightarrow \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$

By combining these, any complex number $a + bi$ can be written as:$$a \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} + b \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} = \begin{bmatrix} a & -b \\ b & a \end{bmatrix}$$

# Quaternions

With this knowledge of the complex number system and the complex plane, we can extend this to 3-dimensional space by adding two imaginary numbers to our number system in addition to $i$.

The general form to express quaternions is

$$ q = s + xi + yj + zk \quad s,x,y,z \in \mathbb{R}$$

Where, according to Hamilton’s famous expression:

$$ i^2 = j^2 = k^2 = ijk = -1 $$

and

$$\begin{aligned}
ij = k \quad & jk = i \quad & ki = j \\
ji = -k \quad & kj = -i \quad & ik = -j
\end{aligned}$$

You may have noticed that the relationship between $i, j, k$ are very similar to the cross product rules for the unit cartesian vectors:

$$\begin{aligned}
x \times y &= z \quad & y \times z &= x \quad & z \times x &= y \\
y \times x &= -z \quad & z \times y &= -x \quad & x \times z &= -y
\end{aligned}$$

Hamilton also recognized that the $i, j, k$ imaginary numbers could be used to represent three cartesian unit vectors $\textbf{i}, \textbf{j}, \textbf{k}$ with the same properties of imaginary numbers, such that $ \textbf{i}^2 = \textbf{j}^2 = \textbf{k}^2 = -1 $

**Note: Why ijk is -1?** Hamilton designed the symbols $i, j, k$ not merely as numbers, but as unit imaginaries representing rotations in 3D space. They follow a cyclic multiplication rule (often visualized in a circle)
- $ij = k$
- $jk = i$
- $ki = j$

Therefore, by substituting $ij$ with $k$:$$ijk = (ij)k = (k)k = k^2 = -1$$

**Note: Why does a quaternion use four components?**: Hamilton initially attempted to create a system with only three components ($a + bi + cj$). However, he confronted a fundamental problem when calculating the multiplication of these 3D numbers:
- Comparison with Complex Numbers: In the case of standard complex numbers ($a + bi$), the product of two numbers always remains within the 2D complex plane.
- The Problem of 3D Multiplication: When multiplying 3D numbers, a new term like $ij$ emerges. This term cannot be represented using only the three existing components ($1, i, j$).
- The Necessity of the 4th Axis: Therefore, a new axis ($k$) was required to define the result of $ij$. This naturally led to a 4-dimensional system consisting of four axes ($1, i, j, k$).

## Quaternions as an Ordered Pair

We can also represent quaternions as an ordered pair:

$$ q = [s, \textbf{v}] \quad s \in \mathbb{R}, \quad \mathbf{v} \in \mathbb{R}^3 $$

Where $\textbf{v}$ can also be represented by its individual components:

$$ q = [s, x\textbf{i} + y\textbf{j} + z\textbf{k}] \quad s,x,y,z \in \mathbb{R} $$

Using this notation, we can more easily show the similarities between quaternions and complex numbers.

$$\begin{array}{|c|c|c|}
\hline
\text{\textbf{Feature}} & \text{\textbf{Complex Numbers (2D)}} & \text{\textbf{Quaternions (3D)}} \\ \hline
\text{Components} & \text{Real } (a) + \text{Imaginary } (bi) & \text{Scalar } (s) + \text{\textbf{Vector }} (\mathbf{v}) \\ \hline
\text{Structure} & \text{1 Real + 1 Imaginary axis} & \text{1 Scalar + \textbf{3 Imaginary axes }} (i, j, k) \\ \hline
\end{array}$$

## Adding and Subtracting Quaternions

Quaternions can be added and subtracted similar to complex numbers:

$$\begin{aligned}
q_a &= [s_a, \mathbf{a}] \\
q_b &= [s_b, \mathbf{b}] \\
q_a + q_b &= [s_a + s_b, \mathbf{a} + \mathbf{b}] \\
q_a - q_b &= [s_a - s_b, \mathbf{a} - \mathbf{b}]
\end{aligned}$$

## Quaternion Products

We can also express the product of two quaternions:

$$\begin{aligned}
q_a &= [s_a, \mathbf{a}] \\
q_b &= [s_b, \mathbf{b}] \\
q_a q_b &= [s_a, \mathbf{a}][s_b, \mathbf{b}] \\
&= (s_a + x_ai + y_aj + z_ak)(s_b + x_bi + y_bj + z_bk) \\
&= (s_as_b - x_ax_b - y_ay_b - z_az_b) \\
&\quad + (s_ax_b + s_bx_a + y_az_b - y_bz_a)i \\
&\quad + (s_ay_b + s_by_a + z_ax_b - z_bx_a)j \\
&\quad + (s_az_b + s_bz_a + x_ay_b - x_by_a)k
\end{aligned}$$

Which results in another quaternion. If we replace the imaginary numbers $i, j, k$ in the previous expression by the ordered pairs (also known as the quaternion units),

$$i = [0, \mathbf{i}], \quad j = [0, \mathbf{j}], \quad k = [0, \mathbf{k}]$$

And substituting back to the original expression together with $[1,\mathbf{0}]=1$ gives:

$$\begin{aligned}
[s_a, \mathbf{a}][s_b, \mathbf{b}] &= (s_as_b - x_ax_b - y_ay_b - z_az_b)[1, \mathbf{0}] \\
&\quad + (s_ax_b + s_bx_a + y_az_b - y_bz_a)[0, \mathbf{i}] \\
&\quad + (s_ay_b + s_by_a + z_ax_b - z_bx_a)[0, \mathbf{j}] \\
&\quad + (s_az_b + s_bz_a + x_ay_b - x_by_a)[0, \mathbf{k}]
\end{aligned}$$

And expanding this expression into a sum of ordered pairs gives:

$$\begin{aligned}
[s_a, \mathbf{a}][s_b, \mathbf{b}] &= [s_as_b - x_ax_b - y_ay_b - z_az_b, \mathbf{0}] \\
&\quad + [0, (s_ax_b + s_bx_a + y_az_b - y_bz_a)\mathbf{i}] \\
&\quad + [0, (s_ay_b + s_by_a + z_ax_b - z_bx_a)\mathbf{j}] \\
&\quad + [0, (s_az_b + s_bz_a + x_ay_b - x_by_a)\mathbf{k}]
\end{aligned}$$

If we multiply through with the quaternion unit and extract the common vector components, we can rewrite this equation in this way:

$$\begin{aligned}
[s_a, \mathbf{a}][s_b, \mathbf{b}] &= [s_as_b - x_ax_b - y_ay_b - z_az_b, \mathbf{0}] \\
&\quad + [0, s_a(x_b\mathbf{i} + y_b\mathbf{j} + z_b\mathbf{k}) + s_b(x_a\mathbf{i} + y_a\mathbf{j} + z_a\mathbf{k}) \\
&\quad + (y_az_b - y_bz_a)\mathbf{i} + (z_ax_b - z_bx_a)\mathbf{j} + (x_ay_b - x_by_a)\mathbf{k}]
\end{aligned}$$

This equation gives us the sum of two ordered pairs. The first ordered pair is a **Real** quaternion and the second is a **Pure** quaternion. These two ordered pairs can be combined into a single ordered pair:

$$\begin{aligned}
[s_a, \mathbf{a}][s_b, \mathbf{b}] &= [s_as_b - x_ax_b - y_ay_b - z_az_b, \\
&\quad s_a(x_b\mathbf{i} + y_b\mathbf{j} + z_b\mathbf{k}) + s_b(x_a\mathbf{i} + y_a\mathbf{j} + z_a\mathbf{k}) \\
&\quad + (y_az_b - y_bz_a)\mathbf{i} + (z_ax_b - z_bx_a)\mathbf{j} + (x_ay_b - x_by_a)\mathbf{k}]
\end{aligned}$$

And if we substitute,

$$\begin{aligned}
\mathbf{a} &= x_a\mathbf{i} + y_a\mathbf{j} + z_a\mathbf{k} \\
\mathbf{b} &= x_b\mathbf{i} + y_b\mathbf{j} + z_b\mathbf{k} \\
\mathbf{a} \cdot \mathbf{b} &= x_ax_b + y_ay_b + z_az_b \\
\mathbf{a} \times \mathbf{b} &= (y_az_b - y_bz_a)\mathbf{i} + (z_ax_b - z_bx_a)\mathbf{j} + (x_ay_b - x_by_a)\mathbf{k}
\end{aligned}$$

We get: $$[s_a, \mathbf{a}][s_b, \mathbf{b}] = [s_as_b - \mathbf{a} \cdot \mathbf{b}, s_a\mathbf{b} + s_b\mathbf{a} + \mathbf{a} \times \mathbf{b}]$$ Which is the general equation of a quaternion product.

**Note: Mnemonics for Quaternion Multiplication** (The "Dot-Cross" Rule)

When multiplying two quaternions $q_1 = [s_1, \mathbf{v}_1]$ and $q_2 = [s_2, \mathbf{v}_2]$:
- Real Part ($s$): "Multiply the scalars ($s_1s_2$) and subtract the dot product ($\mathbf{v}_1 \cdot \mathbf{v}_2$)."
- Vector Part ($\mathbf{v}$): "Cross-multiply the scalars and vectors ($s_1\mathbf{v}_2 + s_2\mathbf{v}_1$), then add the cross product ($\mathbf{v}_1 \times \mathbf{v}_2$)."

## A Real quaternion

A **Real** Quaternion is a quaternion with a vector term of 0:

$$q = [s, \mathbf{0}]$$

And the product of two Real Quaternions is another Real Quaternion:

$$\begin{aligned}
q_{a} & = [s_a, \mathbf{0}] \\
q_{b} & = [s_b, \mathbf{0}] \\
q_{a}q_{b} & = [s_a, \mathbf{0}][s_b, \mathbf{0}] \\
           & = [s_{a}s_{b}, \mathbf{0}]
\end{aligned}$$

Which is similar to the product of two complex numbers that contain a zero imaginary term.

$$\begin{aligned}
z_{1} & = a_{1} + 0i \\
z_{2} & = a_{2} + 0i \\ 
z_{1}z_{2} & = (a_{1} + 0i)(a_{2} + 0i) \\
           & = a_{1}a_{2}
\end{aligned}$$

## Multiplying a Quaternion by a Scalar

We can also multipy a quaternion by a scalar which should obey the rule:

$$\begin{aligned}
q & = [s, \mathbf{v}] \\
\lambda q & = \lambda [s, \mathbf{v}] \\
          & = [\lambda s, \lambda \mathbf{v}]
\end{aligned}$$

We can confirm this by using the product or Real Quaterions shown above to multiply a quaternion by the scalar as a Real Quaternion:

$$\begin{aligned}

q         & = [s, \mathbf{v}] \\
\lambda   & = [\lambda, \mathbf{0}] \\
\lambda q & = [\lambda, \mathbf{0}][s, \mathbf{v}] \\
          & = [\lambda s, \lambda \mathbf{v}]
\end{aligned}$$

## Pure Quaternions

Similar to Real Quaternions, Hamilton also defined the Pure Quaternion as a quaternion that has zero scalar term: $$ q = [0, \mathbf{v}] $$

Or, written in its component parts: $$ q = xi + yj + zk $$

And we can also take the product of two **Pure** quaternions where $\mathbf{a} = (a_1, a_2, a_3), \mathbf{b} = (b_1, b_2, b_3)$:

$$\begin{aligned}
q_{a}q_{b} &= [0, \mathbf{a}][0, \mathbf{b}] \\
           &= (-\underbrace{(a_1 b_1 + a_2 b_2 + a_3 b_3)}_{\text{Dot Product}}, \underbrace{(a_2 b_3 - a_3 b_2)i + (a_3 b_1 - a_1 b_3)j + (a_1 b_2 - a_2 b_1)k}_{\text{Cross Product}}) \\
           &= [-\mathbf{a} \cdot \mathbf{b}, \mathbf{a} \times \mathbf{b}]
\end{aligned}$$

According to the quaternion product rule shown above.

## Additive Form of a Quaternion

We can also express quaternions as an addition of the Real and Pure quaternion parts:

$$\begin{aligned}
q & = [s, \mathbf{v}] \\
  & = [s, \mathbf{0}] + [0, \mathbf{v}]
\end{aligned}$$

## Unit Quaternion

Given an arbitrary vector $\mathbf{v}$, we can express this vector in both its scalar magnitude and its direction as such:

$$ \mathbf{v} = v \mathbf{\hat{v}} \text{ where } v = |\mathbf{v}| \text{ and } |\mathbf{\hat{v}}| = 1 $$
 
## Binary Form of a Quaternion

We can now combine the definitions of the unit quaternion and the additive form of a quaternion, we can create a representation of quaternions which is similar to the notation used to describe complex numbers:

$$\begin{aligned}
q & = [s, \mathbf{v}] \\
  & = [s, \mathbf{0}] + [0, \mathbf{v}] \\
  & = [s, \mathbf{0}] + v[0, \mathbf{\hat{v}}] \\
  & = s + v\hat{q}
\end{aligned}$$

This gives us a way to represent the quaternion that is very similar to complex numbers:

$$\begin{aligned}
z & = a + bi \\
q & = s + v\hat{q} \\
\end{aligned}$$

## Quaternion Conjugate

The quaternion conjugate can be computed by negating the vector part of the quaternion:

$$\begin{aligned}
q   & = [s, \mathbf{v}] \\
q^* & = [s, -\mathbf{v}]
\end{aligned}$$

And the product of a quaternion with its conjugate gives:

$$\begin{aligned}
qq^* &= [s, \mathbf{v}][s, -\mathbf{v}] \\
     &= [s^2 - \mathbf{v} \cdot -\mathbf{v}, -s\mathbf{v} + s\mathbf{v} + \mathbf{v} \times -\mathbf{v}] \\
     &= [s^2 + \mathbf{v} \cdot \mathbf{v}, \mathbf{0}] \\
     &= [s^2 + v^2, \mathbf{0}]
\end{aligned}$$

## Quaternion Norm

If you recall from the definition of the norm of a complex number:

$$\begin{aligned}
|z|  &= \sqrt{a^2 + b^2} \\
zz^* &= |z|^2
\end{aligned}$$

Similarly, the norm (or magnitude) of a quaternion is defined as:

$$\begin{aligned}
q   &= [s, \mathbf{v}] \\
|q| &= \sqrt{s^2 + v^2}
\end{aligned}$$

## Quaternion Normalization

With the definition of a quaternion norm, we can use it to normalize a quaternion. A quaternion is normalized by dividing it by $|q|$:

$$ q' = \frac{q}{\sqrt{s^2 +v^2}} $$

As an example, let’s normalize the quaternion:

$$ q = [1, 4\mathbf{i} + 4\mathbf{j} - 4\mathbf{k} ]$$

First, we must compute the norm of the quaternion:

$$\begin{aligned}
|q| &= \sqrt{1^2 + 4^2 + 4^2 + (-4)^2} \\
    &= \sqrt{49} \\
    &= 7
\end{aligned}$$

Then, we must divide the quaternion by the norm of the quaternion to compute the normalized quaternion:

$$\begin{aligned}
q' &= \frac{q}{|q|} \\
   &= \frac{1 + 4\mathbf{i} + 4\mathbf{j} - 4\mathbf{k} }{7} \\
   &= \frac{1}{7} + \frac{4}{7}\mathbf{i} + \frac{4}{7}\mathbf{j} + \frac{4}{7} \mathbf{k}
\end{aligned}$$

## Quaternion Inverse

The inverse of a quaternion is denoted $q^{-1}$. To compute the inverse of a quaternion, we take the conjugate of the quaternion and divide it by the square of the norm:

$$ q^{-1} = \frac{q^*}{|q|^2} $$

To show this, we can take the fact that by definition of the inverse:

$$ qq^{-1} = [1, \mathbf{0}] = 1 $$

And multiply both sides by the conjugate of the quaternion gives:

$$ q^{*}qq^{-1} = q^{*} $$

And by substitution we get:

$$\begin{aligned}
|q|^2 q^{-1} &= q^* \\
q^{-1} &= \frac{q^*}{|q|^2}
\end{aligned}$$

And for unit-norm quaternions whose norm is 1, we can write:

$$ q^{-1} = q^{*} $$

## Quaternion Dot product

Similar to vector dot-products, we can also compute the dot product between two quaternions by multiplying the corresponding scalar parts and summing the results:

$$\begin{aligned}
q_1 &= [s_1, x_1 \mathbf{i} + y_1 \mathbf{j} + z_1 \mathbf{k}] \\
q_2 &= [s_2, x_2 \mathbf{i} + y_2 \mathbf{j} + z_2 \mathbf{k}] \\
q_1 \cdot q_2 &= s_1 s_2 + x_1 x_2 + y_1 y_2 + z_1 z_2
\end{aligned}$$

We can also use the quaternion dot-product to compute the angular difference between the quaternions:

$$\cos \theta = \frac{s_1 s_2 + x_1 x_2 + y_1 y_2 + z_1 z_2}{|q_1| |q_2|}$$

And for unit-norm quaternions, we can simplify the equation:

$$ \cos{\theta} = s_1s_2 + x_1x_2 + y_1y_2 + z_1z_2 $$

## Rotations

If you recall we defined a special form of the complex number called a **Rotor** that could be used to rotate a point through the 2D complex plane as:

$$ q = \cos(\theta) + i\sin(\theta) $$

Then by its similarities to complexs, it should be possible to express a quaternion that can be used to rotate a point in 3D-space as such:

$$ q = [\cos(\theta), \sin(\theta)\mathbf{v}] $$

**Note, notation**:  
- Vectors (Geometric Objects)
  - $\mathbf{p}$: The original position vector you wish to rotate.
  - $\hat{v}$: The rotation axis, defined as a unit vector (a vector with a magnitude of $1$).
  - $p'$: The resulting vector after the rotation has been applied.
- Quaternions (Mathematical Operators)
  - $q$: The Rotation Quaternion (or Rotor). It is a 4D complex number that encodes the rotation information.
    - $s$ (or $\cos\theta$): The Scalar part of the quaternion. It regulates the "weight" of the original position in the final result.
    - $\lambda \mathbf{\hat{v}}$ (or $\sin\theta \mathbf{\hat{v}}$): The Vector part of the quaternion. It aligns the rotation with the axis $\mathbf{\hat{v}}$.
  - $p$: The Pure Quaternion representation of the vector $\mathbf{p}$. To perform quaternion multiplication, the 3D vector must be converted into a 4D form by setting the scalar term to zero: $[0, \mathbf{p}]$.
- Scalar Weights
  - $\theta$: The rotation angle. In this "Special Case," $\theta$ represents the full angle of rotation.
  - $s$: A shorthand symbol for the scalar component, defined here as $\cos\theta$.
  - $\lambda$: A shorthand symbol for the magnitude of the vector component, defined here as $\sin\theta$.


Let’s test if this theory holds by computing the product of the quaternion $q$ and the vector $p$. First, we can express $p$ as a Pure quaternion in the form: $$ p = [0, \mathbf{p}] $$ And $q$ is a unit-norm quaternion in the form: $$ q = [s, \lambda \mathbf{\hat{v}}] $$

Then,
$$\begin{aligned}
p' & = qp \\
   & = [s, \lambda \mathbf{\hat{v}}][0, \mathbf{p}] \\
   & = [-\lambda \mathbf{\hat{v}}][0, \mathbf{p}] \\
   & = [-\lambda \mathbf{\hat{v}} \cdot \mathbf{p}, s\mathbf{p} + \lambda \mathbf{\hat{v}} \times \mathbf{p}]
\end{aligned}$$

We see that the result is a general quaternion with both scalar and a vector parts.

1. Let's first consider the **special case where $p$ is perpendicular to $\hat{v}$** in which case, the dot-product term $-\lambda \hat{v} \cdot p = 0$ and the result becomes the Pure quaternion: $$ p' = [0, s\mathbf{p} + \lambda \mathbf{\hat{v}} \times \mathbf{p}] $$

    In this case, to rotate $\mathbf{p}$ about $\mathbf{\hat{v}}$ we just substitute $ s = \cos\theta $ and $ \lambda = \sin \theta $.

    $$ p' = [0, \cos\theta \mathbf{p} + \sin \theta (\mathbf{\hat{v}} \times \mathbf{p})] $$

    As an example, let’s rotate a vector $p, 45^\circ$ about the z-axis then our quaternion $q$ is (i.e., $\mathbf{\hat{v}} = \mathbf{k} = (0, 0, 1)$):

    $$\begin{aligned}
    q & = [\cos(\theta), \sin(\theta)\mathbf{k}]
      & = [\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2}\mathbf{k}]
    \end{aligned}$$

    And let's take a vector $p$ that adheres to the special case that $p$ is perpendicular to $k$: $$ p = [0, 2\mathbf{i}] $$

    Now let's find the product of $qp$

    $$\begin{aligned}
    p' & = qp \\
      & = [\frac{\sqrt{2}}{2}, \frac{\sqrt{2}}{2}\mathbf{k}][0, 2\mathbf{i}] \\
      & = [0, 2\frac{\sqrt{2}}{2}\mathbf{i} + 2\frac{\sqrt{2}}{2}\mathbf{k} \times \mathbf{i}]
      & = [0, \sqrt{2}\mathbf{i} + \sqrt{2}\mathbf{j}]
    \end{aligned}$$

    Which results in a **Pure** quaternion that is rotated 45' about the k axis. We can also confirm that the magnitude of the resulting vector is maintained:

    $$\begin{aligned}
    |\mathbf{p}'| &= \sqrt{\sqrt{2}^2 + \sqrt{2}^2} \\
    &= 2
    \end{aligned}$$

    Which is exactly the result we expected!

2. Now let's consider a quaternion that is not orthogonal to $\mathbf{p}$, i.e., $\mathbf{\hat{v}}$ is not perpendicular to $\mathbf{p}$. If we specify the vector part of our quaternion to $45^\circ$ offset from $\mathbf{p}$ we get:
    
    $$\begin{aligned}
    \mathbf{\hat{v}} &= \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \\
    \mathbf{p} &= 2\mathbf{i} \\
    q &= [\cos \theta, \sin \theta \mathbf{\hat{v}}] \\
    p &= [0, \mathbf{p}]
    \end{aligned}$$

    And multiplying our vector $\mathbf{p}$ by $\mathbf{q}$ we get:

    $$\begin{aligned}
    p' & = qp \\
      & = [\cos \theta, \sin \theta\mathbf{\hat{v}}][0, \mathbf{p}] \\
      & = [-\sin \theta \mathbf{\hat{v}} \cdot \mathbf{p}, \cos \theta \mathbf{p} + \sin \theta \mathbf{\hat{v}} \times \mathbf{p}]
    \end{aligned}$$

    And substituting $\mathbf{\hat{v}}, \mathbf{p}$ and $\theta = 45^\circ $ gives:

    $$\begin{aligned}
    p' &= \left[ -\frac{\sqrt{2}}{2} \left( \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \right) \cdot (2\mathbf{i}), \frac{\sqrt{2}}{2}2\mathbf{i} + \frac{\sqrt{2}}{2} \left( \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \right) \times 2\mathbf{i} \right] \\
    &= [-1, \sqrt{2}\mathbf{i} + \mathbf{j}]
    \end{aligned}$$

    Which is no longer a pure quaternion, and it has not been rotated $45^\circ$ and the vector's norm is no longer 2 (instead it has been reduced to $\sqrt{3}$).

3. However, all is not lost. Hamilton recognized (but didn't publish) that if we post-multiply the result of $\mathbf{qp}$ by the inverse of $\mathbf{q}$ then the result is a **pure** quaternion and the norm of the vector component is maintained. Let's see if we can apply this to our example.

    First, let's compute $q^{-1}$:

    $$\begin{aligned}
    q &= \left[ \cos \theta, \sin \theta \left( \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \right) \right] \\
    q^{-1} &= \left[ \cos \theta, -\sin \theta \left( \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \right) \right]
    \end{aligned}$$

    For $\theta = 45^\circ$ gives:

    $$\begin{aligned}
    q^{-1} &= \left[ \frac{\sqrt{2}}{2}, -\frac{\sqrt{2}}{2} \left( \frac{\sqrt{2}}{2}\mathbf{i} + \frac{\sqrt{2}}{2}\mathbf{k} \right) \right] \\
    &= \frac{1}{2} [\sqrt{2}, -\mathbf{i} - \mathbf{k}]
    \end{aligned}$$

    And combining the previous value of $qp$ and $q^{-1}$ gives:

    $$\begin{aligned}
    qp &= [-1, \sqrt{2}\mathbf{i} + \mathbf{j}] \\
    qpq^{-1} &= [-1, \sqrt{2}\mathbf{i} + \mathbf{j}] \, \frac{1}{2} [\sqrt{2}, -\mathbf{i} - \mathbf{k}] \\
    &= \frac{1}{2} \left[ -\sqrt{2} - (\sqrt{2}\mathbf{i} + \mathbf{j}) \cdot (-\mathbf{i} - \mathbf{k}), \mathbf{i} + \mathbf{k} + \sqrt{2} (\sqrt{2}\mathbf{i} + \mathbf{j}) - (-\mathbf{i} - \mathbf{k}) \times (\sqrt{2}\mathbf{i} + \mathbf{j}) \right] \\
    &= \frac{1}{2} [-\sqrt{2} + \sqrt{2}, \mathbf{i} + \mathbf{k} + 2\mathbf{i} + \sqrt{2}\mathbf{j} - \mathbf{i} + \sqrt{2}\mathbf{j} + \mathbf{k}] \\
    &= [0, \mathbf{i} + \sqrt{2}\mathbf{j} + \mathbf{k}]
    \end{aligned}$$

    Which is a **pure** quaternion and the norm of the result is:

    $$\begin{aligned}
    |p'| &= \sqrt{1^{2} + \sqrt{2}^{2} + 1^{2}} \\
    &= \sqrt{4} \\
    &= 2
    \end{aligned}$$

    which is the same as $\mathbf{p}$ so the norm of the vector is maintained.

    So we can see that the result is a pure quaternion and that the norm of the initial vector is maintained, but the vector has been rotated $90^\circ$ rather than $45^\circ$ which is twice as much as desired! So in order to correctly rotate a vector $p$ by an angle $\theta$ about an arbitrary axis $\mathbf{\hat{v}}$, we must consider the half-angle and construct the following quaternion:

    $$ q = [\cos(\frac{1}{2}\theta), \sin(\frac{1}{2}\theta\mathbf{\hat{v}})]$$

    Which is the general form of a rotation quaternion!

**Note, Why distinguish between Real and Pure parts in a Unit Quaternion?**: In the context of 3D rotation, they represent the two fundamental components of the axis-angle representation:

- The Real part ($w$): Encodes the magnitude of rotation, specifically as $\cos(\theta/2)$.
- The Pure part ($\mathbf{v}$): Encodes the direction of the rotation axis ($\mathbf{u}$), scaled by the remaining rotational magnitude, $\sin(\theta/2)$.