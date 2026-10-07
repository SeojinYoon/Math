
# Euler number

In 1683, Jacob Bernoulli discovered the constant $e$ while studying continuous compounding. He calculated how an initial deposit would grow when the principal is $1$ and the annual interest rate is $100\%$, using the formula:$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n$$

He proved that this limit does not diverge, but converges to a value strictly between $2$ and $3$. This marked the first time in mathematical history that a constant was defined through a limit process and its convergence was proven.

## Common Misconception: Infinite Time vs. Infinite Frequency

A common intuitive error is to assume that $e \approx 2.718$ represents the balance after an infinite amount of time has passed.
- Infinite Time ($t \to \infty$): If the money is left to compound forever, the total amount diverges to infinity ($\infty$).
- Infinite Compounding Frequency ($n \to \infty$): The limit defines what happens over a fixed unit of time (1 year) when the compounding intervals are subdivided indefinitely.

### The Tug-of-War: Why Doesn't It Explode to Infinity?

In the formula $\left(1 + \frac{1}{n}\right)^n$, as the number of compounding intervals $n$ grows toward infinity, two opposing mathematical forces pull against each other:
- The Base Pulls Toward $1$:

    Because the interest rate is divided into $n$ tiny pieces ($\frac{1}{n}$), each individual payout shrinks toward zero. The base $\left(1 + \frac{1}{n}\right)$ gets closer and closer to $1$. Multiplying numbers very close to $1$ tends to keep the result small.
- The Exponent Pulls Toward $\infty$:

    At the same time, the power $n$ goes to infinity because interest is credited infinitely many times. Raising any number greater than $1$ to an infinitely large power tends to explode toward infinity.

If the shrinking base had won, the result would collapse to $1$. If the growing exponent had won, the balance would blow up to infinity.

Instead, the two forces reach an exact mathematical equilibrium. Even when compounding happens every split second without pause, the balance over one full year cannot grow without bound—it converges precisely to $e \approx 2.71828\dots$, representing the natural ceiling of continuous growth.

## From the Constant $e$ to the Function $e^x$: Why $e$ is Just $x = 1$

In modern mathematics, the constant $e$ is understood as a single evaluation point of the continuous exponential function $f(x) = e^x$. Specifically, $e$ is simply $e^x$ when $x = 1$:$$e = e^1$$

In reality, interest rates are rarely $100\%$ ($r = 1$), and compounding rarely stops after exactly $1$ year ($t = 1$). When an annual interest rate $r$ is compounded $n$ times per year over $t$ years, the formula generalizes to:$$\lim_{n \to \infty} \left(1 + \frac{r}{n}\right)^{nt}$$

By substituting $m = \frac{n}{r}$ (so that $m \to \infty$ as $n \to \infty$), we can rewrite the expression:$$\lim_{m \to \infty} \left[\left(1 + \frac{1}{m}\right)^m\right]^{rt} = \left[\lim_{m \to \infty} \left(1 + \frac{1}{m}\right)^m\right]^{rt} = e^{rt}$$

Here, the exponent is simply $x = rt$:
- $r$ (Growth Rate): How aggressively the quantity grows at any given instant.
- $t$ (Duration): How long that continuous growth is sustained.
- $x = rt$ (Total Cumulative Growth): The net growth capacity generated over the entire process.

Thus, $e$ represents the baseline factor ($\approx 2.718$) achieved when total cumulative growth equals exactly one unit ($rt = 1$). Any arbitrary rate $r$ or duration $t$ simply scales that standard unit through $e^{rt}$.

## The Benchmark Scale: Defining the "Standard Meter Stick"

To measure continuous compounding universally, mathematicians isolated the purest possible baseline scenario:
- Initial Principal: $1$
- Nominal Annual Interest: $100\%$ ($r = 1$)
- Duration: $1$ year ($t = 1$)

Without compounding (simple interest), $1$ dollar generates $1$ dollar of interest, ending with $2$ dollars. With continuous compounding, however, that same interest capacity yields:$$\lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n = e \approx 2.71828\dots$$

Here, $e$ serves as the Standard Reference Scale: the absolute multiplier achieved when exactly one full unit of baseline growth capacity is fully compounded.

## The Exponent $rt$: Accumulating Simple Interest "Tickets"

To apply this benchmark to real-world investments without recalculating complex limits every time, we separate the process into two clear phases: collecting tickets and redeeming them through the continuous engine.

1. What is a "Ticket" ($rt$)?

    The exponent $rt$ does not represent compound interest. Instead, it is the raw tally of nominal simple interest tickets earned, calculated by simply multiplying the stated annual rate by the number of years:$$\text{Ticket Count } (x) = r \cdot t = (\text{Nominal Rate per Year}) \times (\text{Number of Years})$$

    A ticket count represents: "Ignoring all compounding, what percentage of the initial principal has been earned as raw interest?"

2. Case Studies: Reaching the Same Ticket Count via Different Paths

    The power of this scale is that any combination of rate ($r$) and time ($t$) yielding the same product results in the exact same final multiplier.

    - Case A: Earning Exactly $0.5\text{ Ticket}$ ($50\%$ Growth Gauge)

        If an investment accumulates half of the benchmark capacity ($rt = 0.5$):
        - $5\%$ for $10$ years: $0.05 \times 10 = \mathbf{0.5\text{ ticket}}$
        - $10\%$ for $5$ years: $0.10 \times 5 = \mathbf{0.5\text{ ticket}}$
        - $2.5\%$ for $20$ years: $0.025 \times 20 = \mathbf{0.5\text{ ticket}}$
        - $50\%$ for $1$ year: $0.50 \times 1 = \mathbf{0.5\text{ ticket}}$

    Though the contract terms differ dramatically, every single scenario delivers the identical payoff under continuous compounding:$$\text{Final Multiplier} = e^{0.5} \approx \mathbf{1.6487\dots\times \text{Principal}}$$

    - Case B: Earning Exactly $1.0\text{ Ticket}$ ($100\%$ Full Gauge)

        If an investment completes the full benchmark unit ($rt = 1.0$):
        - Bernoulli's Original Setup: $100\%$ for $1$ year $\implies 1.00 \times 1 = \mathbf{1.0\text{ ticket}}$
        - Conservative Long-Term Bond: $5\%$ for $20$ years $\implies 0.05 \times 20 = \mathbf{1.0\text{ ticket}}$
        - Moderate Medium-Term Loan: $10\%$ for $10$ years $\implies 0.10 \times 10 = \mathbf{1.0\text{ ticket}}$
        - High-Yield Short-Term Venture: $25\%$ for $4$ years $\implies 0.25 \times 4 = \mathbf{1.0\text{ ticket}}$

    Because each strategy produces exactly $1.0$ ticket of raw growth material, feeding them into the continuous compounding engine yields Bernoulli's constant:$$\text{Final Multiplier} = e^{1.0} \approx \mathbf{2.71828\dots\times \text{Principal}}$$
    