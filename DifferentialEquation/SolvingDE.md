
# How to solve differential equation?

## Separation of Variables

The difficulty of solving a differential equation comes from the fact that x and y are entangled. In fact, the goal of solving an ordinary differential equation is often to rewrite it in a form with separated variables. 

This raises the question: "Why do entangled variables make problems difficult to solve?". Consider the following expression. Suppose that y depends on x, but the functional relationship between them is unknown. Let's see the following equation.

$$ \frac{dy}{dx} = xy $$

To solve this, one might attempt to integrate both sides.

$$ \int{\frac{dy}{dx}}dx = \int{xy}dx $$

However, the expression $xy$ is difficult to integrate because the dependence of $y$ on $x$ is unknown. To overcome this, we used to do separation of variables. Separation of variables is a technique where we rearrange the equation such that all terms involving y are on one side (with $dy$) and all terms involving $x$ are on the other side (with $dx$):

$$ \frac{dy}{y} = xdx $$

By doing this, we bypass the problem of y being an unknown function of x within the integral. Now, both sides can be integrated independently.

$$ \int{\frac{dy}{y}}dy = \int{x}dx $$

This effectively 'de-couples' the variables, turning a complex differential relationship into two straightforward integration problems. Generally, we can re-write the separation of variables like that.

$$\int{f(y)}dy = \int{g(x)}dx$$

## Substitution

The substitution method is a technique to achieve a goal for separation of variables. Consider the following equation:

$$ \frac{dy}{dx} = (x + y)^2 $$

This equation is difficult to solve directly because the variables $x$ and $y$ are entangled in the term $(x + y)$, which prevents direct separation of variables.

We can simplify the problem using the substitution method. Let $u = x + y$ and substitute it into the equation. The right-hand side can then be written easily as $u^2$. 

$$ \frac{dy}{dx} = (x + y)^2 = u^2$$

However, we must also rewrite the left-hand side in terms of $u$. For replace the left side into the $u$ notation, we need to find the derivative relationship amoung $x$,$y$ and $u$. To do this, we find the derivative relationship between $x$, $y$, and $u$ by differentiating our substitution:

$$ u = x + y $$
$$ \rightarrow \frac{du}{dx} = \frac{dx}{dx} + \frac{dy}{dx} $$
$$ \rightarrow \frac{dy}{dx} = \frac{du}{dx} - 1 $$

Now, we have all the ingredients to apply the substitution method. 

1. Substitution: 
    $$ \frac{du}{dx} - 1 = (u^2) $$
2. Separation of variables:
    $$\frac{1}{u^2 + 1}{du} = dx $$

## Integrating factor

After finding an integrating factor, we multiply it on both sides of the equation. This transforms the equation into a form that can be written as a derivative. Then, we integrate the equation to find the solution.

Here is the procedure for solving a first-order linear ODE

1. Convert the ODE into the standard linear form.
    - $y' + p(x)y = q(x)$
2. Find the integrating factor.
    - $u(x) = e^{\int{p(x)}dx}$
3. Multiply both sides of the equation by the integrating factor.
    - $u(x)y' + u(x)p(x)y = u(x)q(x)$
4. Rewrite the left-hand side as a derivative
    - $(uy)' = q(x)u$
