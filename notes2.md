# Lecture 2
## Polyhedra

consists of finitely many linear inequalities and equalities, e.g. hyperplanes and halfspaces; it is an intersection of all of those so to say.

$$
Ax <= b
$$

where this is elementwise.

$$
Cx = d
$$

we can denote the set

$$
\{ \; x \; | \; Ax \leq b, \; Cx=d \; \}
$$

now, how do we prove that it is convex? Usually, we would utilize the fact that one solution $x = \theta x_1 + (1-\theta) x_2$, we just need to prove this.

$$
\begin{matrix}
Cx_1 =d & Cx_2=d  \\
Cx = d \rightarrow & C\left( \theta x_1 + (1-\theta)x_2\right) = d \\
Ax_1 \leq b & Ax_2 \leq b \\
Ax\leq b \rightarrow & A\left( \theta x_1 + (1-\theta)x_2\right) \leq b
\end{matrix}
$$

## Positive semidefinite cone

$S^n$ is a set of symmetric $n \times n$ matrices

$$
\begin{matrix}
X \in S^n & Y \in S^n & 1 \geq \theta \geq 0 \\
\end{matrix}
$$

$$
\theta X + (1-\theta )Y = Z
$$

The sum of symmetric matrices are still symmetric, so we don't have to perform further steps, and they are indeed convex.

$S^n_+ = \{ X \in S^n | X \geq 0 \}$, symmetric positive-semidefinite matrices, then we know that multiplied with any vector $z \in \;\mathbb{R}^n$ gives a positive solution in quadratic form. And to prove that the matrix is convex we use our knowledge from convex cones

$$
X \in S^n_+ \; \; Y \in S^n_+ \; \; \theta_1 X + \theta_2 Y
$$

where $\theta_i \geq 0$, now we merely take the quadratic form to prove convexity.

$$
Z^T\left( \theta_1 X + \theta_2 Y \right) Z \geq 0
$$

Another matrix is $S^n_{++} = \{ X \in S^n \; | \; X > 0 \}$

## Operations that preserve convexity

> Apply definition $x_1, x_2 \in C$, $0 \leq \theta \leq 1$

> show that $C$ is obtained from simple convex sets by operations that preserve convexity

- intersection
- affine functions
- perspective functions
- linear-fractional fucntions

> "matlab" oracle approach, merely plot it xD

## Intersection

The intersection of any number of convex sets is convex

## Affine functions

suppose, $f: \mathbb{R}^n \rightarrow \mathbb{R}^m$ is affine, e.g. ($f(x) = Ax+b$), then we know that the mapping and inverse mapping is also convex, e.g.

$$
\begin{matrix}
S \subseteq R^n \; \text{convex} & f(S) = \{ f(x) \; | \; x \in S \} \; \text{convex}
\end{matrix}
$$

$$
\begin{matrix}
C \subseteq R^n \; \text{convex} & f^{-1}(C) = \{ x \in R^n \; | \; f(x) \in C \} \; \text{convex}
\end{matrix}
$$

## Generalized inequalities

A convex cone, $K \subseteq \mathbb{R}^n$ is a proper cone if it is:

> K is closed (contains its boundary)

> K is solid (nonempty interior)

> K is pointed (contains no line)

Without these three constraints, the theory would fall apart quickly. An example, is the non-negative orthant and a positive semidefinite cone $K = S^n_+$.

### Generalized inequailities: defined by a proper cone K

> $x \leq_K y$ is defined as $y - x \in K$ and similarily, $x <_K y$ is $y - x \; \in \text{int} K$.

Componentwise inequalities, e.g.

$$
x \leq_{R^n_{+}} y
$$

where the two points lies within the postive domain of R, and all the elements of y is greater than or equal to x.

### Generalized inequalities: minimum and minimal elements

$x \in S$ is the minimum element of $S$ with respect to $\leq_K$ if $y \in S \rightarrow x \leq_k y$, which should be read as, if any point in the set $S$ is more than $y$ in the set, then $x$ is the minimum element.

