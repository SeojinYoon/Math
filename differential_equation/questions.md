
# What is ODE?

The differential equation(DE) describes the direction and rate of change of a system given its current state. An ordinary differential equation(ODE) does this with respect to a single independent variable.

**Note, the meaning of state and system**: I used to be confused every time I saw the definition of a differential equation. While many explanations are intuitive, they often fail to define what 'state' and 'system' actually mean. The meaning of state is the dependent variable ($y$), while the system is the mechanism that describes the change of state given a specific independent variable ($x$) and the current state ($y$). This concept becomes much clearer when you look at the equation:$$\frac{dy}{dx} = f(x, y)$$This equation describes how the state ($y$) changes with respect to both the independent variable and its own current value. This is precisely how a system is formulated within a differential equation.

**Note on Explicit vs. Implicit Expressions**: I find it much more intuitive to view a differential equation as an explicit function. In that form, the right-hand terms clearly describe the rate of change of the state. In contrast, implicit expressions like$$\frac{dy}{dx} - f(x, y) = 0$$can feel somewhat ambiguous at first glance.

If the system follows its own internal laws without any external influence, it is expressed as a homogeneous equation. However, when an external force or input ($g(x)$) is applied, it becomes an inhomogeneous equation, describing how the system's state responds to that external stimulus while still respecting its internal mechanism

**Note on Homogenous vs. Inhomogenous**: So far, I have described the left side of an implicit differential equation as the 'system's rule'. When this rule equals zero, it is a homogeneous equation, meaning the system simply follows its own internal laws of equilibrium. However, in an inhomogeneous equation, the right side is non-zero. From the viewpoint of the system's rule, this means the system is forced to align its internal state with that right-hand value—even if it cracks the system's original equilibrium. In other words, the right side acts as a commanding 'input' that the internal rule must now satisfy.

For example, in a physics engine, if a ball falls under gravity and encounters wind, the wind itself is the external input. The resulting movement of the ball is the change of state ($y$), which occurs as the system satisfies the external force of the wind while respecting its internal rule of gravity. Ultimately, the solution to this inhomogeneous equation represents the continuous equilibrium points where the internal mechanism and the external force reach a mathematical balance.

## What is the difference between DE and Equation?

An equation defines a constraint (relation) between variables. In contrast, a differential equation (DE) describes a rule governing how a dependent variable changes with respect to an independent variable.

Solving an equation means finding all possible states (points) that satisfy the given constraint. In contrast, solving a DE means finding a function (or a family of functions) whose derivative satisfies the given rule.

Consider the equation $x^2 + y^2 = 4$. Its solution $\{(x,y)\in\mathbb{R}^2 \mid x^2 + y^2 = 4\}$ is the set of all states (x,y) satisfying the equation. Now consider the differential equation $y' + 2x = 4$. Its solution is $y(x) = 4x - x^2 + C$ ,which represents a family of functions describing the possible state trajectories of y as a function of x.

If the independent variable is time, the solution of a DE can be interpreted as the time evolution (trajectory) of a system given an initial condition. Philosophically, solving a differential equation corresponds to predicting the future behavior of a system based on its governing dynamics and the principle of causality.

# Are the symbols y and f the same in y' = f(x,y)?

No, The symbols y and f are different. The symbol f represents a rule that combines x and y to determine how the system changes.

For example, consider the equation. $ y' = f(x, y) $. If we int erpret the y' as the gradual change of position with respect to time, the y represents position and x represents time. The function f describes how the current state (x,y) determines this rate of change.

Thus, f is the mechanism of a two-variable state system, and y' is the output of that system, representing how the position changes at a given time and location.

# Why do we need a initial value to solve differential equation?

Mathematically, solving a differential equation requires integration, which converts an equation for a derivative into an equation for the original function. Let us think in reverse. Suppose the original equation describing the history of $y$ is $y = x^2 + 3$. If we differentiate it, the constant disappears, giving $y’ = 2x$. Since integration is the inverse operation of differentiation, integrating $2x$ gives $x^2 + C$. However, the constant $C$ cannot be determined from the differential equation alone. To determine $C$, we need an initial condition (or initial state) for the differential equation. A problem given by a differential equation together with an initial value is called an Initial Value Problem (IVP).

Let's consider this equation. $ a(x)y' + b(x)y = c(x) $

# What is standard linear form?

The standard linear form is a clear and standardized way to represent a first-order linear differential equation so that it can be solved systematically. This form provides a systematic view by separating the system the system dynamics $p(x)$ from the external input $Q(x)$. The term $p(x)y$ represents the rate of change depending on current state, whereas $q(x)$ represents an external input that is independent of the current state.

It has the form $ \frac{dy}{dx} + p(x)y = q(x) $ 

This form satisfies the following conditions.
1. The coefficient of $\frac{dy}{dx}$ is 1.
2. The term involving y appears on the left-hand side.
3. The term depending only on x appears on the right-hand side.

## Why do we convert the DE into a standard linear form?

In the stardard linear form, we can solve the equation mechanically using a method called intergral factor. Here is the integrating factor $ μ(x) = e^{\int{p(x)}dx} $. 

### Where the integrating factor come frome?

The integrating factor is a function introduced to transform a first-order linear differential equation into the derivative of a product (via the product rule).

Let me explain this in detail. Consider the standard linear form: $y' + p(x)y = q(x)$, we multiply both sides by a function $u(x)$, obtaining $uy' + p(x)uy = q(x)u$. Using the product rule, $(uy)' = uy' + u'y = q(x)u$. To rewrite the left-hand side as $q(x)u$, we require $ u' = p(x)u $. This differential equation can be solved by separation of variables: $\frac{1}{u}du = p(x)dx $. Integrating both side gives $ln(u) = \int{p(x)}dx$ and therefore, $u = e^{\int{p(x)}dx}$.