5. Integrate both sides.
    - $\int{(uy)'}dx = uy + C = \int{q(x)u(x)}dx + C$
6. Find the general solution.
    - $y = \frac{\int{q(x)u(x)}dx + C}{u}$
7. Find the particular solution using the initial condition $(y(x_0) = y_0)$
    - Substitute x=0 and y=y_0 into the general solution
        - $y_0 = \frac{\int q(x)u(x)dx \big|_{x=x_0} + C}{u(x_0)}$
    - Rearrange the equation to isolate the constant $C$. Once $C$ is found, substitute it back into the general solution to obtain the particular solution.

Let's solve this equation by the above procedure: $ xy' - y = x^3 $.

- First, we need to convert the equation into the standard linear form: $y' -\frac{1}{x}y = x^2$
- Second, let's find the integrating factor: $u = e^{-(\int{\frac{1}{x}}dx)} = (e^{ln(x)})^{-1} = \frac{1}{x}$.
- Third, multiply both sides of equation by the integrating factor: $\frac{1}{x}y' - \frac{1}{x^2}y = x$
- Fourth, rewrite the left side as as derivatve: $(\frac{1}{x}y)' = x$
- Fifth, integrate both sides: $\frac{1}{x}y = \frac{1}{2}x^2 + C$
- Sixth, find the general solution: $y = \frac{1}{2}x^3 + Cx$

# In case of the physical input is trigonometric

Let's consider the equation: $y' + ky = kq_e(t)$, where $q_e(t) = k \cos(\omega t)$. One standard approach is to use an integrating factor.
1. Find the integrating factor: $\mu(t) = e^{\int k dt} = e^{kt}$
2. Multiply both sides by $\mu(t)$: $e^{kt}y' + ke^{kt}y = k e^{kt} \cos(\omega t)$
3. Rewrite the left-hand side as a derivative: $\frac{d}{dt}(e^{kt}y) = k e^{kt} \cos(\omega t)$
4. Integrate both sides: $e^{kt}y = \int k e^{kt} \cos(\omega t) dt$

However, evaluating this integral requires integration by parts twice, which is algebraically tedious. To avoid this complexity, we can instead use Euler's formula ($e^{i\omega t} = \cos \omega t + i \sin \omega t$) and the superposition principle.

The strategy is to transform the original problem into a complex differential equation:

$$\tilde{y}' + k\tilde{y} = k e^{i\omega t}$$

where $\tilde{y} = u + i v$. Once we solve for $\tilde{y}$, we simply take the real part of the solution. This method is justified by the linearity of the operator $L$ and the superposition principle. Since $L$ is a linear operator, the equation for $\tilde{y}$ can be split into its real and imaginary components:
$$L(\tilde{y}) = L(u + i v) = k \cos(\omega t) + i k \sin(\omega t)$$
$$L(u) + i L(v) = k \cos(\omega t) + i k \sin(\omega t)$$

Let's solve the differential equation: $\tilde{y}' + k\tilde{y} = ke^{i\omega t}$. 
1. Find the integrating factor: 
$$\mu(t) = e^{kt}$$
2. Multiply both sides by $\mu(t)$:
$$e^{kt}\tilde{y}' + ke^{kt}\tilde{y} = ke^{(k+i\omega)t}$$
3. Rewrite the left-hand side as a derivative: 
$$\frac{d}{dt}(e^{kt}\tilde{y}) = k e^{(k+i\omega)t}$$
4. Integrate both sides: 
$$e^{kt}\tilde{y} = \int k e^{(k+i\omega)t} dt = \frac{k}{k+i\omega} e^{(k+i\omega)t} + C$$
5. Solve for $\tilde{y}$: Divide both sides by $e^{kt}$ to isolate $\tilde{y}$:
$$\tilde{y} = \frac{k}{k+i\omega} e^{i\omega t} + Ce^{-kt}$$
6. The solution can be decomposed into a steady-state part and a transient part:
$$\tilde{y}(t) = \underbrace{\frac{k}{k+i\omega} e^{i\omega t}}_{\text{steady-state}} + \underbrace{Ce^{-kt}}_{\text{transient}}$$

The transient term $Ce^{-kt}$ decays to zero as $t \to \infty$, leaving only the steady-state response.

We found the solution of $\tilde{y}$, but to take find solution of y, we need to take the real part from it. To find the physical solution $y(t) = \text{Re}\{\tilde{y}(t)\}$, we need to transform the complex expression into a form where the real part is easily identifiable.

1. Express the complex amplitude in polar form

    The complex amplitude is $Y = \frac{k}{k+i\omega}$. To find its magnitude and phase:
    - Magnitude ($|Y|$): $|Y| = \frac{|k|}{|k+i\omega|} = \frac{k}{\sqrt{k^2 + \omega^2}}$
    - Phase ($\phi$): The denominator $k+i\omega$ has a phase of $\phi = \arctan(\omega/k)$. Since it's in the denominator, the total phase is $-\phi$.
    - Thus, we can rewrite $Y$ as:
    $$Y = \frac{k}{\sqrt{k^2 + \omega^2}} e^{-i\phi}$$
2. Combine with the time-varying part. Substitute this $Y$ back into the steady-state part of $\tilde{y}$:
    $$\tilde{y}_{ss} = Y e^{i\omega t} = \left( \frac{k}{\sqrt{k^2 + \omega^2}} e^{-i\phi} \right) e^{i\omega t}$$
    $$\tilde{y}_{ss} = \frac{k}{\sqrt{k^2 + \omega^2}} e^{i(\omega t - \phi)}$$

3. Apply Euler's formula and take the Real Part 
    Using Euler's formula ($e^{i\theta} = \cos\theta + i\sin\theta$):
    $$\tilde{y}_{ss} = \frac{k}{\sqrt{k^2 + \omega^2}} \left[ \cos(\omega t - \phi) + i\sin(\omega t - \phi) \right]$$
    Now, simply take the Real part ($\text{Re}$):
    $$y(t) = \text{Re}\{\tilde{y}_{ss}\} = \frac{k}{\sqrt{k^2 + \omega^2}} \cos(\omega t - \phi)$$

# Why Do Exponential Functions Solve Linear Differential Equations?

1. **Clue from the First-Order Linear ODE**
    
    Let's consider the simplest first-order linear differential equation:

    $$y' - ry = 0$$

    The equation $y' = ry$ implies that the rate of change of $y$ is proportional to $y$ itself. This fundamental relationship can be solved using the separation of variables:

    $$\frac{dy}{y} = r dt \implies \ln|y| = rt + C \implies \mathbf{y = Ce^{rt}}$$

    From this, we gain a crucial insight: the exponential function is the fundamental form that remains proportional to itself after differentiation.

    - Note: This proof demonstrates that the exponential function is the natural solution for homogeneous differential equations. This is because the homogeneous form inherently describes a system where the rate of change is governed solely by the state of the variable itself ($y' = ry$).
    
2. **Extension to Second-Order Linear ODEs**

    Now, consider the second-order case:
    $$y'' + ay' + by = 0$$

    By introducing the differential operator $D = \frac{d}{dt}$, we can rewrite the equation as:

    $$(D^2 + aD + b)y = 0$$

    Factoring the operator polynomial gives us two roots, $r_1$ and $r_2$:

    $$(D - r_1)(D - r_2)y = 0$$

    This higher-order equation can be decomposed into a sequence of two first-order problems:

    1. **Substitution**: Let $(D - r_2)y = u$ to reduce the second-order differential equation to a first-order equation. Then the equation becomes $(D - r_1)u = 0$.
        - Insight: This equation takes the form $Du = r_1 u$, meaning that the function $u$ is proportional to its own derivative.
        - As we proved in the first-order case, the exponential function is the unique solution to this relationship ($u = C_1 e^{r_1 t}$).
    2. **First Step**: Based on the first-order proof above, the solution for $u$ is:
        $$u = C_1 e^{r_1 t}$$
    3. **Second Step**: Now we solve the non-homogeneous first-order equation: 
        $$ u = (D - r_2)y = C_1 e^{r_1 t} $$
        
        which gives:

        $$ y’ - r_2 y = C_1 e^{r_1 t} $$

        Applying the integrating factor $e^{-r_2 t}$ and differentiation using the product rule:

        $$\frac{d}{dt}(e^{-r_2 t} y) = C_1 e^{(r_1 - r_2)t}$$

    Integrating both sides:

    $$e^{-r_2 t} y = \frac{C_1}{r_1 - r_2} e^{(r_1 - r_2)t} + C_2$$

    Rearranging for $y$:
    $$\mathbf{y = A e^{r_1 t} + B e^{r_2 t}}$$
    (where $A = \frac{C_1}{r_1 - r_2}$)

3. **Conclusion: The Core Logic**

    Through the process of operator factorization, we can conclude that:
    - A higher-order differential operator can be decomposed into a product of several first-order operators.

    Now, we know the truth from the operator factorization process.
    - The high order differential operator is splitted by a product of several first order differential operator
    - Since each first-order operator inherently yields an exponential solution ($e^{rt}$), the overall solution must be built from these terms.
    - By the **Superposition Principle**, the linear combination of these exponential functions forms the general solution of the system.

# Solution family and solving strategy

In most cases, solving a differential equation follows a systematic strategy: **defining a potential solution family** and then **reducing the solution space** through physical or mathematical constraints.

1. **Defining the Family (Prior Knowledge)**: 

    For a homogeneous second-order differential equation, we have already established that the exponential function ($e^{rt}$) is the fundamental solution family. This serves as our "prior" or starting hypothesis.

2. **Applying Constraints (Dimensionality Reduction)**: 

    By substituting this assumed form ($y = e^{rt}$) into the original differential equation, we impose a strict constraint on the possible values of $r$.

3. **Solving the Residual Problem**: 

    This substitution transforms a complex calculus problem (differential equation) into a simpler algebraic problem (characteristic equation). By solving for $r$, we identify the specific members of the exponential family that satisfy our system's dynamics.

**Illustrative Example: Polynomial Curve Fitting**

This process is analogous to the following example. Suppose we are given three data points: $(0,1)$, $(1,3)$, and $(2,7)$, and we need to find a function that passes through them. If we have prior knowledge that the solution belongs to the second-order polynomial family—expressed as $p(x) = ax^2 + bx + c$—the task of solving for the function is reduced to finding the specific coefficients $(a, b, c)$ that satisfy the given points.

By substituting the coordinates into our "family" equation, we transform the problem into a system of linear equations:

- $p(0) = c = 1$
- $p(1) = a + b + c = 3$
- $p(2) = 4a + 2b + c = 7$

This illustrates how defining a solution family first allows us to focus on solving for the remaining parameters that fit the specific constraints. In the same way, assuming $e^{rt}$ for a differential equation shifts our focus from searching for an unknown function to calculating the characteristic roots ($r$).

# Reduction of order (The Idea of Jean le Rond d'Alembert)

The Method of Reduction of Order, pioneered by Jean le Rond d'Alembert, demonstrates a profound shift from searching for a second solution from scratch to leveraging the known structure of the first solution. By substituting the constant of integration with a functional parameter $u(x)$, d'Alembert succeeded in reducing the complexity of second-order differential equations.

1. **The Hypothesis**

    Consider the general second-order homogeneous equation in standard form:$$y'' + p(x)y' + q(x)y = 0 \tag{1}$$
    
    Assume that $y_1(x)$ is a known non-zero solution. Since any second solution $y_2(x)$ must be linearly independent of $y_1(x)$, we propose the following hypothesis:$$y_2(x) = u(x) y_1(x) \tag{2}$$where $u(x)$ is a non-constant function.

2. **Substitution and Grouping**

    To solve for $u(x)$, we differentiate Equation (2) using the product rule:
    - $y_2' = u'y_1 + u y_1'$
    - $y_2'' = u''y_1 + 2u'y_1' + u y_1''$

    Substituting these into Equation (1) gives:$$(u''y_1 + 2u'y_1' + u y_1'') + p(x)(u'y_1 + u y_1') + q(x)(u y_1) = 0$$

    Now, we group the terms by the derivatives of $u(x)$:$$u''(y_1) + u'(2y_1' + p(x)y_1) + u \underbrace{(y_1'' + p(x)y_1' + q(x)y_1)}_{= 0} = 0$$

    Since $y_1$ is a solution to the original equation, the term multiplied by $u$ vanishes, leaving us with a first-order linear equation with respect to $u'$:$$u''y_1 + u'(2y_1' + p(x)y_1) = 0$$

3. **Solving for $u'(x)$ using Separation of Variables**.

    Let $v = u'$. Then the equation becomes $v'y_1 + v(2y_1' + p(x)y_1) = 0$. We can now separate the variables:$$\frac{1}{v} dv = -\left( \frac{2y_1' + p(x)y_1}{y_1} \right) dx$$

    Integrating both sides as shown in the derivation steps:$$\int \frac{1}{v} dv = \int \left( -\frac{2y_1'}{y_1} - p(x) \right) dx$$

    $$\ln |v| = -2 \ln |y_1| - \int p(x)dx + C$$
    $$\ln(|v| y_1^2) = -\int p(x)dx + C$$

    By taking the exponential of both sides and solving for $v$, we get:$$v = u' = c \frac{e^{-\int p(x)dx}}{y_1^2}$$

4. **The General Formula for $u(x)$**

    Finally, integrating one more time yields the general expression for $u(x)$:$$\mathbf{u(x) = c \int \frac{e^{-\int p(x)dx}}{[y_1(x)]^2} dx}$$

5. **The Final Expression for $y_2(x)$**

    Once we have derived the general formula for $u(x)$, we can substitute it back into our initial hypothesis, $y_2(x) = u(x) y_1(x)$. From the previous step, we found:$$u(x) = \int \frac{e^{-\int p(x)dx}}{[y_1(x)]^2} dx$$

    (Note: For simplicity, we set the integration constant $c=1$ and the additive constant to $0$, as we only need one linearly independent solution). By multiplying this by $y_1(x)$, we obtain the general formula for the second linearly independent solution:$$\mathbf{y_2(x) = y_1(x) \int \frac{e^{-\int p(x)dx}}{[y_1(x)]^2} dx}$$

6. **Linearity and the General Solution**

    According to the Principle of Superposition, since $y_1(x)$ and $y_2(x)$ are linearly independent, the complete general solution of the second-order homogeneous differential equation is a linear combination of both:$$y(x) = C_1 y_1(x) + C_2 y_2(x)$$

    $$y(x) = C_1 y_1(x) + C_2 y_1(x) \int \frac{e^{-\int p(x)dx}}{[y_1(x)]^2} dx$$

# Linear second-order ODE solution

Let's solve the equation: $y'' + Ay' + By = 0$.

We already have a prior that the solution to a second-order homogeneous differential equation belongs to the exponential family. Therefore, let’s substitute the exponential function $y = e^{rt}$ into the equation. After substitution, we obtain:

$$r^2 e^{rt} + A r e^{rt} + B e^{rt} = 0$$

To simplify, we can divide both sides by $e^{rt}$ (since $e^{rt} \neq 0$), resulting in:

$$r^2 + Ar + B = 0$$

This is known as the characteristic equation of the system.

A second-order polynomial equation can yield three types of solutions, and this property directly determines the behavior of the differential equation:

1. **Distinct Real Roots**: The roots are real and different ($r_1 \neq r_2$).
2. **Complex Conjugate Roots**: The roots are different but involve imaginary numbers.
3. **Repeated Roots**: The two roots are identical ($r_1 = r_2$).

**Case 1: Distinct Real Roots**

In the first case, the general solution of the differential equation is:

$$y = C_1 e^{r_1 t} + C_2 e^{r_2 t}$$

Suppose we apply the initial conditions $y(0) = 1$ and $y'(0) = 0$. Using our general solution and its derivative $y'(t) = -3C_1 e^{-3t} - C_2 e^{-t}$, we can establish the following system of linear equations:

1. From $y(0) = 1$:
$$C_1 + C_2 = 1$$

2. From $y'(0) = 0$:
$$-3C_1 - C_2 = 0$$

Solving this system (e.g., by adding the two equations), we find $-2C_1 = 1$, which gives $C_1 = -1/2$ and $C_2 = 3/2$. Therefore, the particular solution that satisfies these specific initial conditions is:

$$\mathbf{y(t) = -\frac{1}{2}e^{-3t} + \frac{3}{2}e^{-t}}$$

**Case 2: Complex Conjugate Roots ($r = \alpha \pm \beta i$)**

In this case, the characteristic equation yields complex roots, leading to the solution form $y = e^{(\alpha \pm \beta i)t}$. Based on the principle of superposition, the general solution can be written as:

$$y = C_1 e^{(\alpha + \beta i)t} + C_2 e^{(\alpha - \beta i)t}$$

Using the exponential law, we can factor out $e^{\alpha t}$:$$y = e^{\alpha t} \left( C_1 e^{i\beta t} + C_2 e^{-i\beta t} \right)$$

Next, we apply Euler's formula ($e^{i\theta} = \cos \theta + i \sin \theta$) to convert the complex exponentials into trigonometric functions:
- $e^{i\beta t} = \cos(\beta t) + i \sin(\beta t)$
- $e^{-i\beta t} = \cos(\beta t) - i \sin(\beta t)$

Substituting these back into the expression, the terms inside the parentheses are rearranged as follows:
$$(C_1 + C_2) \cos(\beta t) + i(C_1 - C_2) \sin(\beta t)$$

Since $C_1$ and $C_2$ are arbitrary constants, we can define new real-valued constants: $A = C_1 + C_2$ and $B = i(C_1 - C_2)$. This results in the final real-valued general solution:

$$\mathbf{y(t) = e^{\alpha t} (A \cos \beta t + B \sin \beta t)}$$

**Note**: It may seem counterintuitive that $B$ is a real constant despite involving the imaginary unit $i$. This is because $C_1$ and $C_2$ are typically complex conjugates of each other (e.g., $C_1 = a + bi$ and $C_2 = a - bi$). In this case, the term $i(C_1 - C_2)$ simplifies to a purely real number, as the imaginary parts cancel out or multiply with $i$ to become real. 
- $A = C_1 + C_2 = a + bi + a - bi = 2a$
- $B = i(C_1 - C_2) = i(a + bi - (a - bi)) = -2b$

**Example: $y'' + 4y' + 5y = 0$**

The characteristic equation is $r^2 + 4r + 5 = 0$, giving roots $r = -2 \pm i$. Here, the real part $\alpha = -2$ and the imaginary part $\beta = 1$. The general solution is:
$$y = e^{-2t} (A \cos t + B \sin t)$$

With initial conditions $y(0) = 1$ and $y'(0) = 0$, we first find the derivative:

$$y' = \underbrace{-2e^{-2t}(A \cos t + B \sin t)}_{f'g} + \underbrace{e^{-2t}(-A \sin t + B \cos t)}_{fg'}$$

Applying the conditions at $t = 0$:
1. $y(0) = e^{0}(A \cos 0 + B \sin 0) = \mathbf{A = 1}$
2. $y'(0) = -2e^{0}(A \cos 0 + B \sin 0) + e^{0}(-A \sin 0 + B \cos 0) = \mathbf{-2A + B = 0}$

Solving these gives $A = 1$ and $B = 2$. Thus, the particular solution is:

$$\mathbf{y(t) = e^{-2t}(\cos t + 2 \sin t)}$$

**Case 3: Repeated Roots ($r_1 = r_2 = r$)**

When the characteristic equation $r^2 + Ar + B = 0$ yields a repeated real root $r$, we only obtain one solution from the exponential family: $y_{1}(x) = e^{rx}$. To find the second linearly independent solution $y_{2}(x)$, we apply the reduction of order.

$$\mathbf{y_2(x) = y_1(x) \int \frac{e^{-\int p(x)dx}}{[y_1(x)]^2} dx}$$

In the standard second-order homogenous equation $ y'' + A' + By = 0$:
- The coefficient function is constant: $p(x) = A$.
- The first solution is $y_{1}(x) = e^{rx}$, where the repeated root is $ r = \frac{-A}{2} $.
Now, let's substitute these into the reduction of order formula:

## Q. Why is $y = c_1y_1 + c_2y_2$ a solution?

This can be explained by the Superposition Principle, which states that a linear combination of solutions to a linear homogeneous ODE is also a solution. Consider the following second-order linear homogeneous equation:$$y'' + py' + qy = 0$$

This equation can be rewritten using the differential operator ($D$):

$$\to D^2y + pDy + qy = 0$$
$$\to (D^2 + pD + q)y = 0$$

We can represent the term $(D^2 + pD + q)$ as $L$, which denotes a linear operator. To justify the superposition principle, we must prove that $L$ is indeed linear. A linear operator must satisfy:$$L(c_1u_1 + c_2u_2) = c_1L(u_1) + c_2L(u_2)$$

**Proof of Linearity for $L$**:$$\begin{aligned}L(u_1 + u_2) & = (D^2 + pD + q)(u_1 + u_2) \\ & = [D^2(u_1) + pD(u_1) + qu_1] + [D^2(u_2) + pD(u_2) + qu_2] \\ & = L(u_1) + L(u_2)\end{aligned}$$

Since $L$ is a linear operator, we can rewrite the operation on the general solution as:$$L(c_1y_1 + c_2y_2) = c_1L(y_1) + c_2L(y_2)$$

Given that $y_1$ and $y_2$ are individual solutions, $L(y_1) = 0$ and $L(y_2) = 0$. Therefore:$$L(c_1y_1 + c_2y_2) = c_1(0) + c_2(0) = 0$$

This confirms that the linear combination $c_1y_1 + c_2y_2$ is also a valid solution to the original equation.

## Q. Why is this the General Solution?

While the Superposition Principle confirms that $y = c_{1}y_{1} + c_{2}y_{2}$ is a solution, we must also prove that it constitutes all possible solutions (the General Solution). This is justified by the following mathematical principles:

**1. Existence and Uniqueness Theorem:** According to the Picard-Lindelöf Theorem, for a second-order linear ODE with continuous coefficients, there exists one and only one unique solution for a given set of initial conditions, $y(x_0) = y_0$ and $y'(x_0) = v_0$. Our solution $y = c_{1}y_{1} + c_{2}y_{2}$ contains two arbitrary constants, providing the necessary degrees of freedom to satisfy any possible initial conditions.

**2. Linear Independence and the Wronskian:** As noted in your records ($y_1 \neq Cy_2$), the solutions $y_1$ and $y_2$ must be linearly independent. This independence is verified if the Wronskian ($W$) is non-zero:$$W(y_1, y_2) = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix} \neq 0$$

When $W \neq 0$, the system of equations for $c_1$ and $c_2$ is guaranteed to have a unique solution for any initial values. This ensures that no solution exists outside the span of $\{y_1, y_2\}$.

**3. Dimension of the Solution Space:** From a linear algebra perspective, the set of all solutions to a second-order linear homogeneous ODE forms a two-dimensional vector space. Any set of two linearly independent solutions, $\{y_1, y_2\}$, acts as a basis for this space.Just as any vector in a 2D plane can be represented by two basis vectors, any solution in this 2D solution space can be expressed as a linear combination: $y = c_{1}y_{1} + c_{2}y_{2}$.

**Conclusion**: Because our solution set $\{y_1, y_2\}$ is linearly independent and provides enough constants to satisfy the Uniqueness Theorem, it is mathematically guaranteed to cover the entire "solution space." Therefore, $y = c_{1}y_{1} + c_{2}y_{2}$ is indeed the General Solution.

# Theorem: Real and Imaginary Parts of Complex Solutions

If a complex-valued function $y(t) = u(t) + iv(t)$ is a solution to the linear homogeneous differential equation with real coefficients:$$y'' + Ay' + By = 0$$where $A$ and $B$ are real constants, then the real part $u(t)$ and the imaginary part $v(t)$ are themselves individual real-valued solutions to the same equation.

**Proof**

1. Substitution into the Differential Equation
    
    Assume $y = u + iv$ is a solution. By substituting this into the original equation, we get:$$(u + iv)'' + A(u + iv)' + B(u + iv) = 0$$

2. Expansion using Linearity of DifferentiationSince differentiation is a linear operator, we can distribute the derivatives and the real coefficients $A$ and $B$:$$(u'' + i v'') + A(u' + i v') + B(u + iv) = 0$$

3. Grouping into Real and Imaginary Parts. Now, we rearrange the terms to group the real components and the imaginary components separately:$$\underbrace{(u'' + Au' + Bu)}_{\text{Real Part}} + i \underbrace{(v'' + Av' + Bv)}_{\text{Imaginary Part}} = 0 + 0i$$

4. Conclusion by Equality of Complex Numbers 

    For a complex number to be zero, both its real part and its imaginary part must independently equal zero. Therefore: $$u'' + Au' + Bu = 0$$ $$v'' + Av' + Bv = 0$$ This proves that both $u$ and $v$ satisfy the original differential equation. Thus, they are individual real-valued solutions. $\square$

**Note**: The transition from a single complex solution $ y = u +iv $ to two separate real solutions $u$ and $v$ is justified by the fundamental property of complex equality.

When we subsitute $u$ into the differential equation, we obtain the expression $u'' + Au' + Bu$. Similarly, substituting $v$ yields $v'' + Av' + Bv$. Crucially, our initial expansion of the complex solution showed that these two specific expressions are exactly the real and imaginary components that sum to zero: $$(u'' + Au' + Bu) + i(v'' + Av' + Bv) = 0 + 0i$$

Since a complex number is zero if and only if its real and imaginary parts are independently zero, it is mathematically guaranteed that $u'' + Au' + Bu = 0$ and $v'' + Av' +Bv = 0$. Therefor, $u$ and $v$ satisfy the original differential equation individually, confirming them as valid, independent real-valued solutions.

**Connection to Case 2 (Complex Roots)**

By applying Euler’s Formula to the complex exponential solution $y = e^{(\alpha + i\beta)t}$, we get:$$y(t) = e^{\alpha t}(\cos \beta t + i \sin \beta t) = \underbrace{e^{\alpha t} \cos \beta t}_{u(t)} + i \underbrace{e^{\alpha t} \sin \beta t}_{v(t)}$$

Based on the Theorem proven above:
1. Since $y(t) = u(t) + iv(t)$ is a solution, $u(t) = e^{\alpha t} \cos \beta t$ must be a real-valued solution.
2. Similarly, $v(t) = e^{\alpha t} \sin \beta t$ must also be a real-valued solution.

Therefore, the general real-valued solution is a linear combination of these two independent solutions:$$\mathbf{y(t) = e^{\alpha t} (C_1 \cos \beta t + C_2 \sin \beta t)}$$

**Note on Symbol Consistency**: There may be potential confusion regarding the shift in symbols from $u$ and $v$ (used in the Theorem) to $\alpha$ and $\beta$ (used in Case 2). To bridge these sections, one should recall that the general framework $y = u + iv$ represents any complex solution. In this context, by substituting the specific form $y = e^{(\alpha + i\beta)t}$ into the differential equation, we decompose it into its real component ($u = e^{\alpha t} \cos \beta t$) and imaginary component ($v = e^{\alpha t} \sin \beta t$). Since these two components are linearly independent and the original differential equation is homogeneous with real coefficients, both must independently satisfy the equation to equal zero, as established by the Theorem.

**Note on the Choice of Sign ($\pm \beta$)**: One might wonder if choosing $r = \alpha - \beta i$ instead of $r = \alpha + \beta i$ would alter the general solution. Mathematically, the general solution remains invariant regardless of the sign. As demonstrated, one fundamental solution is $e^{\alpha t}\cos{\beta t}$; since the cosine function is an even function ($\cos(-\beta t) = \cos(\beta t)$), changing the sign of $\beta$ has no effect. Similarly, while the sine function is an odd function ($\sin(-\beta t) = -\sin(\beta t)$), any change in sign is absorbed by the arbitrary coefficient ($C_2$). Therefore, the fundamental set of solutions remains equivalent, and the general real-valued solution remains unchanged.

**Application: Solving for Complex Conjugate Roots**

Solve the differential equation: $y'' + 4y' + 5y = 0$.

1. Characteristic Equation: The characteristic equation is $r^2 + 4r + 5 = 0$. Using the quadratic formula, we obtain the complex conjugate roots:$$r = \frac{-4 \pm \sqrt{16 - 20}}{2} = -2 \pm i$$

2. Complex-Valued Solution: Initially, we obtain a complex-valued solution: $y(t) = e^{(-2+i)t}$. By applying Euler’s Formula ($e^{it} = \cos t + i \sin t$), we can expand this as:$$y(t) = e^{-2t} (\cos t + i \sin t) = \underbrace{e^{-2t} \cos t}_{u(t)} + i \underbrace{e^{-2t} \sin t}_{v(t)}$$

3. Extracting Real-Valued Solutions: As previously proved, the real part $u(t)$ and the imaginary part $v(t)$ satisfy the original differential equation independently. Thus, we obtain two linearly independent real-valued solutions
    - $y_1(t) = e^{-2t} \cos t$
    - $y_2(t) = e^{-2t} \sin t$

4. General Solution: By the Principle of Superposition, the general solution is:$$\mathbf{y(t) = e^{-2t} (C_1 \cos t + C_2 \sin t)}$$


# Damping (감쇠, 減衰)

Damping is a phenomena in which the amplitude of oscillation continuously decreases over time. This concept is fundamental to oscillatory system; without damping, a system would vibrate indefinitely without ever setting at its equilibrium point. When damping is present, the system's mechanical energy is dissipated-transformed into other forms, such as heat-and released into the environment. As a result, the system gradually converges toward the equilibrium point. 

A system requires energy to sustain motion, but the damping force opposes this movement by exerting a resistive force in the direction opposite to the velocity at every point in time. Due to the resistance, mechanical energy is consumed, and the system continuously loses the "motivation" (kinetic energy) to maintain its motion, eventually leading to a state of rest.

Ultimately, oscillation occurs because the resistance is too low to overcome the inertia, allowing the system to overshoot its equilibrium point repeatedly until all energy is dissipated.

- A type of damping
    - **Underdamped**

        If you pull a spring and release it, it oscillates up and down several times before finally coming to a stop. This occurs because the damping force is too weak to prevent the system from overshooting its equilibrium position.
    - **Overdamped**

        The spring returns to its original position very slowly without oscillating, similar to a spring moving through thick honey. Although there is no overshoot, the excessive damping force causes a significant delay in returning to the equilibrium state.
    - **Critically Damped**

        The system returns to its equilibrium position in the shortest possible time without any oscillation (overshoot). It acts as the "Golden Balance" between being underdamped and overdamped. Like a perfectly tuned door closer, it provides the fastest recovery to the rest state while ensuring the motion remains smooth and steady.

- Mathematical Insights

    This unique behavior is driven by general solution $ y(t) = (C_{1} + C_{2}t)e^{-at}$, where the linear term t allows the system to satisfy initial velocity conditions while maintaining the fatest possible exponential decay toward zero. In biomechanics, this state is often sought by the nervous system to achieve both speed and precision in limb movements.

- Why is the type of damping so important?  

    The significance of damping becomes even clearer when viewed through the lens of robotics and motor control. Consider a robot arm ordered to move to a specific target position.

    - Underdamped state: The arm may reach the target position quickly, but it will oscillate (overshoot) repeatedly around the target before coming to a rest. While its initial speed is high, the overall time to achieve a stable "rest state" is long due to these vibrations.
    - Overdamped state: The arm approaches the target very slowly. Because the damping force is excessively high—essentially "braking" too much—the arm avoids oscillation and appears safe, but the operational efficiency is poor due to the sluggish movement.
    - Critically damped state: This represents the "mathematical golden balance." The robot rapidly reduces its velocity just as it reaches the target, stopping perfectly without any oscillation. This state achieves the minimum settling time, making it the most efficient way to reach a stable equilibrium.
    
- Biological Significance in Motor Control

    The nervous system actively tunes muscle stiffness and viscosity to achieve a state near critical damping. This strategic tuning is essential for precise movement execution, as it minimizes 'setting time'- the time required to reach a stable target- while preventing 'overshoot' (oscillatory errors). By maintaining a critically damped state, the brain ensures that reaching and manipulation tasks, such as handwriting, are performed with optimal speed and maximal stability against internal neural noise.

- Mathmatical connection of damping states

    This bahvior of a second-order system $ y'' + Ay' + By = 0 $ is determined by the roots of its characteristic equation: $r^2 + Ar+ B = 0$.


    1. Underdamped (D < 0)
        - Mathematical condition: This discriminant $A^2 - 4B < 0$, resulting in complex conjugate roots ($r = \alpha \pm \beta i$).
        - General Solution: $y(t) = C_1 e^{(\alpha + i\beta)t} + C_2 e^{(\alpha - i\beta)t}$ (where $C_1, C_2$ are complex constants)
        - Connection: Through Euler’s Formula ($e^{i\beta t} = \cos \beta t + i \sin \beta t$), the imaginary components introduce sine and cosine functions. For the physical solution $y(t)$ to be real-valued, $C_1$ and $C_2$ must be complex conjugates, which combine into new real coefficients ($K_1, K_2$) to form $y(t) = e^{\alpha t} (K_1 \cos \beta t + K_2 \sin \beta t)$.
        - The "Envelope": When the real part is negative ($\alpha < 0$), the term $e^{\alpha t}$ acts as a decaying exponential "envelope" that causes the amplitude of the oscillations to decrease over time until they die out.
    2. Overdamped (D > 0)
        - Mathematical condition: This discriminant $A^2 - 4B > 0$, resulting in two distinct real roots $(r_1, r_2)$.
        - General solution: $y(t) = C_{1}e^{r_{1}t} + C_{2}e^{r_{2}t}$ (where $r_1$, $r_2$ < 0)
        - Connection: Since both roots are real and negative, the solution is a pure sum of decaying exponentials. There are no trigonometric terms, meaning no oscillation occurs. The system is "too heavy" or "too viscous," causing it to crawl back to equilibrium slowly.
    3. Critically Damped ($D = 0$)
        - Mathematical condition: This discriminant $A^2 - 4B = 0$, resulting in a repeated real root ($r = -a$).
        - General Solution: $y(t) = (C_1 + C_2 t) e^{-at}$
        - Connection: As derived through the Method of Reduction of Order, this case requires an additional linear term $t$ to maintain linear independence. Mathematically, this is the "fastest" possible decay. It represents the boundary where the system has just enough damping to prevent the onset of oscillation, allowing for the minimum settling time.

# Wronskian

The Wronskian is a mathematical tool used to test whether two functions are linearly independent. Consider two vectors, such as $[1,0]$ and $[1,1]$. By definition, two vectors are linearly independent if one cannot be represented as a constant multiple of the other. In this case, $[1,0]$ and $[1,1]$ are independent because $c \cdot [1,0]$ can never result in $[1,1]$ for any constant $c$.

The **determinant** is an excellent tool for testing this independence. If the determinant of a matrix formed by these vectors is zero, it indicates that the vectors point in the same (or exactly opposite) direction, meaning they are linearly dependent. Conversely, if the determinant is non-zero, the vectors head in different directions, proving they are linearly independent.

Similarly, testing two functions for independence involves a process of vectorization. Consider two solutions, $y_1$ and $y_2$, of a second-order differential equation. At any given point $x$, each solution can be vectorized by combining the function and its derivative: $\begin{bmatrix} y_i \\ y_i' \end{bmatrix}$. We can then construct the following matrix:$$\begin{pmatrix} y_1 & y_2 \\ y_1' & y_2' \end{pmatrix}$$

To determine if these two solutions are linearly independent, we calculate the determinant of this matrix, known as the Wronskian ($W$):$$W(x) = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix}$$

**Example** Here is an example. Prove the two solutions of second-order differential equation is linear independent: $$ y'' + 3y' + 2y = 0 $$

The characteristic equation is $r^2 + 3r + 2 = 0$, which can be factored as $(r+2)(r+1)=0$, yielding the roots $r_1 = -2$ and $r_2 = -1$. Thus, the two fundamental solutions are:$$y_1 = e^{-2t}, \quad y_2 = e^{-t}$$

To check their linear independence, we calculate the Wronskian ($W$):$$W(y_1, y_2) = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix} = \begin{vmatrix} e^{-2t} & e^{-t} \\ -2e^{-2t} & -e^{-t} \end{vmatrix}$$

Calculating the determinant:$$W = (e^{-2t})(-e^{-t}) - (e^{-t})(-2e^{-2t})$$ $$W = -e^{-3t} + 2e^{-3t} = e^{-3t}$$Since $e^{-3t} \neq 0$ for all $t$, the Wronskian is non-zero. Therefore, the two solutions are linearly independent.

# Theorem: The general solution to $Ly = f(x)$ is $y = y_p + y_c$

To verify that $y = y_p + y_c$ is the general solution for $Ly = f(x)$, we apply the Linearity Principle of the operator $L$.

- $y_c$ (Complementary Solution): The solution to the homogeneous equation $Ly = 0$. This represents the system's autonomous behavior.
- $y_p$ (Particular Solution): The specific solution that satisfies the non-homogeneous equation $Ly = f(x)$.

**Let's prove all the $ y_p + c_1y_1 + c_2y_2 $ are solutions**. By substituting the combined form $y_p + y_c$ into the linear operator $L$, we observe: $$L(y_p + y_c) = L(y_p) + L(y_c)$$ 

Since $y_c$ is the solution to the system's "natural state" (where the net internal reaction is zero), $L(y_c)$ becomes 0. Consequently, the entire equation reduces to:$$L(y_p) = f(x)$$

This confirms the differential equation with external input can be decomposed into particular solution and complementary solution. Mathematically, this guarantees that we can separate the intrinsic characteristics of the system from the effects of the external stimulus.

Let's prove there are **no other solution without $y = y_p + y_c$**. Let's assume there is another solution, satisfying $L(u) = f(x)$ when we know the particular solution satisfying $L(y_p) = f(x)$. Now, let's see the difference of two solutions having a character by inputing to linear operator $L$: $$ L(u - y_p) = L(u) - L(y_p) = f(x) - f(x) = 0 $$

To ensure that $y = y_p + y_c$ is **the only possible form of the general solution**, consider an arbitrary solution $u$ such that $L(u) = f(x)$. Since we already have a particular solution $y_p$ where $L(y_p) = f(x)$, we can analyze the difference between the two:$$L(u - y_p) = L(u) - L(y_p) = f(x) - f(x) = 0$$

The result shows that the difference $(u - y_p)$ satisfies the homogeneous equation $Ly = 0$. Therefore:$$u - y_p = y_c \quad \Rightarrow \quad u = y_p + y_c$$

This proves that every solution to a linear differential equation is inevitably composed of a particular solution and a complementary solution. There is no "hidden" third component in a linear system.

**Note on meaning of complementary and particular solution**: 

1. Complementary Solution (Inertia/Momentum): Even if the driver takes their foot off the pedals, the car doesn't stop instantly. It has momentum—a tendency to keep its current state of motion based on its own physical properties (mass, friction). This "internal" behavior, which depends on the car's initial state and physical makeup, is represented by the complementary solution ($y_c$). It is the car's "natural" response.

2. Particular Solution (External Force/Input): On the other hand, the driver actively manipulates the car by pressing the gas or brake pedals. This applies an external force to change the car's position or speed according to the driver's intent. This "forced" response to external input is represented by the particular solution ($y_p$).

Therefore, the final position of the car ($y$) is the sum of these two components: $$y = \underbrace{y_c}_{\text{How the car "wants" to move by itself}} + \underbrace{y_p}_{\text{How the driver "forces" the car to move}}$$

In a linear system, the state is determined by the negotiation between the system's inherent inertia and the external forces applied to it.

# Substitution rule

The substitution rule in a differential equation is an efficient method to find a solution without performing tedious deriviation process. Mainly, this is used to find particular solution($y_p$), and it is especially powerful when dealing with exponential inputs.

The exponential function $e^{\alpha x}$ has a unique property: it maintains its functional shape during differentiation and simply produces the constants $\alpha$ as a coefficient. When this property is expanded to a polynomial derivation operator $p(D)$, the rule is expressed as: $$p(D)e^{\alpha x} = p(\alpha)e^{\alpha x}$$

In other words, in the presence of an exponential function, the complex polynomial derivation operator $p(D)$ can be substituted with a simple number $p(\alpha)$.

**Note on naming - "Substitution" rule**: Why do we call this rule as "Substitution"? The term "Substitution" originates from the idea of replacing a complex component (which is difficult to integrate or manipulate) with a simpler, more manageable representative. In this context, if we view $p(D)$ as a "complex dummy" (an expression depending on a complex variable $D$) and $p(\alpha)$ as a "simple dummy" (a simplified parameter $\alpha$), the rule allows us to transition between these two "worlds.

**Proof**

$$\begin{aligned}
p(D)e^{\alpha x} = (D^2 + AD + B)e^{\alpha x} & = D^2e^{\alpha x} + ADe^{\alpha x} + Be^{\alpha x} \\
& = \alpha e^{\alpha x} + A\alpha e^{\alpha x} + Be^{\alpha x} \\
& = p(\alpha) e^{\alpha x}
\end{aligned}$$


**Note on Advantage of substitution rule**: The practical importance of substitution rule to find a particualr solution is best demonstrated by by comparing solution process with and without its application.

Suppose we need to find a particular solution for the following equation: $$ y'' + 3y' + 2y = e^{5x} $$

1. **Without the Substitution Rule (The Conventional Method)**: To find the solution, we must execute the following steps:
    1. Assume the solution of shape $y_p = Ae^{5x}$ based on the input is $e^{5x}$
    2. Perform differentiation: $y'_{p} = 5Ae^{5x}$, $y''_p = 25Ae^{5x}$
    3. Substitute these into the original equation: $(25Ae^{5x}) + 3(5Ae^{5x}) + 2(Ae^{5x}) = e^{5x}$
    4. Factor out $Ae^{5x}$: $(25 + 15 + 2)Ae^{5x} = e^{5x}$, which leads to $42A = 1$
    5. Solve for A: $A = 1/42$

2. **With the Substitution Rule**: Consider the original equation represented in the operator form:$$p(D)y_p = e^{5x}$$ where $p(D) = D^2 + 3D + 2$. By utilizing the rule $p(D)e^{\alpha x} = p(\alpha)e^{\alpha x}$ (where $\alpha = 5$), the process is significantly streamlined:
    1. To isolate $y_p$, express it using the inverse operator:$$y_p = \frac{1}{p(D)} e^{5x}$$
    2. Apply the Substitution Rule: Since the input is an exponential function, we can directly substitute the operator $D$ with the constant $5$:$$y_p = \frac{1}{p(5)} e^{5x} = \frac{1}{5^2 + 3(5) + 2} e^{5x} = \frac{1}{42} e^{5x}$$

## Exponential Input Theorem for $ y'' + Ay' + By = e^{\alpha x} $

This theorem formalizes the particular solution ($y_p$) respect to the linear derivative operator $p(D)$ when the input is an exponential function.

Theorem: Given the linear differential equation $p(D)y = e^{\alpha x}$, where $\alpha$ is a complex constant and $p(\alpha) \neq 0$, the particular solution is:$$y_p = \frac{e^{\alpha x}}{p(\alpha)}$$

**Proof** To verify that $y_p = \frac{e^{\alpha x}}{p(\alpha)}$ is the solution, we substitute it into the original equation:

$$\begin{aligned}
p(D)y_p & = e^{\alpha x} \\
p(D) \left[ \frac{e^{\alpha x}}{p(\alpha)} \right] & = e^{\alpha x} \\
\frac{1}{p(\alpha)} \underbrace{p(D) e^{\alpha x}}_{\text{Apply Substitution Rule}}  & = e^{\alpha x} \\
\frac{p(\alpha)e^{\alpha x}}{p(\alpha)} \quad (\because p(D) \rightarrow p(\alpha) \text{ for } e^{\alpha x}) & = e^{\alpha x} \\
e^{\alpha x} & = e^{\alpha x}
\end{aligned}$$

where $p(\alpha) \neq 0$

**Example** 

Find a solution: $$ y'' -y' + 2y = 10e^{-x}\sin{x} $$

The equation is equal to the imaginary part of $$ (D^2 -D + 2)\tilde{y} = 10e^{-1 + i}x $$

After applying exponential input theorem, we get:

$$ \begin{aligned}
\tilde{y_p} & = \frac{10e^{(-1+i)x}}{(-1+i)^2 - (-1 + i) + 2} \\
    & = \frac{10e^{(-1+i)x}}{3 - 3i} = \frac{10}{3}\frac{1+i}{2}e^{-x}(\cos x + i\sin x) \\
    & = Im(\tilde{y_p}) = \frac{5}{3}e^{-x}(\cos x + i\sin x) \\
    & = \frac{5}{3}e^{-x}\sqrt{2} \cos (x - \frac{\pi}{4})

\end{aligned}$$

## Exponential-shift rule

The **Exponential-shift rule** is a powerful generalization of the **Substitution rule**. While the Substitution rule describes how a polynomial operator $p(D)$ interacts with a pure exponential function ($e^{ax}$), the Exponential-shift rule extends this to the proudct an exponential function and any arbitrary function ($u(x)$).

The logic of extension:
- Substitution Rule: Transform the operator $p(D)$ into a constant $p(\alpha)$ when acting on $e^{ax}$.
- Exponential-shift Rule: Descrbies how the operator $p(D)$ shifts as it passes through the exponential function to act on the remaining function $u(x)$

$$ p(D)e^{ax}u(x) = e^{ax}p(D + a)u(x) $$

**Prove by Mathematical Induction**

The polynomial function $p(D)$ is combination of terms like $D$, $D^2$, $D^3$ etc. So, if we know the property of each term, we can generalize it into the arbitrary k-th terms.

1. if $ p(D) = D $,

    $$ De^{ax}u = D[e^{ax}]u + e^{ax}D[u] = ae^{ax}u + e^{ax}Du = e^{ax}(D + a)u $$

2. if $ p(D) = D^2 $,

    $$ \begin{aligned}
    D^2e^{ax}u = D[D[e^{ax}u]] 
    & = D(e^{ax}(D + a)u) \\
    & = e^{ax}(D + a)(D + a)u \\
    & = e^{ax}(D + a)^2u
    \end{aligned}$$

3. if $p(D) = c_nD^{n} + ... + c_1D + c_0$, 

    $$\sum c_k D^k (e^{ax}u) = \sum c_k e^{ax}(D+a)^k u = e^{ax} \left( \sum c_k (D+a)^k \right) u$$
    $$\therefore p(D)e^{ax}u = e^{ax}p(D+a)u$$


**Application: Solving for $y_p$ when $p(a) = 0$, Simple root case**

We aim to solve the differential equation $p(D)y = e^{ax}$. However, if $p(a) = 0$, the standard substitution rule cannot be applied. Therefore, we assume a trial solution of the form:$$y_p = e^{ax}v(x)$$

Our goal is to determine the unknown function $v(x)$. By applying the Exponential-shift rule, we get:$$p(D) [e^{ax}v(x)] = e^{ax}$$
$$e^{ax} p(D+a) v(x) = e^{ax}$$

Dividing both sides by $e^{ax}$ yields:$$p(D+a) v(x) = 1$$

If $a$ is a simple root of $p(D)$, it implies that $(D - a)$ is a factor of the polynomial. Thus, we can write:$$p(D) = (D - a)Q(D)$$

Replacing $D$ with $D + a$ in the above equation, we obtain:$$p(D+a) = (D+a-a)Q(D+a) = D \cdot Q(D+a)$$

Now, substituting this back into our equation for $v(x)$:$$D \cdot Q(D+a) v(x) = 1$$

Since $D$ denotes the differentiation operator, the term $Q(D+a)v(x)$ must be equal to $x$ (by integration):$$Q(D+a) v(x) = x$$

Assuming $v(x)$ is the particular part of the response, we can evaluate the operator at $D=0$ (or directly at $Q(a)$):$$v(x) = \frac{x}{Q(a)}$$

To express $Q(a)$ in terms of $p(D)$, we differentiate $p(D) = (D-a)Q(D)$ with respect to $D$ using the product rule:$$p'(D) = 1 \cdot Q(D) + (D-a)Q'(D)$$

By evaluating at $D = a$, we find that $p'(a) = Q(a)$. Substituting this into our expression for $v(x)$, we get:$$v(x) = \frac{x}{p'(a)}$$

Finally, substituting $v(x)$ back into our original assumption $y_p = e^{ax}v(x)$, we arrive at the particular solution:$$y_p = \frac{xe^{ax}}{p'(a)}$$

**Proof, Other version, Simple root case (p(a) = 0)**

1. The Problem:  
    We need to solve $p(D)y = e^{ax}$. However, the Exponential Input Theorem fails because $p(a) = 0$.

2. Testing the Candidate Solution:  
    Following the suggestion to try $y = e^{ax} \cdot x$, we substitute it into the operator:$$p(D)[e^{ax} \cdot x]$$

3. Applying the Exponential-shift Rule:  
    The rule states that when $e^{ax}$ passes to the left of the operator $p(D)$, $D$ is replaced by $(D+a)$:$$e^{ax} \cdot p(D+a)[x]$$

4. Evaluating $p(D+a)x$:  
    Let $p(D) = (D-b)(D-a)$. By replacing $D$ with $(D+a)$:$$p(D+a) = (D+a-b)(D+a-a) = (D+a-b)D$$

    Applying this to $x$:$$p(D+a)x = (D + a - b)Dx = D(Dx) + (a-b)Dx$$

    Since $Dx = 1$ and $D(1) = 0$:$$p(D+a)x = 0 + (a-b) \cdot 1 = \mathbf{a-b}$$

5. Verification and Conclusion:  
    As we derived earlier, $p'(a) = a-b$. Therefore:$$p(D)[e^{ax} \cdot x] = e^{ax} \cdot p'(a)$$

    To make the right-hand side exactly $e^{ax}$, we must divide our candidate by $p'(a)$.Thus, the particular solution is:$$\mathbf{y_p = \frac{e^{ax} \cdot x}{p'(a)}}$$