The minimal element of a set with respect to $\leq_K$ means that no points are least.

### Seperating hyperplane thereom

If we have two disjoint convex sets C and D, then there exists an $a \neq 0$, b, such that we are able to seperate the two sets by a hyperplane.

### Supporting hyperplane thereom

Given a set C, then there exists a hyperplane tangential at the point $x_0 \in C$ on the boundary $\{ x \; | \; a^Tx = a^T x_0 \}$, the interior set of C and the boundary point (is convex) is a disjunctive, $Ø$, and therefore it is a special case of the seperating hyperplane thereom.

### Dual cones and generalized inequalities

For any cone $K$, we define the dual cone

$$
K^* = \{ y  \; | \; y^T x \geq 0 \; \text{for all } x \in K \}
$$

### Minimum and minimal elements via dual inequalities

### Optimal production frontier

## Assignment

> Show that $\sum_i^k \theta_i x_i \in C$ by induction on k

Given the constraint $\theta_i \geq 0$
$$
\theta_1 + \theta_2 + \theta_3 = 1
$$
and it might not hold
$$
\theta_1 x_1 + (1 - \theta_1)x_2 \notin C
$$
unless $\theta_3 = 0$. Proof by induction $k=3$, now given the two equations with constraint $\theta_1 \neq 1$

$$
\theta_2 x_2 + \theta_3 x_3 \notin C
$$

however, with linear scalarization

$$
\frac{\theta_2}{1 - \theta_1} x_2 + \frac{\theta_3}{1 - \theta_1} x_3 \in C
$$

so we may now rewrite

$$
\theta_1 x_1 + (1 - \theta_1)\left( \frac{\theta_2}{1 - \theta_1} x_2 + \frac{\theta_3}{1 - \theta_1} x_3 \right) \in C
$$

and so on..

> Show that a set is convex if and only if its intersection with any line is convex. ``Show that
a set is affine if and only if its intersection with any line is affine``.

A set $S$ and $B$ is intersecting, we know the intersecting set is convex if both are convex. Since a line $L$ is a convex set, then we know that the other set $C$ is convex, if the line intersection is convex.

