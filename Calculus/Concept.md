
# L'Hôpital's rule

L'Hôpital's rule is a method in calculus used to evaluate limits of indeterminate forms (specifically $\frac{0}{0}$ or $\frac{\pm\infty}{\pm\infty}$) by differentiating the numerator and the denominator separately.

## Mathematical Definition

Suppose $f(x)$ and $g(x)$ are differentiable near a point $c$ (or as $x \to \pm\infty$), with $g'(x) \ne 0$ near $c$.

- Indeterminate Form Condition:$$\lim_{x \to c} f(x) = 0 \quad \text{and} \quad \lim_{x \to c} g(x) = 0$$or$$\lim_{x \to c} f(x) = \pm\infty \quad \text{and} \quad \lim_{x \to c} g(x) = \pm\infty$$

- Existence of Derivative Limit:$$\lim_{x \to c} \frac{f'(x)}{g'(x)} = L \quad (\text{where } L \text{ is finite or } \pm\infty)$$

If these conditions hold, then:$$\lim_{x \to c} \frac{f(x)}{g(x)} = \lim_{x \to c} \frac{f'(x)}{g'(x)}$$

Key Point: Do not use the Quotient Rule on $\frac{f(x)}{g(x)}$; instead, take the derivative of the numerator $f'(x)$ and the derivative of the denominator $g'(x)$ independently.

## Why Is It Called a "Rule" Instead of a "Theorem"?