**Example**

Consider the equation: $$(D^2 + w_0^2)y = e^{iw_0t}$$

From view point of the exponential shift rule, $p(D) = (D^2 + w_0^2)$, and $iw_0$ is the simple root of p(D).

If we take the derivative of $p(D)$ with respect to $D$, we get:$$p'(D) = 2D$$

By substituting $D$ with $a$, we find:$$p'(a) = p'(iw_0) = 2iw_0$$

Finally, applying the exponential shift rule yields the particular solution:$$y_p = \frac{te^{iw_0t}}{2iw_0}$$

# Fourier series

## Reduces things to problems that you've already solved

Let $f(t) = s(t) + \frac{1}{2}$.We know the Fourier series of $g(u)$ with period $2\pi$ and amplitude $1$:$$g(u) = \frac{4}{\pi} \sum_{n=\text{odd}} \frac{\sin(nu)}{n}$$If $s(t)$ has a period of $2$ and amplitude $1$, it can be represented by $g(u)$ by scaling its period from $2\pi$ to $2$. To do this, we substitute $u = \pi t$:$$s(t) = g(\pi t) = \frac{4}{\pi} \sum_{n=\text{odd}} \frac{\sin(n\pi t)}{n}$$Therefore:$$f(t) = g(\pi t) + \frac{1}{2} = \frac{1}{2} + \frac{4}{\pi} \sum_{n=\text{odd}} \frac{\sin(n\pi t)}{n}$$

