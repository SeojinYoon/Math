
# Euler number

# Euler's formula
Mathematician Leonhard Euler favored the function $e^x$ because it is the only function that remains unchanged after differentiation. He wondered, 'What would happen if $x$ were replaced by the imaginary unit $ix$?'
He discovered a fascinating property: when $e^{ix}$ is differentiated twice, it becomes the negative of itself, as shown below.

- First derivative: $\frac{d}{dx}e^{ix} = i e^{ix}$ (A $90^{\circ}$ rotation)
- Second derivative: $\frac{d^2}{dx^2}e^{ix} = i^2 e^{ix} = -e^{ix}$ (A $180^{\circ}$ rotation, or the negative of itself)

This behavior perfectly mirrors the properties of $\sin(x)$ and $\cos(x)$, leading Euler to the realization that exponential growth and trigonometric rotation are deeply connected. 
- $\frac{d^2cos(x)}{dx^2} = -cos(x) $
- $\frac{d^2sin(x)}{dx^2} = -sin(x) $

Based on this insight, he utilized Taylor expansion to formally prove the following identity which is called **Euler's formula**.
$$ e^{ix} = \cos(x) + i\sin(x) $$

## Euler's formula and polar coordinate

$$ e^{i\theta} $$
In the polar coordinate system, a point is represented as $(r, \theta)$, where $r$ denotes the radius and $\theta$ denotes the angle. Using Euler’s formula, the same point can be expressed as $r(\cos \theta + i \sin \theta)$ or $re^{i\theta}$. This form effectively separates the position into real and imaginary components through cosine and sine functions, allowing any point on the plane to be expressed compactly.

$$ (r, \theta) \leftrightarrow re^{i\theta} $$

While pure polar notation $(r, \theta)$ provides a visual description, it lacks inherent rules for direct calculation. For instance, when rotating a vector, we typically add angles mentally and update the tuple. However, Euler’s formula allows this to be represented as a formal operation: $r_{1} e^{i\theta_1} \cdot r_{2}e^{i\theta_2} = r_{1}r_{2}e^{i(\theta_1+\theta_2)}$.

## Transition to dynamics

$$ e^{i\omega t} $$
When we extend this concept to time-dependent variables, we introduce the term $e^{i\omega t}$. In this dynamic form, the phase is no longer a static constant but a function of time. As $t$ increases, the vector $e^{i\omega t}$ rotates counter-clockwise at a constant angular velocity $\omega$. This allows us to model continuous oscillations. By combining a static phase shift $e^{i\theta}$ with a dynamic rotation $e^{i\omega t}$, we can represent a delayed signal as $re^{i(\omega t + \theta)}$.

## Convert catesian form into euler's form

To bridge the gap between the static coordinate $a+bi$ and the dynamic rotation $re^{i\theta}$, we must calculate two key components: the magnitude ($r$) and the phase ($\theta$).

1. Calculating the Magnitude ($r$)  
    The magnitude represents the distance from the origin to the point $(a, b)$. According to the Pythagorean theorem:$$r = \sqrt{a^2 + b^2}$$
2. Calculating the Phase ($\theta$)  
    The phase represents the counter-clockwise angle from the positive real axis. Using the inverse tangent function:$$\theta = \tan^{-1}\left(\frac{b}{a}\right)$$

    By combining these, we can rewrite any rectangular number as:$$a + bi \rightarrow r e^{i\theta}$$

3. Handling Fractional Forms

    When dealing with complex numbers in a fractional form, such as a transfer function $Y = \frac{Z_1}{Z_2}$, converting the entire expression directly into $a+bi$ can be algebraically tedious. Instead, it is much more efficient to convert the numerator and denominator into Euler's form separately:

    If $Z_1 = r_1 e^{i\theta_1}$ and $Z_2 = r_2 e^{i\theta_2}$, then:

    $$Y = \frac{r_1 e^{i\theta_1}}{r_2 e^{i\theta_2}} = \left( \frac{r_1}{r_2} \right) e^{i(\theta_1 - \theta_2)}$$

    This reveals a fundamental property of complex division:
    - The magnitudes are divided.
    - The phases are subtracted.

    For example, in the expression $Y = \frac{k}{k + i\omega}$ (where $k > 0$)
    - Numerator ($k$): Magnitude is $k$, Phase is $0$
    - Denominator ($k + i\omega$)
        - Magnitude is $\sqrt{k^2 + \omega^2}$
        - Phase is $\tan^{-1}(\frac{\omega}{k})$
        - Euler Form: $Y = \frac{k}{\sqrt{k^2 + \omega^2}} e^{-i \tan^{-1}(\frac{\omega}{k})}$

    This operation shows that the output signal is scaled by the factor $\frac{k}{\sqrt{k^2 + \omega^2}}$ and shifted (delayed) by the angle $-\tan^{-1}(\frac{\omega}{k})$.