Now if the set $C$ is convex, and the line-segment crosses between $x_1$ and $x_2$ then the linear combination of $x_1$ and $x_2$ belong to the intersection, and is also a part of the set $C$.`

> What is the distance between two parallel hyperplanes $\{ x \in R^n | a^T x = b_1 \}$ and $\{ x \in R^n | a^T y = b_2 \}$.

It can be determined by projection the error $||x - y||^2_2$ down onto $a^T$ to then measure the length, which can be done by

$$
\frac{\left| \left| a^T \bullet (x-y) \right| \right|_ 2}{||a||_2}
$$

> Voronoi description of halfspace. Let a and b be distinct points in $R^n$. Show that the set of all points that are closer  (in Euclidean norm) to a than b, is a halfspace. Describe it explicitly as an inequality of the form $c^T x \leq d$. 

It is given that
$$ ||x - a||_2^2 \leq ||x - b||_2^2 $$
i.e.
$$ 
x^Tx - 2a^Tx + a^T a \leq x^Tx - 2b^Tx + b^T b
$$
$$ 
2(b-a)^Tx \leq b^T b - a^T a
$$

where $c =2(b-a)$ and $d= b^T b - a^T a$

> Which of the following sets S are polyhedra? If possible, express S in the form $S = \{ x  \; | \; Ax \leq b, Fx = g \}$

- $S = \{ y_1 a_1 + y_2 a_2 \; | \; -1 \leq y_i \leq 1 \}$, where $a_1, a_2 \in R^n$

so basically it is a plane, consisting of four hyperplanes and with constrainted by two normal vectors i.e.

$$
a = \begin{bmatrix}
\pm 1 \\ 0
\end{bmatrix} \text{and } a = \begin{bmatrix}
0 \\ \pm1
\end{bmatrix}
$$

$$
A = \begin{bmatrix} 1 & 0 \\
                    -1 & 0 \\
                    0 & 1 \\
                    0 & -1
    \end{bmatrix} \; \; \;b = \begin{bmatrix} 1 \\
                    -1 \\
                    1 \\
                    -1
    \end{bmatrix}
$$

- $S = \{ x \in R^n \; | \; x \geq 0, \; 1^T x = 1, \; \sum x_ia_i = b_1, \; \sum_i x_i a_i = b_2 \}$.

we know that x is a vector in $R^n$ with three constraints: unit, linear and quadratic halfplanes.

- $S = \{ x \in R^n \; | \; x \geq 0, \; x^T y \leq 1 \text{ for all } y, \; ||y||_2 = 1\}$

$x$ has to be larger than $0$, meaning it is in $R^n_{+}$, and should be within unit length, constrainted by unit length, however, this is not a polyhedran, as it would require infinitely many halfspaces, rather it uniquely defined as being a unit-ball. 

- $S = \{ x \in R^n \; | \; x \geq 0, \; x^T y \leq 1 \text{ for all } y \; \sum |y|_i = 1\}$

in $R^2$ it forms a rotated square and a diamant in $R^3$, to write the constraints, we have to consider all the halfspaces and the constraints they impose; 

in $R^2$ the constraints is as follows
$$
a_x \cdot x \leq b_x \; \; \; a_y \cdot x \leq b_y \; \; \; a_{\angle} \cdot x \leq b_1 
$$
in $R^3$ the constraints are similar; one constraints (normal vector) for each plane spanned by $\sum |y|_i=1$, i.e. the solution space is embedded in $R^n_+$ (due to x being strictly positive) with one more constraint comprised of the halfplane that intersects with the unit-axes.

> Which of the following sets are convex?

- A slab - $\{ x  \in R^n | \alpha \leq a^Tx \leq \beta \}$

A slab is a convex set, as the solution set is comprised of two half spaces:

$$
\{ x \; | \; a^T x_\alpha \leq a^T x \leq a^T\ x_\beta  \}
$$

- A rectangle, i.e., a set of the form $\{ x \in R^n \; | \; \alpha_i \leq x_i \leq \beta_i, \; i = 1,...,n\}$, sometimes called a hyperrectangle. 

The set is comprised of $n^2$ halfspaces parametrized by normalvectors, since the set is closed by halfspaces it is a polyhedron and a polyhedron is convex. 

- A wedge $\{ x \in R^n \; | \; a_1^T x \leq b_1,  a_2^T x \leq b_ 2 \}$

The set is not convex, since the normal vectors are not strictly parallel, if they were the set would be constrained by two halfspaces, but instead they might intersect thus forming two convex sets.

- The set of points closer to a given point than a given set, i.e., 

$$
\{ x \; | \; ||x - x_0 ||_2 \leq ||x-y||_2 \text{ for all } y \in S \}
$$

where $y \subseteq R^n$

$$
\begin{matrix}
(x-x_0)^T(x-x_0) \leq (x-y)^T(x-y) \\
x^Tx -2x_0^Tx+x_0^T x_0\leq x^Tx-2y^Tx+y^Ty \\
2y^Tx-2x_0 ^Tx \leq y^Ty-x_0^Tx_0
\end{matrix}
$$

which is a halfspace.

- The set of points closer to one set than another, i.e., 

$$
\{ x \; | \; \text{dist}(x, S) \leq \text{dist}(x, T) \}
$$

where $S, T \subseteq R^n$ and $\text{dist}(x, S) = \inf \{ ||x-z||_2 \; | \; z \in S\}$. The infinum is a set smallest element, which in this case is the $z$ closest to $x$, generating arbitrary sets it should not be hard to confirm that this is not true.

- The set $\{ x | x + S_2 \subseteq S_1 \}$ where $S_1, S_2 \subseteq R^n$ where $S_1$ is convex. 

Any x, that maps a one arbitrary set to a convex set forms a convex set, e.g.

$$
x + S_2 \subseteq S_1 \text{ if } x + y \in S_1 \text{ for all } y \in S_2 
$$

$$
\{ x  \; | \; x + S_2 \subseteq S_1 \} = \cap_{y \in S_2} \{ x  \; | \; x + y \subseteq S_1 \} = \cap_ {y \in S_2} (S_1 -y)
$$

and translation and intersection with convex sets are convex.

- The set of points whose distance to a does not exceed a fixed fraction $\theta$ of the distance to b. The set

$$
\{ x \; | \; || x - a ||_2 \leq \theta^2 || x-b ||_2 \}
$$

we can assume $a \neq b$ and $\theta$ ranges from 0 to 1. Firstly, we may rewrite the math

$$
x^Tx - 2a^Tx + a^Ta \leq \theta^2 \left[ x^T x-2b^Tx+b^T b \right]
$$

which we know from before constitutes a half space

$$
(1-\theta^2)\cdot x^Tx + 2(\theta^2b - a)^T x + (a^T a- \theta^2b^T b) \leq 0
$$

$$
x^Tx - 2\frac{(a - \theta^2b)^T}{k} x + \frac{(a^T a- \theta^2b^T b)}{k} \leq 0
$$

$$
x^Tx - 2\frac{(a - \theta^2b)^T}{k} x \leq \frac{(\theta^2b^T b - a^T a)}{k}
$$

$$
(x-\frac{(a - \theta^2b)}{k})^T(x-\frac{(a - \theta^2b)}{k})\leq \frac{(\theta^2b^T b - a^T a)}{k} + (\frac{a - \theta^2b}{1-\theta})^T(\frac{a - \theta^2b}{1-\theta})
$$

$$
(x - x_0)^T(x-x_0) \leq R^2
$$

when $\theta$ is 1, it is equal to a halfspace, otherwise it is a ball 

> Some set of probability distributions. Let x be a real-valued random variable with $\text{prob}(x=a_i) = p_i$ where $i = 1...n$ and let $p \in R^n$ lies in the standard probability distribution simplex $P = \{ p \; | \; 1^Tp=1, \; p \leq 0 \}$. Which of the following conditions are convex in p?

<p align="center">
  <img src="prob.PNG">
</p>

> (a) Given that x is constant, then $\alpha \leq p \bullet f(x) \leq \beta$, which is a linear constraint, e.g. convex

> (b) The probability of $x > \alpha$ is equal to $\sum_{x_i > \alpha_i} p_i$ which then is compared with $\beta$, i.e. $\sum_{x_i > \alpha_i} p_i \leq \beta$

> (c) The expected value her is equal to $\sum p_i \left( |a_i|^3 - |a_i| \cdot \alpha \right)$, which again is a linear conmstraint.

> (d) The expected value of $x^2$ is equal to $\sum_i p_i x_i \leq \alpha$, which is a linear constraint.

> (e) the expected value is once agian a linear constraint, $x \bullet p \geq \alpha$

> (f) the variance is not a convex set, since it is concave, illustrated by

$$
\text{var}(x) \leq \alpha \; \; \; \rightarrow \; \; \; \sum p_i a_i -  \left(\sum p_i a_i\right)^2 \leq \alpha
$$

$$
\sum p_i a_i^2 -  \left(\sum p_i a_i\right)^2 \leq \alpha \; \; \; \rightarrow \; \; \; p^Tx - \left( p^T x x^T p \right) \leq \alpha
$$

knowing that $xx^T$ is a postive semi-definite matrix, taking the minus makes it negative semidefinite, which means that q is not convex.

> (g) know that var(x) is concave in p, due to the matrix being negative semi-definite, it follows from the definition that the following underneath is true for a concave function, thereby it is true.

$$
p^Tx - \left( p^T x x^T p \right) \geq \alpha
$$

> (h) quartile(x) $\geq \alpha$, where a quartile is defined as the probability of x is larger than $\beta$ where that probability is above $0.25$ is a linear and thus convex constraint, unless $a_1 \leq \alpha$, then it is not defined:

$$
\text{prob}(x \leq a_k) = \sum^k_{i:} p_i < 0.25
$$

> (i) the quartile(x) is lower or equal to alpha, which means that the probability or the returned value should be less than $0.25$.

> 2.16 - Operations that preserve convexity

Show that if $S_1$ and $S_2$ are convex sets in $R^{m \times n}$ then so is their partial sum:

$$
S = \{ ( x, y_1 + y_2) \; | \; x \in R^m , y_1, y_2 \in R^n, (x,y) \in S_1, (x,y) \in S_2 \}
$$

Use the rule that each convex set, should with two arbitrary points comprise a line segment as solution space, thus by picking two points in each set and using those to interpolate, we can prove that the set is indeed convex, when the two convex sets are.

> 2.17 - Image of polyhedral sets under perspective fdunction, in this problem, we study the image of hyperplanes, halfspaces and polyhedra under perspective function $P(x,t) = x/t$ with $\text{dom}P = R^n \times R_{++}$. For each of the following C, given a simple description of: 
$$
P(C) = \{ v/t \; | \; (v,t) \in C, t > 0\}
$$

> The polyhedron $C = \text{conv}\{ (v_1, t_1), ..., (v_k, t_k)\}$ where $v_i \in R^n$ and $t_i > 0$. Now $\text{conv}\{v \} = \{ \sum \theta_i \cdot v_i \;| \; \theta \geq 0, \;1^T\bullet \theta =1\}$

first, I rewrite the operator in terms of v and t. 

$$
\begin{matrix}
v = \sum \theta_i \cdot v_i & t = \sum \theta_i\cdot t_i
\end{matrix} 
$$

thus the operator can be described as 

$$
\begin{matrix}
P(x) =\frac{\sum \theta_i \cdot v_i}{\sum \theta_i \cdot t_i}
\end{matrix}
$$

now that operator is defined, which simply $P(C) \subseteq \frac{\sum \theta_i \cdot v_i}{\sum \theta_i \cdot t_i}$

> The hyperplane $C=\{ \; (v,t) \; | \; f^T v + gt = h  \; \}$

By dividing with t, we get the operator, which we want.

$$
\begin{bmatrix}
f \\
g
\end{bmatrix} \bullet
\begin{bmatrix}
v \\t
\end{bmatrix} =h \rightarrow_{1/t} \{ z \; | \; f \bullet z + g = h/t\}
$$

three scenarios exists, h can be zero, positive or negative.

> The hyperplane $C=\{ \; (v,t) \; | \; f^T v + gt \leq h  \; \}$

$$
\begin{bmatrix}
f \\
g
\end{bmatrix} \bullet
\begin{bmatrix}
v \\t
\end{bmatrix} =h \rightarrow_{1/t} \{ z \; | \; f \bullet z + g \leq h/t\}
$$

three scenarios exists, if h is zero, then it is strictly constrainted. If h is larger than 0, then it is entire $R^n$ the logic is that t can take any value, thus the solution can range the entire space of $R^n$, if h is smaller than zero, then the set is not free. 

> The polyhedron $C = \{ (v, t) | Fv + gt \leq h\}$.
The polyhedron consists of an affine solution $Fv$ and a direction-vector $g$. 

$$
P(C) = \{ z \; | \; Fv + g \leq h/t, \; \text{any } t > 0\}
$$

Three solutions exists

https://math.stackexchange.com/questions/1988497/image-of-polyhedral-sets-under-perspective-function-convex-optimization

$$
\begin{matrix}
z \; | \; Fv + g \leq 0, \; h = 0 \\
z \; | \; Fv + g \geq 0, \; h > 0 \\
\end{matrix}
$$



#### Lecture 2
> https://www.youtube.com/watch?v=P3W_wFZ2kUo