In calculus, procedural techniques and computation recipes that simplify algebraic manipulation are traditionally called "rules" (e.g., the Chain Rule, Product Rule, Quotient Rule, and Cramer's Rule), even though they are all mathematically proven theorems.

## When Not to Use L'Hôpital's Rule

If the functions are continuous at $x = c$ and their direct substitution values are easily determined without yielding indeterminate forms, L'Hôpital's rule is completely unnecessary.

### 1. Determinate Forms (Direct Substitution)
When direct evaluation yields a clear, well-defined finite value:
$$\lim_{x \to 2} \frac{x^2 + 1}{x + 3} = \frac{2^2 + 1}{2 + 3} = \frac{5}{5} = 1$$
Here, both $f(c)$ and $g(c)$ are known and the denominator is non-zero ($g(c) \ne 0$). Applying L'Hôpital's rule here would lead to an incorrect result:
$$\frac{(x^2+1)'}{(x+3)'} = \frac{2x}{1} \xrightarrow{x=2} 4 \quad (\text{Incorrect})$$

### 2. Simple Non-Zero over Zero ($\frac{k}{0}$ where $k \ne 0$)
When the numerator approaches a non-zero number while the denominator approaches zero:
$$\lim_{x \to 0} \frac{\cos x}{x} = \frac{1}{0} \implies \text{Diverges to } \pm\infty$$
This is an asymptotic vertical behavior, not an indeterminate form. L'Hôpital's rule must not be applied.

---

### Key Takeaway
> **L'Hôpital's rule is specifically a tool for uncertainty.**  
> When the destination values ($f(c)$ and $g(c)$) are obvious and determinate, simply evaluate them directly. L'Hôpital's rule becomes indispensable only when direct evaluation collapses into the indeterminate forms $\frac{0}{0}$ or $\frac{\pm\infty}{\pm\infty}$, leaving the relative scale of the two functions hidden.

### Why Does It Work Only for Indeterminate Forms?

1. **When Values Are Well-Defined (Non-Zero):**
   If two runners are at the 100m and 20m marks respectively, their relative position is simply $\frac{100}{20} = 5$. Their instantaneous running speeds (derivatives) do not determine their current ratio because their absolute positions dominate.

2. **When Indeterminate Forms Appear ($0/0$):**
   If both runners start simultaneously from the origin ($0$m), their positions give no meaningful proportion ($\frac{0}{0}$). As time progresses infinitesimally ($t > 0$), their relative distance is determined entirely by how fast each runner accelerates away from zero. 
   
> **Key Intuition:** 
> When absolute positions vanish ($0/0$), the ratio of their values is entirely governed by the ratio of their rates of change (velocities, $f'(x)/g'(x)$).

## Their Relative Relationship

**A Ratio of Two Functions**

Consider two functions expressed as a ratio:

$$\frac{f(x)}{g(x)}$$

Rather than thinking of the two functions as directly influencing each other, we can interpret this ratio as describing how one function changes relative to the other.

An interesting problem arises when both functions approach zero or both approach infinity.

$$0/0$$
Both functions are pushed toward zero.

However, simply knowing that both disappear does not tell us which one disappears faster, or whether they disappear at approximately the same rate.

$$\infty/\infty$$
Both functions expand without bound.

But simply knowing that both become infinitely large does not tell us which one grows faster, or whether they grow while maintaining some stable relative proportion.

Therefore, the important question is no longer simply:

“Where are the two functions going?”

Instead, it becomes:

“As they approach that state, how are they growing or diminishing relative to each other?”

**L’Hôpital’s Rule — Looking at Relative Change**

In the indeterminate forms $0/0$ and $\infty/\infty$, the values of the functions alone are not sufficient to determine their relationship.

L’Hôpital’s rule therefore shifts our attention from where the functions are to how the functions are changing.

We differentiate the two functions,

$f'(x), g'(x) $

and examine

$$ \frac{f'(x)}{g'(x)} $$

This allows us to compare their relative rates of change.

In other words, as we approach a particular point, we examine how rapidly one function grows or diminishes relative to the other, and use this relationship to determine what their ratio ultimately approaches.

The central intuition behind L’Hôpital’s rule can therefore be expressed as:

    When the absolute states of two functions are insufficient to reveal their relationship, we compare how they change in order to understand their relative relationship in the limit.

- Both functions may disappear toward zero.
- Both may expand toward infinity.

But the important question is not only where they are going. It is how they are changing relative to each other as they approach that state.

If this relative relationship approaches some value L,

$$\lim_{x\to a}\frac{f(x)}{g(x)} = L$$

then near the point a

$$f(x) \approx L\,g(x)$$

So L does not mean that a function “increases by L.” Rather, it tells us the relative scale of one function compared with the other near the limit.

- If $L=2$, then $f(x)$ is approximately twice the size of $g(x)$ near the limit.
- If $L=0$, then $f(x)$ becomes negligible compared with $g(x)$.
- If $L=\infty$, then $f(x)$ grows or dominates much more strongly than $g(x)$.

**Summary**

L’Hôpital’s rule is not about determining the state of a function at a particular point from its slope. Rather, when two functions approach a limiting state, it examines the relationship between their rates of change to reveal the relative relationship that remains between them in the limit.

**Engineering view point**

The result obtained through L’Hôpital’s rule can be interpreted as representing the relative magnitude or dominance between two components of a system as the system approaches a particular limiting condition.

**Philosophical view point - relative order**

Philosophically, L’Hôpital’s rule can be viewed as revealing the relative relationship between two competing wills within a person as that person approaches an extreme or limiting state. At the limit, what remains is not the absolute state of each will, but the relationship between them.

# Differentiable

## Trackable

A function being differentiable can be understood as its change being trackable.

Instead of merely observing the current state of a function, differentiation allows us to track in which direction and how rapidly the function is changing at a particular point.

# Limit

## Phylosophical interpretation: Pushing the Will to Its End

A limit describes the process of continuously approaching a particular point.

From the perspective of “will,” we can think of it as asking:

If we keep pushing something toward a particular direction or state, where does it ultimately tend to go?

**The left-hand and right-hand limits are equal**
Even when approaching from two different directions or states, if both processes are pushed toward the same point, they eventually converge to the same state.

**The limit approaches infinity**
As the process is pushed further and further, the value does not settle at any finite state but continues to expand without bound.

**The limit approaches zero**
As the process is pushed further and further, the magnitude of the function becomes smaller and smaller, eventually approaching a state of nothingness.

# Improper Integral

Improper integral은 일반적인 Riemann integral의 정의를 직접 적용할 수 없는 구간이나 함수에 대해 극한(Limit)을 이용하여 정의한 적분이다.

일반적인 정적분 $\int_{a}^{b} f(x)\,dx$은은 다음 두가지 조건이 필요하다.
1. 적분 구간 $[a, b]$가 유한한 닫힌 구간이어야 함
2. 피적분함수 $f(x)$가 해당 구간에서 유계(bounded, 무한대로 발산하지 않음)이어야 함.

이 둘 중 하나라도 만족하지 못할 때 이상적분을 사용한다.

## 이상적분의 두 가지 유형

1. Infinite Intervals

   적분 구간의 한쪽 또는 양쪽 끝이 무한대인 경우이다.

   정의 방식: $$\int_{a}^{\infty} f(x)\,dx = \lim_{t \to \infty} \int_{a}^{t} f(x)\,dx$$

   예시: $$\int_{1}^{\infty} \frac{1}{x^2}\,dx = \lim_{t \to \infty} \left[ -\frac{1}{x} \right]_{1}^{t} = \lim_{t \to \infty} \left( 1 - \frac{1}{t} \right) = 1$$

2. Unbounded / Discontinuous Integrands

   적분 구간은 유한하지만, 구간의 끝점이나 내부에서 함수가 $\pm\infty$로 발산하는 경우이다.

   - 정의 방식 (극한 사용, $x=a$에서 발산할 때):$$\int_{a}^{b} f(x)\,dx = \lim_{t \to a^+} \int_{t}^{b} f(x)\,dx$$
   - 예시 ($x=0$에서 $1/\sqrt{x} \to \infty$):$$\int_{0}^{1} \frac{1}{\sqrt{x}}\,dx = \lim_{t \to 0^+} \left[ 2\sqrt{x} \right]_{t}^{1} = \lim_{t \to 0^+} (2 - 2\sqrt{t}) = 2$$

# The Distinction Between Differential and Derivative

In calculus, decomposing a quantity $y$ into an infinitesimal change element $dy$ is the operation called taking the differential, whereas dividing this element by $dx$ gives the derivative.
- Extracting the Infinitesimal Element (Differential):$$y \;\longrightarrow\; dy$$  
   This isolates the pure infinitesimal increment $dy$ generated when the overall state $y$ undergoes a slight variation.
- Computing the Rate of Change (Derivative):$$y \;\longrightarrow\; \frac{dy}{dx}$$  
   This scales the decomposed change $dy$ relative to the driving increment $dx$. It normalizes the variation into a ratio (velocity, slope, or sensitivity), describing how many units the output changes per unit change in input.

# The Fundamental Duality: Differentiation and Integration

Placing these operations in direct correspondence reveals their core structural symmetry:

- Differentiation ($y \rightarrow dy$): 

   Peels back the accumulated whole y, disassembling it into momentary increments of change (dy).

- Integration ($dy \rightarrow y$):

   Accumulates every single infinitesimal slice ($dy$) from beginning to end using the integral operator $\int$ (derived from summa). By stitching these infinitely many tiny pieces back together, it restores the complete cumulative whole $y$:$$\int dy = y$$

Taking the differential deconstructs a whole into infinitesimal pieces; integration collects every piece from start to finish to restore the whole.

# Why Do We Break Things Down?

Because our perception is far narrower than the world itself, we inevitably break things down and piece them back together—much like differentiation and integration—to expand the boundaries of our understanding. Likewise, we dissect the brain down to single neurons, hoping that by aggregating this knowledge, we might ultimately reconstruct intelligence in artificial form.

# Differentiation

Differentiation is the act of zooming in on the change in one quantity relative to the change in another.

In this sense, differentiating $e^x$ is the act of observing how $e^x$ changes relative to $x$ at a local scale. Remarkably, the derivative of $e^x$ is simply $e^x$ itself, which means its instantaneous rate of change is directly determined by its current value.

## Definition of differentiation

Differentiation can be formalized through several distinct mathematical perspectives, ranging from classical difference quotients to modern linear approximation and rigorous analytical limits.

### Difference Quotient

The classical formulation defines the derivative as the limit of the average rate of change (the difference quotient) as the interval approaches zero. Geometrically, this represents the slope of the secant line converging to the slope of the tangent line.
- Increment Form ($h \to 0$ or $\Delta x \to 0$):

   For an open interval containing $x$, the derivative $f'(x)$ is defined as:$$f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h} = \lim_{\Delta x \to 0} \frac{f(x + \Delta x) - f(x)}{\Delta x}$$

   While mathematically identical, the two notations emphasize different mathematical nuances:
   - $\Delta x$ (Geometric & Differential Focus): Explicitly denotes the actual macroscopic displacement $\Delta x$, expressing the quotient as $\frac{\Delta y}{\Delta x}$. This highlights the geometric ratio of coordinate increments and provides a seamless conceptual bridge to Leibniz's differential notation:$$\lim_{\Delta x \to 0} \frac{\Delta y}{\Delta x} = \frac{dy}{dx}$$
   - $h$ (Algebraic & Perturbation Focus): Replaces the compound symbol $\Delta x$ with a single scalar parameter representing a small offset or perturbation. This simplifies complex algebraic manipulation (e.g., binomial expansions, Taylor series, and finite difference schemes) by keeping algebraic derivations free of repetitive parentheses and compound symbols.

- Fixed-Point Form ($x \to a$):
   
   At a specific evaluation point $a$:$$f'(a) = \lim_{x \to a} \frac{f(x) - f(a)}{x - a}$$

   This representation is especially useful for verifying one-sided derivatives (left- and right-hand limits) to establish differentiability at boundaries or piecewise transitions.

### Carathéodory / Landau

Rather than relying purely on quotient limits, modern analysis often frames differentiation as optimal local linear approximation. This perspective generalizes cleanly to multivariable calculus, Banach spaces, and manifold theory.

- Landau Notation ($o(h)$ Formulation):

   A function $f$ is differentiable at $x$ if there exists a constant $A \in \mathbb{R}$ such that:$$f(x + h) = f(x) + A \cdot h + o(h) \quad \text{as } h \to 0$$

   where $o(h)$ denotes Little-$o$ asymptotic notation satisfying $\lim_{h \to 0} \frac{o(h)}{h} = 0$.The unique constant $A$ is the derivative $f'(x)$. Here, differentiation directly extracts the best linear map approximating the local displacement $\Delta f$.

- Carathéodory's Formulation:

   A function $f$ is differentiable at $a$ if and only if there exists a function $\phi(x)$ that is continuous at $a$ such that:$$f(x) - f(a) = \phi(x)(x - a)$$

   If this holds, the derivative value is given by:$$f'(a) = \phi(a)$$

   Because this formulation eliminates division by zero ($x - a$), it provides an exceptionally elegant proof of the Chain Rule without needing piecewise cases for when the intermediate displacement vanishes.

### $\epsilon$-$\delta$

   The rigorous analytical formulation replaces the informal notion of "approaching zero" with quantified topological neighborhoods via Cauchy and Weierstrass's $\epsilon$-$\delta$ criteria.

   A function $f$ is differentiable at a point $a$ with derivative $L = f'(a)$ if and only if for every $\epsilon > 0$, there exists a $\delta > 0$ such that:$$0 < \vert{}x - a\vert{} < \delta \implies \left\vert{} \frac{f(x) - f(a)}{x - a} - L \right\vert{} < \epsilon$$

   Equivalently, expressed in terms of the increment $h = x - a$:$$\forall \epsilon > 0, \; \exists \delta > 0 \quad \text{such that} \quad 0 < \vert{}h\vert{} < \delta \implies \left\vert{} \frac{f(a + h) - f(a)}{h} - L \right\vert{} < \epsilon$$

   This guarantees that the error between the secant slope and the tangent slope L can be bounded arbitrarily tightly within a sufficiently small punctured symmetric neighborhood around a.

# Definite integral

## Dummy variable

A dummy variable is an auxiliary variable used temporarily during the calculation or expansion of a definite integral; it has no effect on the final value of the integral. In logic and mathematics, it is also referred to as a **bound variable**.

### Core Property: Invariance Under Variable Renaming

The value of a definite integral depends only on the integrand and the limits of integration. Therefore, replacing the dummy variable with any other symbol does not alter the result: $$\int_{a}^{b} f(x) \, dx = \int_{a}^{b} f(t) \, dt = \int_{a}^{b} f(u) \, du$$

**Example:**

   $$\int_{0}^{2} x^2 \, dx = \left[ \frac{1}{3}x^3 \right]_{0}^{2} = \frac{8}{3}$$

   $$\int_{0}^{2} t^2 \, dt = \left[ \frac{1}{3}t^3 \right]_{0}^{2} = \frac{8}{3}$$

Since $x$ and $t$ disappear once evaluated, they are dummy variables.

### Functions Defined by Integrals (Avoiding Variable Collision)

The concept of a dummy variable becomes essential when a variable appears in the limits of integration.

In the Fundamental Theorem of Calculus (FTC), consider a function $F(x)$ defined as: $$F(x) = \int_{a}^{x} f(t) \, dt$$
* **Free Variable ($x$):** Acts as the independent input to the function $F$, determining the upper limit of integration.
* **Dummy Variable ($t$):** A temporary variable sweeping through the integration interval from $a$ to $x$ to accumulate the area.

> **Variable Shadowing (Collision):**  
> Writing $\int_{a}^{x} f(x) \, dx$ creates a notation collision: $x$ simultaneously represents a fixed boundary and a variable of integration. To avoid ambiguity and mathematical errors, the internal integration variable must be separated using a different symbol such as $t$, $u$, or $\tau$.

# Integral

The word **integral** originates from the Latin *integer*, meaning "whole" or "undiminished"—capturing the idea of assembling finely sliced pieces into a complete whole.

Mathematically, what an integral accumulates is the product of an instantaneous rate ($f'(x)$) and an infinitesimal change ($dx$). This product represents a micro-slice: visually, the area of an infinitesimal rectangle ($f'(x) \cdot dx$); physically, an infinitesimal increment of actual change ($dy$).

If tiling rectangles serves as the geometric vehicle, integration is formally the continuous accumulation of infinitesimal rectangles and fundamentally the calculation of a system's net physical change

In kinematics, this duality maps directly to velocity, time, and distance: on a velocity-time plot, the infinitesimal rectangle has height $v(t)$ (rate) and width $dt$ (time), whose product—the micro-area—is arithmetically the slice of distance covered:$$\int_{t_1}^{t_2} \underbrace{v(t)}_{\text{Height}} \cdot \underbrace{dt}_{\text{Base}} = \int_{s_1}^{s_2} \underbrace{ds}_{\text{Slice}} = \underbrace{s(t_2) - s(t_1)}_{\text{Total Change}}$$

Accumulating these rectangles across time simply integrates every momentary displacement to recover the net distance traveled.

## Two Perspectives: Method (Exhaustion) vs. Reality (Change)

To understand integration without confusion, we must distinguish between **the calculation tool we use (The Method of Exhaustion / Riemann Sum)** and **the physical reality it recovers (Accumulated Change)**:

$$\int_{a}^{b} f'(x) \, dx = \lim_{n \to \infty} \sum_{i=1}^{n} \underbrace{f'(x_i)}_{\text{Height}} \cdot \underbrace{\Delta x}_{\text{Base}} = \sum dy = f(b) - f(a)$$

