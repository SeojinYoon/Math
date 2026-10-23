
# Exponential function

## Essential characteristic: Compound Interest limit

The exponential function is defined as the limit of an infinitesimal change multiplied infinitely:$$ f(z) = e^z = \lim_{n \to \infty} \left( 1 + \frac{z}{n} \right)^n$$
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

## Dynamics & Stability: Convergence vs. Divergence over Time

When the exponential function is generalized to model dynamical systems (signal processing, linear control theory, and differential equations), the complex frequency variable $s = \sigma + j\omega$ governs the time-domain trajectory $w(t) = e^{st}$ for $t \ge 0$:

$$w(t) = e^{st} = e^{(\sigma + j\omega)t} = \underbrace{e^{\sigma t}}_{\text{Radial Growth / Decay}} \cdot \underbrace{e^{j\omega t}}_{\text{Phase Rotation}}$$

The absolute magnitude and asymptotic stability of the trajectory depend entirely on the sign of the real part $\sigma$:

1. Strictly Negative Real Part: $\sigma < 0$ (Convergence / Stable Damping)
- Radial scale factor: $e^{\sigma t} \to 0$ as $t \to \infty$.
- Trajectory geometry: The state vector rotates at an angular velocity of $\omega$ rad/s while winding inward toward the origin ($0$), forming an **inward logarithmic spiral**.
- System behavior: Energy dissipates completely, and the state asymptotically converges to the origin.

2. Zero Real Part: $\sigma = 0$ (Marginal Stability / Unit Orbit)
- Radial scale factor: $e^{0 \cdot t} = 1$ for all $t$.
- Trajectory geometry: Without radial growth or decay, the vector traces a closed circular orbit of constant radius $1$ on the complex plane.
- System behavior: Represents a conservative, **undamped harmonic oscillator** that neither diverges nor decays.

3. Strictly Positive Real Part: $\sigma > 0$ (Divergence / Exponential Explosion)
- Radial scale factor: $e^{\sigma t} \to \infty$ as $t \to \infty$.
- Trajectory geometry: With every revolution, the radial distance scales exponentially outward, tracing an **unbounded outward spiral**.
- System behavior: Driven by positive feedback, the output amplitude explodes to infinity.
