
# Matrix representation of polynomial product

The product of two multi-variable polynomials, such as $(x + y + z)(a + b + c)$, can be elegantly represented using linear algebra. 

1. Algebraic Intuition

    When we expand $(x + y + z)(a + b + c)$, **the distributive law** dictates that every term in the first parenthesis must multiply every term in the second. This results in $3 \times 3 = 9$ distinct terms:$$(x+y+z)(a+b+c) = xa + xb + xc + ya + yb + yc + za + zb + zc$$

2. Vector Summation Form

    Each group can be viewed as the sum of elements within a vector. In matrix notation, the sum of elements in a vector is achieved by taking the dot product with the ones vector ($\mathbf{1}$).

    Given:$$\mathbf{u} = \begin{bmatrix} x \\ y \\ z \end{bmatrix}, \quad \mathbf{v} = \begin{bmatrix} a \\ b \\ c \end{bmatrix}, \quad \mathbf{1} = \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}$$

    The expression can be written as:$$(x + y + z)(a + b + c) = (\mathbf{1}^T \mathbf{u})(\mathbf{1}^T \mathbf{v})$$

3. Matrix Expansion

    The full matrix representation you provided breaks down the operation into four distinct components:$$(x + y + z)(a + b + c) = \underbrace{\begin{bmatrix} x & y & z \end{bmatrix} \begin{bmatrix} 1 \\ 1 \\ 1 \end{bmatrix}}_{\text{Sum of } \mathbf{u}} \times \underbrace{\begin{bmatrix} 1 & 1 & 1 \end{bmatrix} \begin{bmatrix} a \\ b \\ c \end{bmatrix}}_{\text{Sum of } \mathbf{v}}$$

    - Left Side: A row vector multiplied by a column vector of ones results in the scalar sum $(x+y+z)$.
    - Right Side: A row vector of ones multiplied by a column vector results in the scalar sum $(a+b+c)$.

4. Connection to Outer Product

    Alternatively, if we wish to see all 9 individual terms in a structured grid, we can use the outer product:$$\mathbf{u}\mathbf{v}^T = \begin{bmatrix} x \\ y \\ z \end{bmatrix} \begin{bmatrix} a & b & c \end{bmatrix} = \begin{bmatrix} xa & xb & xc \\ ya & yb & yc \\ za & zb & zc \end{bmatrix}$$

    The total sum of all elements in this $3 \times 3$ matrix is exactly equal to the polynomial product $(\mathbf{1}^T \mathbf{u})(\mathbf{1}^T \mathbf{v})$.