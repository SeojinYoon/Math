
# Euler number

## Origin and Discovery

Historically, the constant $e$ was not discovered by analyzing geometric curves or abstract differential equations, but through a very practical financial problem investigated by Jacob Bernoulli in 1683: the limit of continuous compound interest.

1. **Bernoulli's Compounding Thought Experiment**

    Consider a principal of $1$ invested at a nominal interest rate of $100\%$ per year:

    - Compounded once a year:$$\left(1 + \frac{1}{1}\right)^1 = 2$$
    - Compounded semi-annually (twice a year, 50% each):$$\left(1 + \frac{1}{2}\right)^2 = 2.25$$
    - Compounded monthly ($12$ times a year):$$\left(1 + \frac{1}{12}\right)^{12} \approx 2.613$$
    - Compounded daily ($365$ times a year):$$\left(1 + \frac{1}{365}\right)^{365} \approx 2.71456$$

    Bernoulli asked: If interest is credited continuously over infinitely small intervals ($n \to \infty$), will the wealth diverge to infinity?$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n$$

    Using the binomial theorem, he proved that this sequence does not explode to infinity; instead, it converges strictly to a finite limit between $2$ and $3$ ($\approx 2.71828\dots$). Bernoulli proved that this bound existed, but he did not identify its profound connection to calculus.
2. **Euler's Formulation as the Universal Scaling Factor**

    Decades later, Leonhard Euler bridged Bernoulli's compounding limit with differential calculus and formally designated the constant as $e$ in his Introductio in analysin infinitorum (1748).

    Euler demonstrated that $e$ can be represented as the infinite series:$$e = \sum_{k=0}^{\infty} \frac{1}{k!} = 1 + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \dots$$

    More importantly, Euler uncovered its exact role in the differentiation of exponential functions. When differentiating an arbitrary exponential function $f(x) = a^x$ from first principles:$$\frac{d}{dx} a^x = a^x \cdot \lim_{h \to 0} \frac{a^h - 1}{h}$$

    The resulting derivative is proportional to the original value $a^x$, but scaled by an extraneous scalar constant:
    - If $a = 2$, $\lim_{h \to 0} \frac{2^h - 1}{h} \approx 0.693$
    - If $a = 3$, $\lim_{h \to 0} \frac{3^h - 1}{h} \approx 1.098$

    Euler observed that there exists a uniquely balanced base where this intrinsic scaling constant equals precisely $1$:$$\lim_{h \to 0} \frac{e^h - 1}{h} = 1 \implies \frac{d}{dx} e^x = e^x$$

    This special base turned out to be the exact same constant Bernoulli had derived from compound interest. The Euler number e is therefore not an arbitrary mathematical invention; it is the unique universal base where continuous growth feeds back into its own rate of change with an exact 1:1 ratio, without requiring any external correction factor.
    
## Nature

$$\frac{dy}{dt} = y$$

Many fundamental processes of change in nature follow this differential equation:
> Cell division: As the cell population increases, the number of dividing cells increases at the exact same pace.
> Continuous compounding: As the accumulated principal grows, the interest added at each moment grows proportionally.

The change is not imposed by an arbitrary external pace; the rate of change simply depends on the state itself. The solution to this equation is $y(t) = e^t$. This is why mathematicians regard $e$ as the truly 'natural' base.

## Circle

$$\frac{dz}{dt} = iz$$

Now, bring this natural engine into a two-dimensional space—the complex plane.

In one dimension, the velocity vector $\frac{dy}{dt}$ points in the same direction as the position vector $y$, resulting in runaway exponential expansion ($y = e^t$). But what happens if the rate of change is forced to turn perpendicular to the position at every instant?

In the complex plane, multiplying by the imaginary unit $i$ rotates any vector by 90 degrees counterclockwise. Replacing the scalar rate with $i$ alters the dynamics completely:

The velocity is always perpendicular to the current position: $\frac{dz}{dt} \perp z$.

Because the velocity points neither outward nor inward, the distance from the origin never changes ($\vert{}z(t)\vert{} = 1$). The motion cannot escape along a straight line; instead, it is bent into a continuous, eternal orbit.

The solution to this differential equation is:$$z(t) = e^{it}$$

Projecting this circular motion onto the real (horizontal) and imaginary (vertical) axes yields Euler's formula:$$e^{it} = \cos(t) + i\sin(t)$$

