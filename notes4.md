# Lecture 4

## Minimization

if a function $f(x,y)$ is convex in $(x,y)$ and $C$ is a convex set, then 

$$
g(x) = \inf_{y \in C} f(x,y)
$$

is convex.

> Example

$$
f(x,y) = x^T A x+ 2x^TBy+y^TCy
$$

with the general form

$$
\begin{bmatrix}
A & B \\
B^T & C 
\end{bmatrix} \geq 0 \; \; \;
C \geq 0
$$

to utilize the thereom, it is provided that $f(x,y)$ is jointly convex (u plot both x and y the graph is ball-shaped) in $(x,y)$, this assume that the block matrix is positive semi-definite and C is positive definite. Minimizing over $y$ gives 

$$
g(x) = \inf_yf(x,y) = x^T(A-BC^{-1}B^T)x
$$

g is convex, hence schur Complement is convex

$$
A-BC^{-1}B^T \geq 0
$$

we can get to this result by simply computing the gradient.

> Example

$$
\text{dist}(x,S) = \inf_{y \in C} ||x-y||
$$
is convex, if S is convex.

A simple proof is to start with the inside function $x-y$, which is a linear function:

$$
f(x,y) = x-y
$$

and it is merely squared, that way we know it is convex.

> Example Perspective

The perspective of a function, $f: R^n \mapsto R$, is the function $g: R^n \times R \mapsto R$,

$$
g(x,t) = tf(x/t), \; \; \; \text{dom } g= \{(x,t) | x/t \in \text{dom }f, \; t > 0 \}
$$

The perspective function scales $x$ at first, and then multiplies the product of the function by t.

## Conjugate function

the conjugate of a function f is defined as

$$
f^*(a) = \sup_{x \; \in \; \text{dom }f} \left( \langle a,x \rangle  - f(x) \right)
$$

thinking of the problem in 1D, where $a$ as is the slope coeffiecient, then we may think of infinite many parallel lines with the slope $a$:

$$
\langle a,x \rangle  + \alpha \leq f(x)
$$

$$
\alpha \leq - [\langle a ,x \rangle  - f(x)]
$$

$$
\alpha \leq - [\langle a,x \rangle  - f(x)]
$$

e.g.

$$
f^*(0) = \sup_{x \; \in \; C} \{ -f(x) \}
$$

$$
f^*(0) = -\inf_{x \; \in \; C} \{ f(x) \}
$$

where $\alpha$ is the constant part, which is a constant part. So the conjugate function is basically what is the function value for some slope $\alpha$.

The properties of affine conjugate functions

a) if we choose some $a, x \in C$, Fenchel's inequality:

$$
f^*(a) \geq \langle a,x \rangle - f(x) \rightarrow f^*(a) + f(x) \geq \langle a,x \rangle 
$$

and b) if we apply a conjugate twice, we get the original value.

## Quasi-convexity functions

$f: R^n \mapsto R$ is a quasiconvex function if $\text{dom } f$ is convex and the sublevel sets

$$
S_{\alpha} = \{ x \in \text{dom } f \; | \; f(x) \leq \alpha \}
$$

are convex for all $\alpha$

<p align="center">
  <img src="imgl4/quasiconvex.PNG">
</p>

where $f$ is quasiconcave if $-f$ is quasiconvex and $f$ is quasilinear if it is quasiconvex and quasiconcave.