## Complexification

Sometimes it is analytically advantageous to map a real-valued function into the complex domain, a process known as Complexification. Consider the term: $$e^{x}\sin{x}$$

To convert this into a complex representation, we should view it not just as a transformation, but as a wrapping process. According to Euler’s formula, $e^{ix} = \cos{x} + i\sin{x}$, where $\sin{x}$ can be identified as the imaginary part:$$\sin{x} = \text{Im}(e^{ix})$$

Thus, we can rewrite the original term as: $$e^{x}\sin{x} = e^{x} \cdot \text{Im}(e^{ix})$$

Since $e^{x}$ is a purely real scalar, it can be "wrapped" into the imaginary operator without loss of generality:$$\text{Im}(e^{x} \cdot e^{ix}) = \text{Im}(e^{(1+i)x})$$

Therefore, the oscillatory decay $e^{x}\sin{x}$ is represented as the imaginary part of a single complex exponential, $\text{Im}(e^{(1+i)x})$. This unified form allows us to treat the entire term as a simple exponential function when applying differential operators.

# Euler angles

Arbitrary rotation in 3D space is quiet complex to happen by once. Leonhard Euler proved that we can represent any rotation as a combination of rotation along x, y, and z axis. 

## Algebraic Proof

In modern mathematics and engineering, this is proven using linear algebra. An arbitrary 3D rotation is represented by a $3 \times 3$ orthogonal matrix $R$ with a determinant of 1.

The goal of the proof is to determine: "Given an arbitrary rotation matrix $R$, do there always exist angles $(\psi, \theta, \phi)$ such that it can be expressed as the product of three fundamental rotation matrices?"

Assuming a rotation in the $Z-Y-X$ sequence (Yaw-Pitch-Roll), the final rotation matrix $R$ is expanded as follows:$$R = R_z(\psi)R_y(\theta)R_x(\phi)$$

Multiplying and expanding these yields a matrix of the following form. (The full expansion is complex, so we will only look at the key elements.)$$R = \begin{bmatrix} r_{11} & r_{12} & r_{13} \\ r_{21} & r_{22} & r_{23} \\ r_{31} & r_{32} & r_{33} \end{bmatrix} = \begin{bmatrix} \cos\psi\cos\theta & \dots & \dots \\ \sin\psi\cos\theta & \dots & \dots \\ -\sin\theta & \cos\theta\sin\phi & \cos\theta\cos\phi \end{bmatrix}$$

For any given arbitrary rotation, we can calculate the three angles through Inverse Kinematics using the observed elements ($r_{ij}$) of $R$.
- Finding $\theta$: Looking at the $(3,1)$ element of the matrix, $r_{31} = -\sin\theta$. Therefore, we can always find $\theta = \arcsin(-r_{31})$.
- Finding $\psi$: Provided $\cos\theta \neq 0$, dividing the $(2,1)$ element by the $(1,1)$ element gives $\frac{\sin\psi\cos\theta}{\cos\psi\cos\theta} = \tan\psi$. Thus, it can be obtained as $\psi = \text{atan2}(r_{21}, r_{11})$.
- Finding $\phi$: Similarly, dividing the $(3,2)$ element by the $(3,3)$ element yields $\tan\phi$, so we can calculate $\phi = \text{atan2}(r_{32}, r_{33})$.

**Conclusion of the Proof**: From the elemental values of an arbitrary rotation matrix R, there always exists a solution that uniquely (or symmetrically) derives three real angles $(ψ,θ,ϕ)$. Therefore, it is mathematically proven that any rotation can be decomposed into the sum of three axial rotations.

**Gimbal Lock** As seen in the algebraic proof, there are infinitely many solutions for $\psi$ and $\phi$ when $\cos\theta = 0$ (i.e., $\theta = \pm 90^\circ$) because the denominator becomes zero. 

