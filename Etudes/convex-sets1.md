## Etrude 1
Is the indicated set convex or not.

> Task 1
$$
\{ X \in S^2 \; | \; X = \begin{bmatrix} x & y \\ y & z  \end{bmatrix}, X \succcurlyeq 0 \}
$$

A symmetric semi-positive definite matrix has the quadratic form, which comprises the set

$$
\{ X \; | \; x^T Xx \geq 0 \}
$$

and is a convex set.

> Task 2

$$
\{ X \in S^2 \; | \; X = \begin{bmatrix} x & y \\ y & z  \end{bmatrix}, x = z \}
$$

or it can be rewritten as

$$
\{ X \in S^2 \; | \; X = \begin{bmatrix} x & y \\ y & x  \end{bmatrix} \}
$$

any linear combination of the set is in the set, therefore it is convex.

> Task 3

$$
\{ X \in S^2 \; | \; X = \begin{bmatrix} x & y \\ y & z  \end{bmatrix}, zx  = 0 \}
$$

The constraint concludes that either one should be 0, it is therefore easy to confirm that the set is not convex

$$
\begin{bmatrix} 
3 & 1 \\
1 & 0
\end{bmatrix}/2 + \begin{bmatrix} 
0 & 1 \\
1 & 3
\end{bmatrix}/2 = \begin{bmatrix} 
1.5 & 1 \\
1 & 1.5
\end{bmatrix}
$$

> Task 4

$$
\{ X \in S^2 \; | \; X = \begin{bmatrix} x & y \\ y & z  \end{bmatrix}, zx  \geq 0 \}
$$

It is easy to disconfirm that the set is not convex by adding two matrices and looking at their middle intersection


$$
\begin{bmatrix} 
-1 & 1 \\
1 & -3
\end{bmatrix}/2 + \begin{bmatrix} 
3 & 1 \\
1 & 1
\end{bmatrix}/2 = \begin{bmatrix} 
1 & 1 \\
1 & -1
\end{bmatrix}
$$

> Task 5

For a fixed $b > 0$, the set

$$
\{ x \in R^n \; | \; ||x||_2 \leq b\}
$$

It is a special case of the euclidean ball, where the centerpoint is origo.

$$
\{ x \in R^n \; | \; (x-0_n)^T(x-0_n) \leq b^2\}
$$

The proof is given in the book and goes like this,

if $||x_1-0_n||_2 \leq r$ and $||x_2-0_n||_2 \leq r$ and $\theta \in [0, 1]$, then

$$
||\theta x_1 + (1-\theta)x_2||_2 \leq \theta ||x_1|| + (1-\theta)||x_2|| \leq \theta b + (1-\theta) b
$$

where we use the homogenity property and the triangle inequality for a norm. 

> Task 6

$$
\{ x \in R^n \; | \; ||x||_2 \geq b, \; b > 0\}
$$

The converse is not true, as we basically can picture the outside of the ball as the set, to prove the point, take two vectors $x_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, x_2 = \begin{bmatrix} -1 \\ 0 \end{bmatrix}$, the line segment between them is not in the set.

$$
||(0.5x_1+0.5x_2)||_2 \ngeq b
$$

> Task 7

For a vector $x \in R^n$ let $x_j$ be the jth largest component of x, i.e.

$$
x_1 \geq x_2 \geq x_3 ... \geq x_n
$$

For a fixed $k \leq n$ the set

$$
\{ (x,t) \in R^n_+ \times R_+ \; | \; x_1 + ... + x_k \leq t \}
$$

we may rewrite the following as

$$
\{ (x,t) \in R^n_+ \times R_+ \; | \; a^T \cdot x \leq t\}
$$

where $a$ is a binary vector, which depends on x, now take for instance

$$
(x, t) = \left(\begin{bmatrix} 1 \\ 0 \end{bmatrix}, 1 \right), \; (y, q) = \left(\begin{bmatrix} 0 \\ 1 \end{bmatrix}, 1 \right), \; \theta = 0.5, \;
$$

which all are in the domain of $(x,t)$

$$
z = \left(x+y \right)/2 \rightarrow \begin{bmatrix} 0.5 \\ 0.5 \end{bmatrix} 
$$

$$
0.5 * 1 \nleq 1
$$

the following set is therefore proven to not be convex.