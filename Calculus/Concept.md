
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
