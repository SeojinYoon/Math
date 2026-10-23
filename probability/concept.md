
# Probability Distribution

A probability distribution is the overarching rule, law, or mathematical measure that dictates how total probability (which must sum or integrate to $1$) is allocated across all possible values a random variable can take.
- It is not restricted to a single equation; it is the theoretical behavior itself (e.g., "fair die distribution", "standard normal distribution", "Poisson process").
- Regardless of whether the random variable is discrete, continuous, or a mixture of both, it always possesses a probability distribution.
- To represent and calculate values from a distribution in practice, we use specific functions:
    - For discrete random variables $\rightarrow$ PMF
    - For continuous random variables $\rightarrow$ PDF
    - For all random variables $\rightarrow$ CDF (Cumulative Distribution Function, $F(x) = P(X \le x)$)

## Joint Probability Distribution

A joint probability distribution models the simultaneous behavior of two or more random variables defined on the same probability space. It captures not only the individual behavior of each variable, but also the statistical dependence and correlations between them.

1. Discrete Case: Joint Probability Mass Function (Joint PMF)

    For two discrete random variables $X$ and $Y$, the joint PMF $p_{X,Y}(x, y)$ evaluates the probability that $X$ takes the specific value $x$ and $Y$ simultaneously takes the value $y$:$$p_{X,Y}(x, y) = P(X = x, Y = y)$$

    A valid joint PMF satisfies:
    - $p_{X,Y}(x, y) \ge 0 \quad \text{for all } (x, y)$
    - $\sum_x \sum_y p_{X,Y}(x, y) = 1$

2. Continuous Case: Joint Probability Density Function (Joint PDF)

    For two continuous random variables $X$ and $Y$, probability over an exact point is zero. Instead, the joint PDF $f_{X,Y}(x, y)$ defines probability over a two-dimensional region $A \subseteq \mathbb{R}^2$:$$P((X, Y) \in A) = \iint_A f_{X,Y}(x, y) \, dx \, dy$$

    A valid joint PDF satisfies:
    - $f_{X,Y}(x, y) \ge 0 \quad \text{for all } (x, y) \in \mathbb{R}^2$
    - $\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx \, dy = 1$

## Marginal Probability Distribution

A marginal probability distribution is the probability distribution of an individual random variable (or a subset of variables) obtained by summing or integrating out all other variables from the joint distribution. This dimension-reduction process is termed marginalization.

1. Discrete Case: Marginal PMF

    To determine the distribution of $X$ alone, sum the joint probabilities over all possible outcomes of $Y$:$$p_X(x) = \sum_y p_{X,Y}(x, y)$$

    Similarly, for $Y$:$$p_Y(y) = \sum_x p_{X,Y}(x, y)$$

2. Continuous Case: Marginal PDF

    To determine the density of $X$ alone, integrate the joint density across the entire support of $Y$:$$f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dy$$

    Similarly, for $Y$:$$f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x, y) \, dx$$

Geometrically, marginalization in continuous space corresponds to projecting the two-dimensional density surface $f_{X,Y}(x, y)$ onto a single axis, collapsing the perpendicular dimension.

# Probability Density Function

A Probability Density Function (PDF), commonly denoted as $f(x)$ or $f_X(x)$, is a mathematical function that characterizes the distribution of an absolutely continuous random variable. It describes the relative likelihood of a variable taking a value near any given point on the real number line.

## Core Concept: Why Density Instead of Probability?

For continuous random variables (such as time, mass, or position), the support consists of uncountably infinite values. As a result, the probability of the variable taking any exact, isolated point is identically zero:$$P(X = x) = 0 \quad \text{for every } x \in \mathbb{R}$$

Because point probabilities vanish, continuous probability cannot be represented by point masses. Instead, $f(x)$ quantifies concentration—probability per unit length—analogous to physical linear mass density ($\lambda = dm/dx$).

The function value $f(x)$ is not a probability. A true probability is obtained exclusively by integrating the density over a finite interval $[a, b]$:$$P(a \le X \le b) = \int_{a}^{b} f(x) \, dx$$

#### Mathematical definition

In probability theory, convolution is the mathematical operation used to determine the probability distribution of the sum of two or more independent random variables:$$Z = X + Y$$

# Convolution

In probability theory, convolution is the mathematical operation that yields the probability distribution of the sum of two (or more) independent random variables:$$Z = X + Y$$

## Mathematical Definitions

1. Continuous Case: Convolution of PDFs

    Let $X$ and $Y$ be independent continuous random variables with probability density functions (PDFs) $f_X(x)$ and $f_Y(y)$. The PDF of their sum $Z = X + Y$, denoted $f_Z(z)$, is the continuous convolution of $f_X$ and $f_Y$:$$f_Z(z) = (f_X * f_Y)(z) = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx$$

    Because the convolution operator is commutative, this can equivalently be written as:$$f_Z(z) = \int_{-\infty}^{\infty} f_X(z - y) f_Y(y) \, dy$$