## Solve particular solution if f(t) is given as Fourier series

Let's recall the equation $x'' + \omega_0^2 x = f(t)$, which describes an **Undamped Simple Harmonic Oscillator**. For a harmonic forcing term, the particular solution is given by:$$x_p(t) = \frac{1}{\omega_0^2 - \omega^2} \begin{cases} \cos(\omega t) \\ \sin(\omega t) \end{cases}$$

If $f(t) = \frac{a_0}{2} + \sum_{n=1}^{\infty} \left( a_n \cos(\omega_n t) + b_n \sin(\omega_n t) \right)$ with $\omega_n = \frac{n\pi}{L}$, then by superposition:$$x_p(t) = \frac{a_0}{2\omega_0^2} + \sum_{n=1}^{\infty} \left( \frac{a_n \cos(\omega_n t)}{\omega_0^2 - \omega_n^2} + \frac{b_n \sin(\omega_n t)}{\omega_0^2 - \omega_n^2} \right)$$

(The constant term corresponds to the $\omega = 0$ frequency response).

For a 0-to-1 square wave with period $T=2$ (where $L=1$), the input is $f(t) = \frac{1}{2} + \frac{2}{\pi}\sum_{n=\text{odd}}\frac{\sin(n\pi t)}{n}$, and the system response is:

$$x_p(t) = \frac{1}{2\omega_0^2} + \frac{2}{\pi}\sum_{n=\text{odd}} \frac{\sin(n\pi t)}{n\left(\omega_0^2 - (n\pi)^2\right)}$$

Let's say natural frequency $\omega_0 = 10$. Then,

$$ x_p(t) \approx 0.005 + 0.6(\frac{\sin (n \pi t)}{91} + \frac{\sin (3 \pi t)}{12} + \frac{\sin (5 \pi t)}{-146}) $$


If $w_0 = 10$, near-resonance occurs for frequency $3\pi$ in Input

### Auditory system

Frequencies in f(t) are hidden but system picks out the frequencies closest to its natural freq. In our cochlea, complicated wave hits each one resonates to hidden frequency in the way which is closest to natural frequency.


