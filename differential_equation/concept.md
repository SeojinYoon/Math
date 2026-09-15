
# Differential equation

A differential equation (DE) differs from standard algebraic equations because it describes a relationship involving derivatives, which link a dependent variable to its independent variable.Consider Newton’s Second Law of Motion. While it is often written simply as $F = ma$, expressing it as $F = m \frac{dv}{dt}$ (or $F = \frac{dp}{dt}$) reveals a more complex structure. In the algebraic form ($F = ma$), $a$ is treated as a single, static value. However, in the DE form, the acceleration is explicitly shown as a rate of change, involving both the dependent variable (velocity) and the independent variable (time).

In a standard explicit function, such as $y = f(x)$, the relationship between variables is direct and intuitive. In contrast, a differential equation defines the relationship through the system's behavior:$$ f(x, y, y', y'', \dots) = g(x) $$ Here, the equation doesn't tell you what $y$ is directly; instead, it tells you how $y$ must change in relation to itself and $x$.

**Note on Control theory**: We can interpret $g(x)$ as the time-varying command (or reference signal) that the system is instructed to follow. The independent variable $x$ represents the continuous time domain over which this command unfolds. In this light, the DE describes the system's dynamic process of generating $y$ (the internal adjustment) to faithfully track the intended goal $g(x)$ while battling its own physical limitations (like inertia or resistance) at every moment.

**Note on The Essence of Differential Equations: A Pursuit of Intent within a Shared Domain**: A differential equation is not merely a mathematical tool for calculation; it is a dynamic narrative of a System chasing a Goal within the shared domain of Time ($t$).

1. Shared Domain (Time): 
    Both the internal state of the system ($y$) and the intended goal ($g$) exist upon the same canvas of time. As time flows, the goal evolves, continuously presenting the system with new targets to achieve.
2. Projection of Intent (Goal): 
    In this context, $g(t)$ on the right-hand side represents more than just an input; it is the "Path of Intention" over time. It dictates where the system should be.