---

### 1. The Method: Method of Exhaustion
The **Method of Exhaustion** (formalized by Riemann sums) is the mathematical *engine* of definite integration:

1. **Slice the Domain:** Subdivide the interval $[a, b]$ into $n$ ultra-narrow slices of width $\Delta x$.
2. **Flatten the Curve:** Over an infinitesimal step, the slope variation vanishes, allowing us to approximate each slice as an upright rectangle with height equal to the local rate $f'(x_i)$.
3. **Tile and Sum:** Sum the areas of all vertical rectangles:
   $$\text{Area}_n = \sum_{i=1}^{n} f'(x_i) \cdot \Delta x$$
4. **Take the Limit ($n \to \infty$):** As $\Delta x \to 0$ ($dx$), all approximation gaps disappear, converging rigorously to the definite integral $\int_{a}^{b} f'(x)\,dx$.

The Method of Exhaustion is not wrong; it is the **formal foundation** that proves and computes the value of an integral.

---

### 2. The Physical Reality: What is the Area Actually Doing?
While the *canvas* displays rectangles being tiled horizontally, look at what the algebra of a single rectangle actually computes:

$$\text{Rectangle Area} = \underbrace{f'(x)}_{\text{Rate } \left(\frac{dy}{dx}\right)} \times \underbrace{dx}_{\text{Step width}} = dy \quad (\text{Actual vertical displacement})$$

* **In Rate Space ($x \text{ vs. } f'(x)$):** The product $f'(x) \cdot dx$ represents a **2D rectangular surface area**.
* **In State Space ($x \text{ vs. } y$):** That exact same product represents a **1D vertical increment ($dy$)**—how much the cumulative quantity $y$ actually grew during that instant.

---

### 3. Summary of Roles

* **The Method (Method of Exhaustion):** Slices the rate curve into rectangles to make an otherwise curved, changing quantity numerically computable.
* **The Visual Proxy:** The total 2D area under the $f'(x)$ curve.
* **The Underlying Truth:** Stacking those rectangular areas is algebraically identical to stringing together infinitesimal changes of state ($dy$), reconstructing the total net change:
  $$\int_{a}^{b} f'(x) \, dx = \int_{y(a)}^{y(b)} dy = f(b) - f(a)$$