Cosine and sine are not arbitrary geometric ratios that bridge the exponential function to a circle. Rather, $e^{it}$ is the pure, coordinate-free engine of rotation, and $\cos(t)$ and $\sin(t)$ are merely its shadows cast onto orthogonal axes.

## Euler's formula

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

In the standard polar coordinate system, a point on the plane is designated as an ordered pair $(r, \theta)$, where $r$ denotes the radial distance and $\theta$ specifies the angular displacement. Via Euler’s formula, this spatial point can be rewritten algebraically as:$$(r, \theta) \longleftrightarrow r(\cos \theta + i \sin \theta) = r e^{i\theta}$$

While both notations map to identical geometric locations on the two-dimensional plane, they possess fundamentally different algebraic capabilities: polar coordinates provide a static labeling scheme, whereas the complex exponential $r e^{i\theta}$ functions as an active dynamic engine.

1. From Manual Labeling to Built-in Algebraic Rotation

    Pure polar notation $(r, \theta)$ provides an intuitive descriptive coordinate, but it lacks intrinsic algebraic operations defined directly on the tuples.

    - When combining or rotating states under pure polar coordinates, one must manually intervene: multiplying radii, mentally summing angles, and manually rewriting the tuple:$$(r_1, \theta_1) \text{ and } (r_2, \theta_2) \implies (r_1 r_2, \;\theta_1 + \theta_2)$$
    - In contrast, expressing the coordinates as complex exponentials automates this process through standard exponent laws:$$\left(r_1 e^{i\theta_1}\right) \cdot \left(r_2 e^{i\theta_2}\right) = (r_1 r_2) e^{i(\theta_1 + \theta_2)}$$

    The geometric rotation does not need to be tracked as a separate geometric procedure; the underlying algebraic structure of exponentiation naturally executes the rotational shift without human intervention.

2. Calculus Without Rotating Basis Vectors

    The most decisive advantage of $r e^{i\theta}$ emerges when differentiating cyclic and oscillatory systems with respect to time ($t$).

    **Differentiating in Polar Coordinates**

    In classical vector calculus, a position vector in polar coordinates is written as $\mathbf{r}(t) = r \hat{\mathbf{r}}(\theta)$. Because the basis vectors $\hat{\mathbf{r}}$ and $\hat{\boldsymbol{\theta}}$ rotate alongside the point, their directions continuously change over time:$$\frac{d\hat{\mathbf{r}}}{dt} = \dot{\theta}\hat{\boldsymbol{\theta}}, \quad \frac{d\hat{\boldsymbol{\theta}}}{dt} = -\dot{\theta}\hat{\mathbf{r}}$$

    Evaluating velocity and acceleration requires product-rule expansion across changing unit vectors, giving rise to geometric artifacts such as the Coriolis and centrifugal terms.

    **Differentiating with Complex Exponentials**

    When represented as $z(t) = r e^{i\omega t}$ (where $\omega = \frac{d\theta}{dt}$), differentiation ceases to be a geometric tracking problem and reduces to elementary scalar multiplication:$$\text{Position: } z(t) = r e^{i\omega t}$$

    $$\text{Velocity: } \frac{dz}{dt} = i\omega \cdot \left(r e^{i\omega t}\right) = i\omega \cdot z(t)$$

    $$\text{Acceleration: } \frac{d^2z}{dt^2} = (i\omega)^2 z(t) = -\omega^2 z(t)$$

    Every time-derivative simply introduces a factor of $i\omega$. The scalar $i$ directly encapsulates the geometric reality: the velocity vector is always orthogonal ($90^\circ$) to the position vector, oriented purely tangentially along the circle.

3. The Linear Eigenfunction of Cyclic Systems

    Under the differential operator $D = \frac{d}{dt}$, pure trigonometric components swap roles and alter forms ($\cos \to -\sin \to -\cos$). Consequently, individual coordinates in a polar tuple do not form independent eigenfunctions.

    In contrast, $e^{i\omega t}$ serves as an exact eigenfunction of the differential operator:$$\frac{d}{dt} e^{i\omega t} = \lambda e^{i\omega t} \quad (\text{where } \lambda = i\omega)$$

    Because differentiation acts merely as multiplication by the eigenvalue $i\omega$, linear differential equations governing harmonic oscillators, wave equations, and neural network oscillations can be converted directly into simple algebraic systems.

    Thus, $re^{iθ}$ is not merely an alternative way to write the polar tuple $(r,θ)$; it is the natural algebraic structure that renders rotation, circular motion, and wave mechanics solvable through elementary arithmetic.

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