2. Discrete Case: Convolution of PMFs

    Let $X$ and $Y$ be independent integer-valued discrete random variables with probability mass functions (PMFs) $p_X(k) = P(X = k)$ and $p_Y(k) = P(Y = k)$. The PMF of $Z = X + Y$ is given by the discrete convolution sum:$$p_Z(n) = (p_X * p_Y)(n) = \sum_{k=-\infty}^{\infty} p_X(k) p_Y(n - k)$$

## Dummy Variable

In the convolution operation, the dummy variable (also called a bound variable) serves as an internal coordinate that parameterizes the **equality constraint** $x + y = t$. By enforcing this algebraic constraint, it collapses the two-dimensional input space into a one-dimensional trajectory, scanning across all permissible input pairs and vanishing entirely once the evaluation yields $(f * g)(t)$.

---

### 1. Mathematical Formulation

$$(f * g)(t) = \int_{-\infty}^{\infty} f(x) g(t - x) \, dx$$

- **Free Variable ($t$):** The fixed target output coordinate. The resulting function value depends strictly on this value.
- **Dummy Variable ($x$):** The internal scanning parameter bound by the integral operator $\int \dots dx$. It acts as the coordinate along the line $x + y = t$.

---

### 2. Operational Roles of the Dummy Variable

- **Pair Matching via Partition of the Target:**
  The fundamental objective of convolution is to accumulate all combinations of inputs whose sum satisfies the rigid constraint:
  $$x + y = t$$
  If the first input assumes value $x$, the second input is strictly constrained to $y = t - x$ so that $x + (t - x) = t$. The dummy variable $x$ sweeps from $-\infty$ to $+\infty$, systematically iterating over every valid decomposition of the target $t$.

- **Constraint-Driven Dimension Reduction:**
  In the two-dimensional state space $(x, y)$, the condition $x + y = t$ defines a 1D diagonal affine subspace (a line) with slope $-1$. 
  
  The dummy variable $x$ serves as the 1D coordinate running along this constrained trajectory. Evaluating the integral $\int \dots dx$ executes **marginalization**—it integrates all density along this diagonal slice, collapsing the 2D product space into a single evaluation point at $t$. Once the operation is complete, the dummy coordinate $x$ evaluates away entirely.

---

### Appendix: The Discrete Analogue (Grid Perspective)

The exact same constraint-driven reduction operates in discrete space:

$$(a * b)_n = \sum_{k=-\infty}^{\infty} a_k b_{n - k}$$

- **The Rigid Constraint ($i + j = n$):** In a 2D integer lattice $(i, j)$ formed by the outer product $a_i b_j$, the condition $i + j = n$ defines an anti-diagonal slice.
- **The Running Index ($k$):** The discrete dummy index $k$ scans along this anti-diagonal slice, collecting all pairs where $j = n - k$. Summing across $k$ collapses the 2D grid into the single sequence element $(a * b)_n$.

## Why does convolution matter?

Convolution is fundamentally about examining how two factors, $x$ and $y$, combine through the relationship $x + y = t$. Out of countless possible pairs of $(x, y)$, convolution selectively integrates only those combinations that satisfy this strict constraint. It is not merely a mathematical technique for solving equations; it is a conceptual framework for modeling complex systems by aggregating simple components. Science interprets the complex world by applying convolution as a tool for coarse-graining.

### 1. Observation Limitation: Coarse-Graining

In the real world, we often cannot isolate the exact individual contribution of each underlying factor because we can only observe the final aggregate result.

* **Microstate Combinations:** $(x = 1, y = 4)$, $(x = 2, y = 3)$, and $(x = 3.5, y = 1.5)$ are distinct, individual events at the microstate level.
* **Macrostate Observation:** However, from a macro-level perspective, our measurements record all these distinct combinations as the exact same aggregate value $t = 5$.

Therefore, to determine the probability of recording a specific macroscopic value $t$, we must accumulate the probabilities across all underlying microstates that yield that sum, regardless of their individual configurations. This process is known as **Coarse-graining**.

### 2. Physical Causality and Time Synchronization: "Past Event + Duration = Current"

In systems that evolve dynamically over time, the constraint $x + y = t$ represents strict temporal causality.

Consider the convolution integral:
$$(f * g)(t) = \int_{-\infty}^{\infty} f(x) g(t - x) \, dx$$

* **$x$:** The past time point when an event or stimulus occurs.
* **$y$:** The elapsed duration after that event occurred.

Physically, the sum of the event's occurrence time ($x$) and its elapsed duration ($y$) must equal the exact present moment ($t$) of observation:
$$x + y = t \implies y = t - x$$

In other words, focusing solely on the condition $x + y = t$ means: 

*"Among the countless effects originating from various moments in the past ($x$), we are gathering and summing up only those signals that, after passing through their respective elapsed times ($y$), simultaneously arrive right before us at this exact present moment ($t$)."*

### 3. The Probability Perspective: Deriving the Marginal Distribution via Convolution

