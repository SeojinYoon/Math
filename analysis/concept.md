
# Power series

## The etymology of power

The ancient Greek mathematician Euclid used the Greek word dynamis to refer to the area of a square with side length $x$.

Dynamis was translated into Latin as potentia when Greek mathematical texts were translated.

The Latin potentia was translated as power when it entered English.

East Asian mathematicians used the character 冪 to translate the concept, as it traditionally referred to covering a rectangular area in classical geometry.

### Expansion to higher powers

Originally, Greek geometry was tied to spatial intuition: $x^2$ represented a square's area, and $x^3$ represented a cube's volume. Because physical space stops at three dimensions, powers beyond the third were long seen as geometrically meaningless.

This limitation broke down with the rise of algebra. The 3rd-century mathematician Diophantus began combining lower degrees to solve higher-order equations, naming $x^4$ "square-square" and $x^5$ "square-cube." Centuries later, Islamic algebraists and early modern European mathematicians like René Descartes freed repeated multiplication from geometric space entirely.

With modern exponential notation ($x^n$), multiplying a variable by itself became a purely abstract arithmetic operation. Consequently, the term power broadened from its initial meaning of a geometric square to denote the general operation of repeated self-multiplication—yielding the second power ($x^2$), the third power ($x^3$), and arbitrary n-th powers ($x^n$).

### Expansion to power series

The key motivation behind extending individual powers ($x^n$) into an infinite sum—a power series—was to compute and manipulate non-polynomial curves and functions using only basic arithmetic operations.

In the 17th century, the emergence of calculus presented mathematicians with severe computational bottlenecks:
- The Limits of Integration: Finding areas under curves defined by roots or rational forms, such as circles ($y = \sqrt{1 - x^2}$) or hyperbolas ($y = \frac{1}{1 + x}$), could not be solved in finite algebraic terms.
- Transcendental Functions: Functions like trigonometric ($\sin x$, $\cos x$), logarithmic ($\ln x$), and exponential ($e^x$) curves resisted evaluation via simple addition and multiplication.

The breakthrough came with Isaac Newton’s generalized binomial theorem (1665). Newton extended $(1 + x)^r$ beyond integer exponents to fractional powers like $r = 1/2$. This turned roots into infinite polynomials:$$\sqrt{1 - x^2} = (1 - x^2)^{1/2} = 1 - \frac{1}{2}x^2 - \frac{1}{8}x^4 - \frac{1}{16}x^6 - \cdots$$

By converting complex curves into infinite sums of powers, mathematicians could integrate and differentiate them term by term just like ordinary polynomials. Later, mathematicians like Brook Taylor and Colin Maclaurin systematized this idea through derivatives, establishing the modern power series framework that represents smooth functions as infinite polynomial expansions.