3. Active Manipulation (Internal Adjustment): 
    The left-hand side, $f(t, y, y', y'', \dots)$, represents the system’s physical reality. To align itself with the changing goal, the system must actively manipulate its internal variables—position, velocity, and acceleration. These derivative terms are the "traces of adjustment" made by the system to overcome its own physical constraints (such as inertia or resistance).
4. Resultant Synchronization (Balance): 
    Solving a DE means finding the "Optimal Trajectory of Manipulation" ($y$). It is the unique and inevitable path the system must take to synchronize its output with the intended goal without violating its own physical laws.

A differential equation is a strategic blueprint for a system, describing how it must differentiate and manipulate its own State to realize a shifting Intention while navigating the relentless flow of Time.

**Note on The Human Equation: A Sublime Journey Toward the Divine**:

Based on the interpretation of goal and limitation, a differential equation can be seen as a representation of the tension between the limitations of the human body and the divine goal one aspires to achieve. In this light, the differential equation captures the sublime journey of an individual constantly refining their life ($y$) to bridge the gap between human frailty and God’s intent.$$ \underbrace{f(y, y', y'', \dots)}_{\text{Physical Reality / Human Limitation}} = \underbrace{g(t)}_{\text{Divine Intent / The Goal}} $$
- $g(t)$ (Divine Intent): The absolute, unchanging purpose or "calling" that guides us through time.
- $f(y, y', \dots)$ (Physical Reality): The "gravity" of our physical existence—our habits, inertia, and the inherent constraints of being human.
- $y$ (The Life Path): The unique trajectory of a soul that, despite its limitations, persistently adjusts and differentiates itself to align with the divine will.

**Note on the Self-Referential Nature of DE**: Often in DE, the puzzles you face involve finding a function($y$) whose derivative (and/or higher-order derivatives) is defined in terms of the function itself. For example, consider an object falling under gravity. If we look at the acceleration, we have:$$\frac{dy'}{dt} = -g \quad (\text{or } y'' = -g)$$ By integrating $-g$ with respect to $t$, we find the velocity function:$$y' = -gt + v_0$$ Furthermore, to find the position function $y(t)$ that satisfies the above velocity, we integrate once more:$$y(t) = -\frac{1}{2}gt^2 + v_0t + y_0$$ Likewise, a differential equation is defined where the behavior of the change is linked to the function itself.

**Note on meaning of design differential equation**:
Defining a differential equation involves identifying the fundamental state variables ($y$) of a phenomenon and describing the system's dynamics through the relationships between their derivatives. The solution to this equation then determines the actual values of those variables over time.

**Note on Advantage of using vector field**: Sometimes we used vector field to describe differential equation. What is the advantage of this compared to describe higher order differential equation directly? 

1. From single trajectory to global flow
    - Direct DE: Solving a higher-order DE usually yields a single solution  based on a specific initial condition.
    - Vector Field: By converting the system into a vector field (Phase Portrait), we can visualize the entire state space. This allows us to see the "global flow"—how every possible state evolves, not just a single path. It transforms the problem from "where does this point go?" to "how does this entire world move?"
2. Qualitative Analysis over Analytical Solutions
    - Many higher-order or non-linear DEs are analytically unsolvable (we cannot find a neat formula for $y(t)$).
    - Vector fields allow for qualitative analysis. We can identify critical points such as Attractors (stability), Repellers (instability), and Saddle points without ever solving the equation. This helps us predict the long-term behavior (asymptotic behavior) of the system.
3. Geometric Intuition and Dimensional Reduction
    - Higher-order derivatives ( ) are difficult to visualize mentally.
    - By reducing an -th order DE into a system of DEs , we represent the dynamics as a simple geometric relationship: "At any given state , the vector  tells me exactly which direction to move." This turns calculus into geometry.
    
# Autonomous

In a differential equation, autonomous means that the independent variable does not appear explicitly in the equation.

$$ \frac{dy}{dt} = f(y) $$

Here is an example contrasting autonomous and non-autonomous differential equations. In the following examples, the autonomous equation does not contain the independent variable t explicitly, whereas the non-autonomous equation does. However, this does not mean that y is not influenced by t in an autonomous equation. Even if y depends on t, that is, y = y(t), the equation can still be autonomous. It simply means that t does not appear explicitly in the differential equation itself.

- autonomous: $\frac{dy}{dt} = y^2 - 3y  \Leftrightarrow  \frac{dy(t)}{dt} = y(t)^2 - 3y(t)$
- non-autonomous:$\frac{dy}{dt} = 2t + y$

“Autonomous” comes from the Greek words auto (“self”) and nomos (“law”), meaning “self-governing.” In an autonomous differential equation, the evolution of the system is determined solely by its current state y, without explicit dependence on an external variable such as time t. This idea can be confusing at first, because y is still a function of t. However, the key point is that although y depends on t, the rate of change at any moment is determined only by the current state y, not by t itself. That is why the equation is called autonomous.

When a differential equation is autonomous, it is often easier to analyze the long-term behavior of the system. For example, in stability analysis, we can study what happens to the state as time goes to infinity. In equilibrium analysis, we can identify states at which the system stops changing by finding points where f(y)=0.

# Superposition principle

The mathematical definition of the superposition principle is as follows: For a linear differential operator $L$, if $y_1$ is a solution to $L(y) = q_1(x)$ and $y_2$ is a solution to $L(y) = q_2(x)$, then the principle of superposition holds:

$$L(c_1y_1 + c_2y_2) = c_1q_1(x) + c_2q_2(x)$$

While the theorem is easy to follow given the definition of linearity, it is important to distinguish between linearity as a property and superposition as a strategy.

Linearity is a mathematical property defined by $L(c_1 x_1 + c_2 x_2) = c_1 L(x_1) + c_2 L(x_2)$. In contrast, the superposition principle is a problem-solving strategy that leverages this property. Since the system (or "machine") is linear, we can analyze its behavior not by struggling with a complex, combined input, but by decomposing it into simpler, manageable pieces ($q_1, q_2$). 

# Input and Ouput

In engineering, an input-output relationship is sometimes described by a function such as $y = f(x)$, where $x$ is the input and $y$ is the output. This represents a static relationship: once the input is given, the output is determined directly. In contrast, a differential equation such as $y’ + p(x)y = q(x)$ describes a dynamic relationship. Here, $x$ is not the input itself, but an independent variable, often time, over which both the input $q(x)$ and the output $y(x)$ are defined. In this case, $q(x)$ acts as the input signal, and $y(x)$ is the corresponding output or response. Therefore, the key difference is not simply the symbols being used, but the type of relationship being described: $y=f(x)$ expresses a direct static mapping from input to output, whereas a differential equation expresses how the output evolves with respect to an independent variable under the influence of an input. So, finding a solution of a differential equation means finding an output function that satisfies the given rule of change. For example, $y’ = 2x$ has the solution $y = x^2 + C$, which is a function whose derivative matches the required rate of change.

# Various kinds of solutions of DE

There are many kinds of solutions when solving differential equation. In this section, I will explain two kinds of solutions: The general solution and the particular solution. The general solution represents a framework of solutions that includes all possible solutions of DE. To solve a differential equation, we perform integration, which introduces an unknown integration constant. Because the value of this constant is not specified, the solution can take different forms. A solution that retains this arbitrary constant is called the **general solution**, whereas a solution in which the constant is specified using additional conditions is called a **particular solution**.

## The number of integral constants

For a first-order linear homogeneous differential equation, the general solution has the form
$y(x) = C_{1} y_{1}(x).$

In contrast, for a second-order linear homogeneous differential equation, the general solution is given by
$y(x) = C_{1} y_{1}(x) + C_{2} y_{2}(x).$

Comparing these two forms, one may ask why the number of integration constants increases with the order of the differential equation. The reason is that solving a first-order differential equation requires one integration, whereas solving a second-order differential equation requires two integrations. Each integration introduces one integration constant, leading to an additional constant in the general solution.

## Transient solution (= complementary solution) and Steady-state solution (= particular solution)

Generally, the solution of a differential equation consists of two parts: **the transient solution** and the **steady-state solution**.

$$y(t) = y_{tr}(t) + y_{ss}(t)$$

- Transient Solution: This is the part of the solution that decays to zero as time progresses.
- Steady-state Solution: This is the part of the solution that persists even after a long period. It represents the final behavior or "equilibrium" of the system, determined primarily by the external input ($q(t)$) rather than the initial state.

In case of the following solution, $y = e^-{kt}\int{q(t)e^{kt}}dt + Ce^{-kt}$, can be decomposed into the two parts.

$$y(t) = \underbrace{e^{-kt} \int q(t) e^{kt} \, dt}_{\text{Steady-state Solution } (y_{ss})} + \underbrace{Ce^{-kt}}_{\text{Transient Solution } (y_{tr})}$$

# Homogenous, Inhomogenous

A differential equation is **homogeneous** if all terms involve the dependent variable and its derivatives only (no standalone independent variable), so the equation can be written with zero on the right-hand side. In contrast, a differential equation is **inhomogenous** if it contains a term that is independent of the dependent variable, so it can be written with non-zero from on the right-hand side. Here is the example of homogenous and inhomogenous equation.

Examples:
- homogenous: $y'' + 3y' + 2y = 0$ 
- inhomogenous $y'' + 3y' + 2y = 3$

One might raise the question that, in the homogeneous example, the term 0 does not involve the dependent variable and therefore the equation should not be considered homogeneous. However, the zero term can be written as $0 \cdot y$, which involves the dependent variable. Thus, the equation is indeed homogeneous.

# Beats and Resonance

## Definition

Beats is a phenomena where the amplitude periodically rises up and falls due to the superposition of two waves with slightly different frequencies. 

Resonance is a phenomena where a system amplifies an external signal by absorbing energy efficiently when the external frequency matches its natural frequency.

## Mathematical interpretation

Consider this equation: $$y'' + w_0^2y = \cos{w_1t}$$

This equation can be written as: $$(D^2 + w_0^2)y = \cos{w_1t}$$

Above equation is the real part of complexification. So, we can complexify it as: $$(D^2 + w_0^2)\tilde{y} = e^{iw_1t}$$

$$\begin{aligned}
\tilde{y_p} = \frac{e^{iw_1t}}{(iw_1)^2 + w_0^2} = \frac{e^{iw_1t}}{w_0^2 - w_1^2} \quad \text{(by Exponential Input Theorem)}
\end{aligned}$$

$$Re(\tilde{y_p}) = y_p = \frac{\cos{w_1t}}{w_0^2 - w_1^2}$$

---

### 1. Beats (In case of $w_1 \approx w_0$)

When $w_1 \approx w_0$

One particular solution (satisfying $y(0)=0, y'(0)=0$) can be written as the sum of another particular solution and a complementary solution to represent the Beats state:

$$y_p = \underbrace{\frac{\cos(w_1t)}{w_0^2 - w_1^2}}_{\text{another } y_p} - \underbrace{\frac{\cos(w_0t)}{w_0^2 - w_1^2}}_{\text{part of } y_c}$$

#### Geometric meaning

Note: $ \cos(B) - \cos(A) = 2\sin(\frac{A-B}{2})\sin(\frac{A+B}{2}) $

$$ \frac{\cos(w_1t) - \cos(w_0t)}{w_0^2 - w_1^2} = \frac{\overbrace{2\sin\left(\frac{(w_0 - w_1)t}{2}\right)}^{\text{frequency is small}} \cdot \overbrace{\sin\left(\frac{(w_0 + w_1)t}{2}\right)}^{\text{frequency is large}}}{w_0^2 - w_1^2} \quad (w_1 \approx w_0)$$

Beats are a mutual interference phenomenon where two peer waves of nearly identical frequencies periodically synchronize and desynchronize, causing the overall amplitude to pulsate over time

---

### 2. Resonance (In case of $w_1 = w_0$)

$$(D^2 + w_0^2)y = \cos{w_0t}$$

Complexify: $ (D^2 + w_0^2)\tilde{y} = e^{iw_0t}$. 
Here, $iw_0$ is a simple zero of $D^2 + w_0^2$.  
Because $p(D) = D^2 + w_0^2 = (D - iw_0)(D + iw_0)$.

$$\therefore \tilde{y_p} = \frac{te^{iw_0t}}{2iw_0} \quad \text{(by Resonant Input Theorem)}$$

$$Re(\tilde{y_p}) = \frac{t \sin{w_0t}}{2w_0} = y_p$$

#### Alternative Approach

When we consider $w_1$ approaching $w_0$, we can derive the identical Resonance formula via L'Hôpital's rule:
$$\lim_{w_1 \to w_0}\frac{\cos(w_1t) - \cos(w_0t)}{w_0^2 - w_1^2} \overset{\text{L'Hôpital}}{=} \lim_{w_1 \to w_0}\frac{-\sin(w_1t)t}{-2w_1} = \frac{t\sin(w_0t)}{2w_0}$$

#### Damped resonance

Damped resonance is a phenomenon that occurs in an oscillating system subjected to a periodic external force, where internal damping elements dissipate energy. As the system dissipates or releases energy, the amplitude does not diverge to infinity despite the continuous energy input from the external force; instead, it converges to a finite maximum value

## Interpretation from a life perspective

In light of a life perspective, the external input can be considered as the "will" regarding how to spend time, while the system represents one's "nature." 
- **Resonance**: When the frequency of one's nature matches the frequency of the will, the system absorbs energy efficiently, leading to a "peak" in the state of life. This is where true amplification occurs.
- **Beats**: When there is a slight frequency difference between one's nature and the will, the state of life experiences periodic fluctuations—rising and falling—rather than sustained amplification. While this creates a dynamic rhythm, it does not allow the system to reach and maintain the "peak" of resonance
- **Damped response**: Even when the will perfectly matches the nature, the system inevitably encounters resistance (such as fatigue, environmental limitations, or physical boundaries). In this state, the amplification does not go to infinity; instead, it settles at a sustainable, optimized peak. It represents a state of "balanced performance" where one achieves maximum output within the boundaries of reality.

# Simple zero (= Simple root)

The term "simple zero" means that a root of an equation appears exactly once. For example, in $(x-3)(x+3) = 0$, the roots $x = 3$ and $x = -3$ each appear only once, so they are simple zeros. However, in $(x-3)^2 = 0$, the root $x = 3$ appears twice, meaning it is not a simple zero but a double zero (or a root of multiplicity 2).

# Fourier series

The Fourier series is a way of representing a complicated function using two simple, fundamental functions: $\sin$ and $\cos$.

[Problem] Given a function $f(t)$ with a period of $2\pi$, find the coefficients $a_n$ and $b_n$ such that:$$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n\cos(nt) + b_n\sin(nt) \right)$$

When we product $\cos(nt)$ to both sides, the equation is:

**Finding $a_n$**

$$\int_{-\pi}^{\pi} f(t)\cos(nt) \, dt = \dots + \int_{-\pi}^{\pi} a_k\cos(kt)\cos(nt) \, dt + \dots + \int_{-\pi}^{\pi} a_n\cos^2(nt) \, dt + \dots$$

All terms on the right-hand side vanish (go to zero) except for $\int_{-\pi}^{\pi} a_n\cos^2(nt) \, dt$. This is because the inner product between any two distinct trigonometric functions with integer frequencies is zero due to their orthogonality. Therefore, the result is: $$ a_n = \frac{1}{\pi}\int_{-\pi}^{\pi} f(t)\cos(nt) \, dt $$

**Finding $b_n$**

Likewise the you will get: $$b_n = \frac{1}{\pi} \int_{-\pi}^{\pi} f(t)\sin(nt) \, dt$$ 

**Finding constant**

To find the constant term $\frac{a_0}{2}$, we simply integrate both sides of the Fourier series over the interval $[-\pi, \pi]$ without multiplying by any trigonometric functions:$$\int_{-\pi}^{\pi} f(t) \, dt = \int_{-\pi}^{\pi} \frac{a_0}{2} \, dt + \sum_{n=1}^{\infty} \left( \int_{-\pi}^{\pi} a_n\cos(nt) \, dt + \int_{-\pi}^{\pi} b_n\sin(nt) \, dt \right)$$

Then, only one constant term survives: $$\int_{-\pi}^{\pi} f(t) \, dt = \int_{-\pi}^{\pi} \frac{a_0}{2} \, dt$$ 

Therefore the result is: $$a_0 = \frac{1}{\pi} \int_{-\pi}^{\pi} f(t) \, dt$$

## When f(t) is Even or Odd function

### Even function

**Claim**

If a $2\pi$-periodic function $f(t)$ is an even function—meaning $f(-t) = f(t)$ for all $t$—then all sine coefficients $b_n$ vanish ($b_n = 0$). Thus, the Fourier series consists only of the constant term and cosine terms.$$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(nt)$$

**Proof**

1. Define the general Fourier series of $f(t)$ $$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos(nt) + b_n \sin(nt) \right) \quad \text{--- (1)}$$

2. Express $f(-t)$ using the parity of trigonometric functions. Since $\cos(-nt) = \cos(nt)$ (even) and $\sin(-nt) = -\sin(nt)$ (odd):$$f(-t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos(nt) - b_n \sin(nt) \right) \quad \text{--- (2)}$$

3. Apply the even function condition ($f(t) = f(-t)$)Subtracting Equation (2) from Equation (1) yields:$$f(t) - f(-t) = \sum_{n=1}^{\infty} 2b_n \sin(nt) = 0$$

4. Determine the coefficientsFor this equality to hold identically for all $t$, the coefficients of the linearly independent functions $\sin(nt)$ must be zero for all $n \ge 1$:$$2b_n = 0 \implies b_n = 0$$

**Conclusion**

$b_n = 0$ for all $n \ge 1$, the Fourier series of an even function reduces to a Fourier Cosine Series:$$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(nt) \quad \blacksquare$$

#### Finding $a_n$

When computing the coefficients of a Fourier series, we isolate specific components by multiplying $f(t)$ by $\cos(nt)$ or $\sin(nt)$ and integrating over one period. If $f(t)$ is an even function, multiplying it by another even function (such as $\cos(nt)$) yields a product that is also even. By leveraging this property, we can simplify the integral: since the integral of an even function over a symmetric domain $[-\pi, \pi]$ equals twice the integral over $[0, \pi]$, the coefficient $a_n$ can be calculated as:$$a_n = \frac{2}{\pi}\int_{0}^{\pi} f(t)\cos(nt) \, dt$$

**Note on Even $\times$ Even $=$ Even**: $g(t) = f(t)\cos(nt)$ is an even function because replacing $t$ with $-t$ gives:$$g(-t) = f(-t)\cos(-nt) = f(t)\cos(nt) = g(t)$$

### Odd function

**Claim**

If a $2\pi$-periodic function $f(t)$ is an odd function—meaning $f(-t) = -f(t)$ for all $t$—then the constant term $a_0$ and all cosine coefficients $a_n$ vanish ($a_0 = 0, a_n = 0$). Thus, the Fourier series consists only of sine terms.$$f(t) = \sum_{n=1}^{\infty} b_n \sin(nt)$$

**Proof**

1. Define the general Fourier series of $f(t)$ $$f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos(nt) + b_n \sin(nt) \right) \quad \text{--- (1)}$$

2. Express $f(-t)$ using the parity of trigonometric functions.  
    Since $\cos(-nt) = \cos(nt)$ (even) and $\sin(-nt) = -\sin(nt)$ (odd):$$f(-t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos(nt) - b_n \sin(nt) \right) \quad \text{--- (2)}$$

3. Apply the odd function condition ($f(-t) = -f(t)$).  

    Adding Equation (1) and Equation (2) yields:$$f(t) + f(-t) = a_0 + \sum_{n=1}^{\infty} 2a_n \cos(nt) = 0$$

4. Determine the coefficients   

    Since $f(t) + f(-t) = 0$ for all $t$, the constant term and all coefficients of $\cos(nt)$ must be zero:$$a_0 = 0 \quad \text{and} \quad 2a_n = 0 \implies a_n = 0$$

**Note on Why do we integrate from $-\pi$ to $\pi$ even if the period of function is $2\pi$?**: 
> For a periodic function $g(x)$ having $2\pi$ period, the integral value across one period is same regardless of where the starting point is
> $$\int_{-\pi}^{\pi} g(x) \, dx = \int_{0}^{2\pi} g(x) \, dx = \int_{\alpha}^{\alpha + 2\pi} g(x) \, dx$$
> Even though the reason either book or paper use $-\pi, \pi$ is to exploit the symmetric property of either Even function of Odd function. if the period is symmetric reference to origin, then we can miximize the property of integral like:
> - Even function: $\int_{-\pi}^{\pi} f(x) \, dx = 2 \int_{0}^{\pi} f(x) \, dx$
> - Odd function: $\int_{-\pi}^{\pi} f(x) \, dx = 0$


We know that the following equation must hold for all $t$:$$a_0 + \sum_{n=1}^{\infty} 2a_n \cos(nt) = 0$$

If an equation is true for all $t$, integrating both sides over one full period $[-\pi, \pi]$ must also preserve the equality:$$\int_{-\pi}^{\pi} \left( a_0 + \sum_{n=1}^{\infty} 2a_n \cos(nt) \right) dt = \int_{-\pi}^{\pi} 0 \, dt$$

Splitting the integral into separate terms:$$\int_{-\pi}^{\pi} a_0 \, dt + \sum_{n=1}^{\infty} 2a_n \int_{-\pi}^{\pi} \cos(nt) \, dt = 0$$ 

- First term: $\int_{-\pi}^{\pi} a_0 \, dt = 2\pi a_0$
- Second term: The integral of a cosine wave over its complete period is always zero ($\int_{-\pi}^{\pi} \cos(nt) \, dt = 0$).

Thus, the entire sum term vanishes upon integration, leaving:$$2\pi a_0 = 0 \implies \mathbf{a_0 = 0}$$Once we know $a_0 = 0$, we are left with $\sum 2a_n \cos(nt) = 0$. Multiplying by $\cos(mt)$ and integrating over $[-\pi, \pi]$ similarly proves that each $a_n = 0$.

**Conclusion** 

Since $a_0 = 0$ and $a_n = 0$ for all $n \ge 1$, the Fourier series of an odd function reduces to a Fourier Sine Series:$$f(t) = \sum_{n=1}^{\infty} b_n \sin(nt) \quad \blacksquare$$

#### Finding $b_n$

When computing the coefficients of a Fourier series, we isolate specific components by multiplying $f(t)$ by $\cos(nt)$ or $\sin(nt)$ and integrating over one period. If $f(t)$ is an odd function, multiplying it by another odd function (such as $\sin(nt)$) yields a product that is even. By leveraging this property, we can simplify the integral: since the integral of an even function over a symmetric domain $[-\pi, \pi]$ equals twice the integral over $[0, \pi]$, the coefficient $b_n$ can be calculated as: $$b_n = \frac{2}{\pi}\int_{0}^{\pi} f(t)\sin(nt) \, dt$$

**Note on Odd $\times$ Odd $=$ Even**: $g(t) = f(t)\sin(nt)$ is an odd function because replacing $t$ with $-t$ gives:$$g(-t) = f(-t)\sin(-nt) = f(t)\sin(nt) = g(t)$$

##### Example $f(t) = t \quad (-\pi < t < \pi), \quad f(t + 2\pi) = f(t)$

if f(t) = t, 

$$\begin{aligned} b_n &= \frac{2}{\pi}\int_{0}^{\pi} t\sin(nt) \, dt \\ 
&= \frac{2}{\pi} \left( \left[ - \frac{t}{n} \cos(nt) \right]_{0}^{\pi} - \int_{0}^{\pi} \left( -\frac{1}{n} \cos(nt) \right) dt \right) \\ 
&= \frac{2}{\pi} \left( \left( -\frac{\pi}{n} \cos(n\pi) - 0 \right) + \left[ \frac{1}{n^2} \sin(nt) \right]_{0}^{\pi} \right) \\ 
&= \frac{2}{\pi} \left( -\frac{\pi}{n} (-1)^n + 0 \right) \\ &= -\frac{2}{n} (-1)^n \\ 
&= \frac{2}{n} (-1)^{n+1} \end{aligned}$$

Therefore, F.S. for f(t) is: 
$$
\begin{aligned}
f(t) &= 2 \sum_{n=1}^{\infty} \frac{(-1)^{n+1}}{n}\sin(nt) \\
&= 2 \left( \sin(t) - \frac{1}{2}\sin(2t) + \frac{1}{3}\sin(3t) - \frac{1}{4}\sin(4t) + \dots \right)
\end{aligned}
$$

## Difference between Fourier series and Taylor series

Fourier series is not trying to approximate the function at a certain point the way Taylor series do. Fourier series tries to treat the whole interval, and approximate the function nicely over the entire interval, in this case, $-\pi$ to $\pi$ as well as possible.

As you can see from this Taylor series formula, the series approximates a function using its derivatives at the reference point $a$. This approach allows the function to be approximated well near that point, but the approximation worsens as $x$ moves further away from the reference point.

$$f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x - a)^n$$

## Dirichlet's Convergence Theorem

1. When $f$ is continuous at $t_0$, the Fourier series converges to the original value $f(t_0)$.
2. When $f$ is discontinuous (jump discontinuity) at $t_0$, the Fourier series converges to the average value $\frac{f(t_0^+)+f(t_0^-)}{2}$.

## When Period is Changed ($2\pi \to 2L$)

The core idea of this process is: *"Substitute the domain into the well-known $2\pi$-periodic world, compute, and then revert back to the original $2L$-periodic domain."*

1. **Substitution**

    Let $t$ be the variable we want to deal with, and $f(t)$ be a function with a period of $2L$. In other words, $f(t + 2L) = f(t)$. Now, let's define a standard variable $x$ with a $2\pi$ period:

    $$t : [-L, L] \quad \longleftrightarrow \quad x : [-\pi, \pi]$$

    The two variables have a proportional (linear) relationship, so we can set up the proportion:

    $$\frac{x}{\pi} = \frac{t}{L}$$

    Rearranging this gives the relationship between $x$ and $t$:

    $$x = \frac{\pi}{L} t \quad \Longleftrightarrow \quad t = \frac{L}{\pi} x$$

2. **Define New Function $g(x)$**

    Instead of the variable $t$, let's define a new function $g(x)$ as:

    $$g(x) \equiv f\left(\frac{L}{\pi} x\right) = f(t)$$

    Now, let's verify that $g(x)$ actually has a period of $2\pi$:

    $$g(x + 2\pi) = f\left(\frac{L}{\pi} (x + 2\pi)\right) = f\left(\frac{L}{\pi}x + 2L\right)$$

    Since $f$ is a $2L$-periodic function, $f(t + 2L) = f(t)$. Therefore:

    $$f\left(\frac{L}{\pi}x + 2L\right) = f\left(\frac{L}{\pi}x\right) = g(x)$$

    Thus, we can be certain that $g(x)$ is a $2\pi$-periodic function.

3. **Expand $g(x)$ as a $2\pi$-Periodic Fourier Series**

    Because $g(x)$ is a $2\pi$-periodic function, we can apply the standard Fourier series formula to $g(x)$:

    $$g(x) = a_0 + \sum_{n=1}^{\infty} \left( a_n \cos(nx) + b_n \sin(nx) \right)$$

    The standard formula to find the coefficient $a_n$ is:

    $$a_n = \frac{1}{\pi} \int_{-\pi}^{\pi} g(x) \cos(nx) \, dx$$

4. **Inverse Substitution**

    - Series Expansion
        Using the relationship equation, we can replace $x$ with $t$.

        Since $x = \frac{\pi}{L} t$, we can rewrite $\cos(nx)$ and $\sin(nx)$ as:

        $$\cos(nx) = \cos\left(n \cdot \frac{\pi}{L} t\right) = \cos\left(\frac{n\pi t}{L}\right)$$
        $$\sin(nx) = \sin\left(n \cdot \frac{\pi}{L} t\right) = \sin\left(\frac{n\pi t}{L}\right)$$

        Since $f(t) = g(x)$, we obtain:

        $$f(t) = a_0 + \sum_{n=1}^{\infty} \left[ a_n \cos\left(\frac{n\pi t}{L}\right) + b_n \sin\left(\frac{n\pi t}{L}\right) \right]$$

    - Reverting Coefficients
        From the coefficient formula $a_n = \frac{1}{\pi} \int_{-\pi}^{\pi} g(x) \cos(nx) \, dx$, let's change the integral variable and interval:

        * $g(x) = f(t)$
        * $\cos(nx) = \cos\left(\frac{n\pi t}{L}\right)$
        * $x \in [-\pi, \pi] \implies t \in [-L, L]$
        * Change of differentials ($dx \to dt$): $x = \frac{\pi}{L} t \implies dx = \frac{\pi}{L} dt$

        Applying these, we get:

        $$a_n = \frac{1}{\pi} \int_{-L}^{L} f(t) \cos\left(\frac{n\pi t}{L}\right) \left(\frac{\pi}{L} dt\right)$$

        Extracting the constant $\frac{\pi}{L}$ outside the integral and simplifying gives:

        $$a_n = \frac{1}{\pi} \cdot \frac{\pi}{L} \int_{-L}^{L} f(t) \cos\left(\frac{n\pi t}{L}\right) dt = \mathbf{\frac{1}{L} \int_{-L}^{L} f(t) \cos\left(\frac{n\pi t}{L}\right) dt}$$

        The coefficients $a_0$ and $b_n$ can be derived in the exact same way.

## Interpreting Non-Periodic Functions via Fourier Series

We can interpret a non-periodic function using a Fourier series by treating it as a periodic function over a specific domain of interest. Since Fourier series inherently require periodicity, we create a "virtual" periodic function that matches our original function on the given interval (e.g., $[0, L]$). What happens outside this interval does not matter as long as the series reproduces the exact function values within $[0, L]$.

For example, consider $f(t) = t^2$ defined only on $[0, L]$:
- **Even Periodic Extension:** Reflects $f(t)$ across the y-axis to make it an even function on $[-L, L]$, resulting in a **Fourier Cosine Series** ($b_n = 0$).
- **Odd Periodic Extension:** Reflects $f(t)$ symmetrically about the origin to make it an odd function on $[-L, L]$, resulting in a **Fourier Sine Series** ($a_0 = 0, a_n = 0$).

By choosing an appropriate extension, we can represent non-periodic functions using purely cosine or sine terms, whichever fits our boundary conditions or simplifies computation.

# Integral and Orthogonal

The integral of functions is an expanded version of the vector inner product. When the product of two functions over a single period integrates to zero, it means the two functions do not overlap in function space.

The formulated version of orthogonality using an integral is represented as:$$\int_{-\pi}^{\pi} u(t)v(t) \, dt = 0$$

## View of DE on Orthogonality 

Two real-valued functions, $u(t)$ and $v(t)$, are defined as orthogonal on the interval $[-\pi, \pi]$ if:$$\int_{-\pi}^{\pi} u(t)v(t) \, dt = 0$$

**Condition and proof**: Let $u_n(t)$ and $v_m(t)$ be real-valued, periodic functions with a period of $2\pi$ that satisfy the following homogeneous second-order linear differential equations, respectively:

1. $u_n'' + n^2 u_n = 0 \quad \implies \quad u_n'' = -n^2 u_n$
2. $v_m'' + m^2 v_m = 0 \quad \implies \quad v_m'' = -m^2 v_m$

If the frequencies are distinct ($m \neq n$), then the two functions are orthogonal on the interval $[-\pi, \pi]$, meaning:$$\int_{-\pi}^{\pi} u_n(t)v_m(t) \, dt = 0$$

Step 1: Cross-multiplication and Subtraction

- Multiply the first equation by $v_m$:$$u_n'' v_m = -n^2 u_n v_m$$
- Multiply the second equation by $u_n$:
$$v_m'' u_n = -m^2 u_n v_m$$

Subtracting the second equation from the first yields:$$u_n'' v_m - v_m'' u_n = (-n^2 + m^2) u_n v_m$$

$$u_n'' v_m - v_m'' u_n = (m^2 - n^2) u_n v_m \quad \text{--- (Eq. 1)}$$

Step 2: Applying the Reverse Product Rule

By observing the left-hand side of Eq. 1, we can rewrite it as the total derivative of a single expression using the reverse product rule for differentiation:$$(u_n' v_m - v_m' u_n)' = u_n'' v_m + \cancel{u_n' v_m'} - (\cancel{v_m' u_n'} + v_m'' u_n) = u_n'' v_m - v_m'' u_n$$

Substituting this back into Eq. 1 gives:$$(u_n' v_m - v_m' u_n)' = (m^2 - n^2) u_n v_m$$

Step 3: Integration Over One Period $[-\pi, \pi]$

Now, we integrate both sides with respect to $t$ from $-\pi$ to $\pi$:$$\int_{-\pi}^{\pi} (u_n' v_m - v_m' u_n)' \, dt = \int_{-\pi}^{\pi} (m^2 - n^2) u_n v_m \, dt$$

Since $(m^2 - n^2)$ is a constant with respect to $t$, it can be pulled out of the integral on the right-hand side. On the left-hand side, the fundamental theorem of calculus cancels the derivative:

$$\left[ u_n' v_m - v_m' u_n \right]_{-\pi}^{\pi} = (m^2 - n^2) \int_{-\pi}^{\pi} u_n v_m \, dt \quad \text{--- (Eq. 2)}$$

Step 4: Vanishing of the Boundary Term via Trigonometric Solutions

To evaluate the boundary term $\left[ u_n' v_m - v_m' u_n \right]_{-\pi}^{\pi}$, we must consider the explicit forms of $u_n(t)$ and $v_m(t)$.

As demonstrated by solving the given differential equations ($u'' + n^2u = 0$), the fundamental solutions are strictly composed of sine and cosine functions (i.e., $\sin(nt)$ and $\cos(nt)$). These trigonometric functions possess a critical property: $2\pi$-periodicity.

Because any combination of $\sin(nt)$, $\cos(nt)$ and their derivatives yields identical values at both $t = \pi$ and $t = -\pi$ (e.g., $\cos(-n\pi) = \cos(n\pi)$ and $\sin(-n\pi) = \sin(n\pi) = 0$), the upper boundary evaluation and the lower boundary evaluation become exactly equal.

Therefore, subtracting the lower boundary value from the upper boundary value yields zero:$$\left[ u_n' v_m - v_m' u_n \right]_{-\pi}^{\pi} = \left( \text{Evaluation at } \pi \right) - \left( \text{Evaluation at } -\pi \right) = 0$$

Substituting this back into Eq. 2 results in:$$0 = (m^2 - n^2) \int_{-\pi}^{\pi} u_n v_m \, dt$$

Step 5: Final Conclusion

By our initial assumption, the frequencies are distinct ($m \neq n$), which guarantees that $(m^2 - n^2) \neq 0$.Consequently, for the equation to hold true, the integral itself must vanish:$$\therefore \int_{-\pi}^{\pi} u_n(t)v_m(t) \, dt = 0$$

Q.E.D. (Quod Erat Demonstrandum - Which was to be demonstrated)

### Sine and Cosine

1. Product of Sines with Distinct Frequencies ($n \neq m$): $$\int_{-\pi}^{\pi} \sin(nt)\sin(mt) \, dt = 0$$

2. Product of Cosines with Distinct Frequencies ($n \neq m$): $$\int_{-\pi}^{\pi} \cos(nt)\cos(mt) \, dt = 0$$

3. Product of Sine and Cosine (Always orthogonal, regardless of whether frequencies are equal or distinct!): $$\int_{-\pi}^{\pi} \sin(nt)\cos(mt) \, dt = 0$$

# Laplace transform

The Laplace transform is a mathematical tool that converts a complex differential equation in the time domain into an easy-to-solve algebraic equation in the complex frequency domain.

$$ t \rightarrow s $$

## Intuition

### What is the s?

$s$ is a complex variable combining frequency and decay rate into a single number: $s = \sigma + j\omega$.
- $\sigma$ (real part, attenuation/growth rate): represents the exponential factor ($e^{-\sigma t}$) governing how the signal's amplitude changes over time.
- $\omega$ (imaginary part, angular frequency): represents the oscillatory component ($e^{j\omega t} = \cos \omega t + j\sin \omega t$), indicating how rapidly the signal rotates or vibrates over time.

The true essence of the Laplace transform formula, $F(s) = \int_0^\infty f(t) e^{-st} \, dt$, lies in asking:

"How much of the fundamental wave component ($e^{-st}$)—oscillating at frequency $\omega$ and decaying at rate $\sigma$—is present within an arbitrary, complex signal $f(t)$?"

It is a process of decomposing and measuring these individual wave components, and the outcome of this measurement is precisely the function of $s$, denoted as $F(s)$.

### Why do we use it?

TODO

## Background

### Where does the Laplace transform come from?

The Laplace transform naturally arises when extending a discrete power series (or generating function) into a continuous domain.

Before explaining the process, let's review the notation for power series. A power series can be written in two ways.
1. Index notation:$$\sum_{n=0}^{\infty} a_n x^n$$
2. Function notation:$$\sum_{n=0}^{\infty} a(n) x^n$$

To make this continuous, we replace the discrete index $n$ with a continuous variable $t$, and the summation with an integral:$$A(x) = \int_{0}^{\infty} a(t) x^t \, dt$$

For this integral to converge for a wide range of functions, we typically require $0 < x < 1$. This restriction ensures:
1. $0 < x < 1 \rightarrow x > 0$ avoids dealing with multi-valued complex powers for real $t$.
2. $0 < x < 1 \rightarrow x < 1$ ensures that $\ln x < 0$, providing an exponentially decaying factor that helps the integral converge.

Since $\ln x$ is negative over $0 < x < 1$, handling negative numbers directly in formulas can be counterintuitive and lead to sign errors. Therefore, we define a new positive variable $s$ such that:$$\ln x = -s \quad (\text{or } s = -\ln x > 0)$$

Substituting $\ln x = -s$ yields the classic Laplace transform and the notations of Laplace transform are:

1. $\mathcal{L}\{a(t)\} = \int_{0}^{\infty} a(t) e^{-st} \, dt$
2. $ f(t) \rightsquigarrow F(s) $

## Property

### Linearity

The Laplace transform is a linear transform (or linear operator), which is one of its most fundamental and powerful properties. This means it satisfies both additivity and scalar multiplication:
- Additivity:$$\mathcal{L}\{f(t) + g(t)\} = \mathcal{L}\{f(t)\} + \mathcal{L}\{g(t)\}$$
- Homogeneity (Scalar Multiplication):$$\mathcal{L}\{c f(t)\} = c \mathcal{L}\{f(t)\} \quad (\text{where } c \text{ is a constant})$$


## Example

Let's see what the result of Laplace transform in the various case of f(t)

- 1

    $\begin{aligned}
    \int_{0}^{\infty} e^{-st} \, dt &= \lim_{R \to \infty} \int_0^R e^{-st} \, dt \\
    &= \lim_{R \to \infty} \left[ \frac{e^{-st}}{-s} \right]_0^R \\
    &= \lim_{R \to \infty} \frac{e^{-sR} - 1}{-s} \\
    &= \frac{1}{s} \quad (\text{if } s > 0)
    \end{aligned}$

- $ e^{at}f(t) $

    $$\begin{aligned}
    \int_{0}^{\infty} e^{at}f(t)e^{-st} \, dt &= \int_{0}^{\infty} f(t) e^{-(s-a)t} \, dt \\
    &= F(s-a) \quad (\text{if } s - a > 0 \implies s > a, \text{ assuming } s > 0 \text{ for } F(s))
    \end{aligned}$$

    This is known as the Exponential Shift Formula (or Frequency Shift Property).  
    Multiplying $e^{at}$ in the time domain ($t$) simply shifts the entire Laplace transform $F(s)$ by $a$ to the right in the $s$-domain:$$f(t) \xrightarrow{\times e^{at}} e^{at}f(t) \quad \iff \quad F(s) \xrightarrow{s \to s-a} F(s-a)$$

- $ e^{at} $

    Since $\mathcal{L}\{1\} = \frac{1}{s} = F(s)$, and $e^{at}$ can be written as $e^{at} \cdot 1$:
    
    $$\mathcal{L}\{e^{at}\} = \mathcal{L}\{e^{at} \cdot 1\} = F(s - a) = \frac{1}{s - a} \quad (s > a)$$

- $ e^{a + bi}t $

    $$ \mathcal{L}\{e^{(a + bi)t}\} = \frac{1}{s - (a + bi)}, \quad \text{where } s > a $$

- $ \cos(at) $

    $ \cos(at) = \frac{e^{iat} + e^{-iat}}{2} $   
    $$ \begin{align}
    \mathcal{L}(\cos(at)) 
        & = \frac{1}{2}(\frac{1}{s - ia} + \frac{1}{s + ia}) \\
        & = \frac{1}{2}\frac{2s}{s^2 + a^2}, \quad \text{where } s > 0 \\
        & = \frac{s}{s^2 + a^2}
    \end{align} $$

- $ \sin(at) $

    $$ \begin{align}
    \mathcal{L}(\sin(at)) 
        & = \frac{a}{s^2 + a^2} , \quad \text{where } s > 0
    \end{align} $$

- $ t^n $
    $$\mathcal{L}\{t^n\} = \int_0^\infty t^n e^{-st} \, dt = \left[ t^n \frac{e^{-st}}{-s} \right]_0^\infty - \int_0^\infty n t^{n-1} \left(\frac{e^{-st}}{-s}\right) dt$$
    $$\lim_{t \to \infty} \frac{t^n e^{-st}}{-s} = -\frac{1}{s} \lim_{t \to \infty} \frac{t^n}{e^{st}} = 0 \quad (\text{by } n \text{ applications of L'Hôpital's rule})$$
    $$\mathcal{L}\{t^n\} = 0 - 0 + \frac{n}{s} \int_0^\infty t^{n-1} e^{-st} \, dt = \frac{n}{s} \mathcal{L}\{t^{n-1}\} \quad (s > 0)$$
    $$\begin{aligned} \mathcal{L}\{t^n\} &= \frac{n}{s} \mathcal{L}\{t^{n-1}\} \\ &= \frac{n}{s} \cdot \frac{n-1}{s} \mathcal{L}\{t^{n-2}\} \\ &= \frac{n(n-1)(n-2)\cdots 1}{s^n} \mathcal{L}\{t^0\} \\ &= \frac{n!}{s^n} \mathcal{L}\{1\} \end{aligned}$$

### Cases where the Laplace transform works well

Because the Laplace transform introduces an exponential decay factor that suppresses the integrand, it works well in cases where this suppression guarantees convergence. In this context, the core requirement is that $f(t)$ is of exponential order (or exponential type).

A function $f(t)$ is said to be of exponential order $\alpha$ if there exist constants $M > 0$ and $\alpha$ such that the following inequality holds for all sufficiently large $t$:$$\vert{}f(t)\vert{} \le M e^{\alpha t}$$

- Example of exponential type
    - $\sin(t)$
        * $\vert{}\sin(t)\vert{} \le 1 \cdot e^{0 \cdot t} = 1$
    - $t^n$
        * $t^n < \frac{n!}{\alpha^n} e^{\alpha t}$
    - $\frac{t^n}{e^t} = t^n e^{-t}$ 
        * $\vert{}f(t)\vert{} \le M = M e^{0 \cdot t}$
- Example of non exponential type
    - $\frac{1}{t}$
        * While $f(t) = \frac{1}{t}$ is of exponential order as $t \to \infty$ (since $\vert{}\frac{1}{t}\vert{} \le 1$ for all $t \ge 1$), its Laplace transform does not exist because it violates the piecewise continuity / local integrability condition near $t = 0$.
            * Decomposition of the Laplace Integral:$$\mathcal{L}\left\{\frac{1}{t}\right\} = \int_0^\infty \frac{1}{t} e^{-st} \, dt = \int_0^1 \frac{1}{t} e^{-st} \, dt + \int_1^\infty \frac{1}{t} e^{-st} \, dt$$
            * Divergence Near the Origin ($t \to 0$):Since $e^{-st} \to 1$ as $t \to 0$, for sufficiently small $\epsilon > 0$ with $\text{Re}(s) > 0$, we have $e^{-st} \ge e^{-s}$ (or bounded away from 0). The integral diverges logarithmically:$$\int_0^1 \frac{1}{t} e^{-st} \, dt \ge e^{-\text{Re}(s)} \int_0^1 \frac{1}{t} \, dt = e^{-\text{Re}(s)} \lim_{\epsilon \to 0^+} \left[ \ln t \right]_\epsilon^1 = \infty$$
            * Conclusion: The damping factor $e^{-st}$ only suppresses growth as $t \to \infty$; it cannot prevent the singularity at $t = 0$. Hence, the Laplace transform does not exist.
    - $e^{t^{2}}$
        * Unlike $1/t$, the function $f(t) = e^{t^2}$ is continuous everywhere on $[0, \infty)$. However, its Laplace transform does not exist for any complex number $s$ because the function grows too fast and is not of exponential order.
        * Why it is not of exponential order:For $f(t)$ to be of exponential order, there must exist constants $M > 0$ and $\alpha$ such that:$$\vert{}f(t)\vert{} \le M e^{\alpha t} \quad \implies \quad \frac{e^{t^2}}{e^{\alpha t}} \le M$$However, for any choice of constant $\alpha$:$$\lim_{t \to \infty} \frac{e^{t^2}}{e^{\alpha t}} = \lim_{t \to \infty} e^{t(t - \alpha)} = \infty$$Since $t^2$ dominates any linear term $\alpha t$ as $t \to \infty$, no finite constant $M$ can bound $e^{t^2}$.

**Mathematical Mechanism: How Initial Conditions Naturally Emerge**

The mechanism enabling this algebraic simplification is the Laplace transform of derivatives. When transforming a derivative, applying integration by parts automatically extracts the boundary value (initial condition) while converting the derivative operator into multiplication by $s$.

1. First-Order Derivative: $\mathcal{L}\{f'(t)\}$

    By definition, the Laplace transform of the first derivative is:$$\mathcal{L}\{f'(t)\} = \int_{0}^{\infty} e^{-st} f'(t) \, dt$$

    Applying integration by parts:
    - Let $u = e^{-st} \implies du = -s e^{-st} \, dt$
    - Let $dv = f'(t) \, dt \implies v = f(t)$

    By definition of Integration by Parts: $$\int_{a}^{b} u \, dv = \Big[ u \cdot v \Big]_{a}^{b} - \int_{a}^{b} v \, du$$

    This yields: $$\int_{0}^{\infty} \underbrace{e^{-st}}_{u} \cdot \underbrace{f'(t) \, dt}_{dv}$$

    $$\mathcal{L}\{f'(t)\} = \left[ e^{-st} f(t) \right]_{0}^{\infty} - \int_{0}^{\infty} (-s e^{-st}) f(t) \, dt$$

    Evaluating both components:

    - The Boundary Term: Assuming $f(t)$ is of exponential order (i.e., $\vert{}f(t)\vert{} < C e^{kt}$ for $s > k$), the upper limit vanishes as $t \to \infty$:$$\lim_{t \to \infty} e^{-st} f(t) = \lim_{t \to \infty} \frac{f(t)}{e^{st}} = 0$$

    Evaluating at the lower limit ($t = 0$) gives:$$\left[ e^{-st} f(t) \right]_{0}^{\infty} = 0 - e^{0} f(0) = -f(0)$$

    This boundary evaluation is the exact moment the initial condition $f(0)$ enters the algebraic equation.

    - The Integral Term: Factoring out the constant scalar $s$ leaves the definition of the transform itself:$$-\int_{0}^{\infty} (-s e^{-st}) f(t) \, dt = s \int_{0}^{\infty} e^{-st} f(t) \, dt = s F(s)$$

    Combining these terms gives the fundamental operational identity:$$\mathcal{L}\{f'(t)\} = s F(s) - f(0)$$

2. Higher-Order Derivatives: $\mathcal{L}\{f''(t)\}$

    Higher-order derivatives are handled recursively by treating $f''(t)$ as $[f'(t)]'$:$$\mathcal{L}\{f''(t)\} = s \mathcal{L}\{f'(t)\} - f'(0)$$

    Substituting the first-order result $\mathcal{L}\{f'(t)\} = s F(s) - f(0)$:$$\mathcal{L}\{f''(t)\} = s \Big( s F(s) - f(0) \Big) - f'(0) = s^2 F(s) - s f(0) - f'(0)$$

    By induction, for an $n$-th order derivative:$$\mathcal{L}\{f^{(n)}(t)\} = s^n F(s) - s^{n-1} f(0) - s^{n-2} f'(0) - \dots - f^{(n-1)}(0)$$

Key Takeaways
- Differentiation becomes multiplication: The differential operator $\frac{d}{dt}$ maps to multiplication by the complex variable $s$.
- Initial conditions are embedded, not solved: All Cauchy initial conditions ($f(0), f'(0), \dots, f^{(n-1)}(0)$) appear as additive polynomial terms from the very first step, converting a calculus differential equation into a straightforward algebraic equation for $F(s)$

## Application

### Laplace transform and solving differential equation

#### The process using Laplace transform to solve differential equation

Solving an Initial Value Problem (IVP) using the Laplace transform follows a structured 4-step pipeline that maps a differential equation from the time domain ($t$) into an algebraic equation in the complex frequency domain ($s$), and then back to the time domain.


1. Apply the Laplace Transform to Both Sides: Converts differential operators into algebraic expressions while embedding initial conditions.

    Apply the Laplace transform $\mathcal{L}\{\cdot\}$ to each term of the differential equation. Using the differentiation property, replace time derivatives with algebraic terms in $s$ and let $\overline{\underline{Y}}(s) = \mathcal{L}\{y(t)\}$:

    - $\mathcal{L}\{y'(t)\} = s\overline{\underline{Y}}(s) - y(0)$
    - $\mathcal{L}\{y''(t)\} = s^2 \overline{\underline{Y}}(s) - s y(0) - y'(0)$
    - $\mathcal{L}\{y^{(n)}(t)\} = s^n \overline{\underline{Y}}(s) - s^{n-1}y(0) - \dots - y^{(n-1)}(0)$

    Substitute the numerical initial conditions ($y(0), y'(0)$, etc.) directly into the equation at this initial step.

2. Solve Algebraically for Y(s): Reduces the differential problem to polynomial algebra without arbitrary constants

    Treat $\overline{\underline{Y}}(s)$ as an algebraic unknown. Collect all terms containing $\overline{\underline{Y}}(s)$ on one side of the equation, factor out $\overline{\underline{Y}}(s)$, and isolate it as a single rational function:$$\overline{\underline{Y}}(s) = \frac{P(s)}{Q(s)}$$

    Here, the denominator $Q(s)$ corresponds to the characteristic polynomial of the ODE, while the numerator $P(s)$ contains the combined contributions of the initial conditions and the transformed forcing function.

3. Perform Partial Fraction Decomposition: Decomposes high-order rational expressions into standard transformable units.

    Because table lookup pairs consist of low-degree elementary terms, factor the denominator $Q(s)$ into linear or irreducible quadratic factors, then expand $\overline{\underline{Y}}(s)$ into simpler partial fractions:$$\overline{\underline{Y}}(s) = \frac{A}{s - p_1} + \frac{B}{s - p_2} + \frac{Cs + D}{(s - \alpha)^2 + \beta^2} + \dots$$

    Compute the unknown coefficients ($A, B, C, \dots$) using methods such as the Heaviside cover-up technique or polynomial coefficient matching.

4. Take the Inverse Laplace Transform: Transforms the algebraic expression back to the time-domain solution.

    Apply the inverse Laplace transform $\mathcal{L}^{-1}\{\cdot\}$ term by term to $\overline{\underline{Y}}(s)$ using standard transform pairs:
    - $\mathcal{L}^{-1}\left\{\frac{1}{s - a}\right\} = e^{at}$
    - $\mathcal{L}^{-1}\left\{\frac{\omega}{s^2 + \omega^2}\right\} = \sin(\omega t)$
    - $\mathcal{L}^{-1}\left\{\frac{s}{s^2 + \omega^2}\right\} = \cos(\omega t)$
    
    The resulting function $y(t) = \mathcal{L}^{-1}\{\overline{\underline{Y}}(s)\}$ is the unique solution to the IVP, naturally satisfying all initial conditions without requiring an auxiliary system of equations for integration constants.

#### Why do we use Laplace transform for solving differential equation?

To solve an ODE using the classical approach, we must follow these steps sequentially:
1. Find the homogeneous solution ($y_h$)
2. Find the particular solution ($y_p$)
3. Combine them to form the general solution ($y = y_h + y_p$)
4. Determine the constants of integration using the initial conditions (for an IVP)

As the order of the differential equation increases, Step 4 becomes computationally heavier because we must solve larger systems of simultaneous equations. In contrast, the Laplace transform naturally incorporates the initial conditions from the start, directly yielding the unique solution in a single algebraic workflow.


# Difference between an Integral Transform and a Standard Differential Operator

- Transform (e.g., Laplace / Fourier): Converts a function $f(t)$ into a new function $F(s)$ in a different domain (variable space)
- Operator (e.g., Differential / Shift): Maps a function $f(t)$ to another function $g(t)$ within the same domain (variable space)