In probability theory, convolution is not an operation designed to generate a joint distribution. Instead, it is the exact mathematical procedure for marginalizing a joint distribution to obtain the 1D marginal distribution of an aggregate random variable.

Suppose two independent continuous random variables, $X$ and $Y$, are defined by their individual probability density functions, $f_X(x)$ and $f_Y(y)$.

1. The Starting Point (Joint Distribution):

    Because $X$ and $Y$ are independent, their complete microstate space is already fully captured by their 2D joint probability density:$$f_{X, Y}(x, y) = f_X(x) f_Y(y)$$
2. The New Aggregate Variable ($T = X + Y$):

    In macroscopic observation, we do not track $X$ and $Y$ separately; we only care about their sum:$$T = X + Y$$

    Our goal is to derive the marginal probability density $f_T(t)$ for this single macro-variable $T$.
3. Marginalization along the Constraint Slice:

    To find the marginal density $f_T(t)$, we must integrate out the redundant microstate degrees of freedom across the 2D joint distribution, restricted strictly to the 1D diagonal slice where $x + y = t$ (i.e., $y = t - x$):$$f_T(t) = \int_{-\infty}^{\infty} f_{X, Y}(x, t - x) \, dx = \int_{-\infty}^{\infty} f_X(x) f_Y(t - x) \, dx = (f_X * f_Y)(t)$$

Convolution is therefore a dimension-reducing projection: it takes an existing 2D joint distribution and marginalizes it along the $x + y = t$ contour to yield the 1D marginal distribution $f_{T}(t)$ of the sum.

## Unit Consistency in Convolution

From the perspective of **dimensional analysis** and **physical causality**, the variables $x$, $y$, and $t$ must share identical units. The primary premise of convolution is the equality constraint:

$$x + y = t$$

A fundamental principle of addition is that terms can only be summed if they possess commensurate dimensions.

For instance, in time-series modeling (e.g., fMRI BOLD analysis):
* **$x$ (Onset):** The exact time a stimulus occurs (unit: seconds, $\text{s}$).
* **$y$ (Elapsed Time / Duration):** The time elapsed since that onset (unit: seconds, $\text{s}$).
* **$t$ (Current Time):** The present moment of observation (unit: seconds, $\text{s}$).

If these quantities were measured in conflicting units (e.g., seconds vs. milliseconds or scanner TR indices), the algebraic sum $x + y = t$ would be physically meaningless and distort the resulting response curve.

### The Infinitesimal Element ($dx$) and Scale Discrepancies in Signals/Probabilities

Examining the continuous convolution integral:

$$(f * g)(t) = \int f(x) g(t - x) \, dx$$

Here, the infinitesimal integration element $dx$ inherently shares the exact same physical unit as the variable $x$.

* **fMRI Example:**
  * If both $x$ and $t$ are measured in **seconds ($\text{s}$)**, then the integration element $dx$ is also in **seconds ($\text{s}$)**.
  * If $f(x)$ represents stimulus intensity and $g(t - x)$ is a dimensionless (or percentage signal change) HRF profile, the overall magnitude (scale) of the convolved output $(f * g)(t)$ is directly governed by the resolution and scale of the time unit.
  * If one variable is defined in seconds while another mistakenly uses the fMRI acquisition interval, **TR (e.g., in units of $2\,\text{s}$)**, the resulting curve will suffer from a twofold amplitude distortion or severe horizontal stretching, yielding an entirely invalid predictive model.



## Theoretical Derivation (From Joint Space to 1D Marginal)

The presence of the integral in the PDF formulation often raises a natural question: why integrate to find a density rather than a probability?

The answer lies in marginalization across the joint distribution.

1. Cumulative Distribution Function (CDF):

    The probability that $Z \le z$ defines the volume under the joint density surface $f_{X,Y}(x, y)$ over the half-plane $x + y \le z$:$$F_Z(z) = P(X + Y \le z) = \int_{-\infty}^{\infty} \left( \int_{-\infty}^{z - x} f_{X,Y}(x, y) \, dy \right) dx$$
2. Independence Condition:

    Because $X$ and $Y$ are independent, their joint density factors into the product of marginals: $f_{X,Y}(x, y) = f_X(x) f_Y(y)$.$$F_Z(z) = \int_{-\infty}^{\infty} f_X(x) \left( \int_{-\infty}^{z - x} f_Y(y) \, dy \right) dx$$
3. Differentiating to Recover Density:

   By the Fundamental Theorem of Calculus (Leibniz integral rule), differentiating $F_Z(z)$ with respect to $z$ removes the inner integral:$$f_Z(z) = \frac{d}{dz} F_Z(z) = \int_{-\infty}^{\infty} f_X(x) \left( \frac{d}{dz} \int_{-\infty}^{z - x} f_Y(y) \, dy \right) dx = \int_{-\infty}^{\infty} f_X(x) f_Y(z - x) \, dx$$ 

Thus, the convolution integral represents a line integral along the diagonal slice $x + y = z$ in the 2D joint probability space, collapsing the 2D joint distribution into a 1D marginal distribution.
