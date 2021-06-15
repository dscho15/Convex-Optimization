## Lecture 5 - Optimization

Optimization problem in standard form:

$$
\begin{matrix}
\text{minimize } &  f_0(x) & \\
\text{s. t.} & f_i(x) \leq 0, & i = 1,...,m \\
\text{} & h_i(x) = 0, & i = 1,...,p
\end{matrix}
$$

where 

$x$ is the optimization variable, which has to lie in the $\text{dom }  f$ and meet the constraints to be a feasible solution. 

$f_0$ is the cost function, $f_0 : R^n \mapsto R$. 

$f_i : R \mapsto R$ is the inequality constraint functions. 

$h_i : R^n \mapsto R$ is the equality constraint functions.

> optimal value:

$$
p^* = \inf \{ f_0(x) \; | \; f_i(x) \geq 0, \; i,...,m, h_i(x) = 0, i = 1,...,p \}
$$

The optimal value is $\infty$, if there is no $x$ that satifies the constraints, ``infeasibility``, and if the problem is unbounded it might be $-\infty$, meaning it is infinity good.

### Global and Locally Optimal

$x$ is feasible if $x \in \text{dom } f$ and satifies the constraints. Furthermore, a feasible $x$ is optimal if $f_0(x) = p^*$. $x$ is locally optimal if there is an $R > 0$ such that the solution is bounded by a third constraint

$$
\left| \left| z - x \right| \right|_2 \leq R
$$

### Domains

The basic requirements are that you are in all of the functions

$$
x \in \mathbf{D} = \cap^m_{i=0} \; \text{dom } f_i \; \cap^p_{i=0} \; \text{dom }h_i  
$$

the explicit constraints are the inequalities, a problem is unconstrainted if it has no explicit constraints. A implicit constraint is the inputs in the cost function, for instance, $\log{x}$ can only take positive inputs, i.e. it is an implicit constraint that $x \in R_+$

### Feasibility problem

$$
\begin{matrix}
\text{minimize } &  x & \\
\text{s. t.} & f_i(x) \leq 0, & i = 1,...,m \\
\text{} & h_i(x) = 0, & i = 1,...,p
\end{matrix}
$$

a more convenient problem is 

$$
\begin{matrix}
\text{minimize } & 0 & \\
\text{s. t.} & f_i(x) \leq 0, & i = 1,...,m \\
\text{} & h_i(x) = 0, & i = 1,...,p
\end{matrix}
$$

which only has two solution $p^* = 0$ or $p^* = \infty$.

### Convex optimization problem

A standard form convex optimization problem is based on

$$
\begin{matrix}
\text{minimize } & f_0 & \\
\text{s. t.} & f_i(x) \leq 0, & i = 1,...,m \\
\text{} & a_i^Tx = b_i, & i = 1,...,p
\end{matrix}
$$


where the equality constraints are affine (THEY HAVE TO BE DEFINED AS AFFINE), and the objective function / inequalities are convex. The magic lies transforming the problem into a feasible convex problem.

### Local and global optima

If you restrict the search to locally, then you can find the best solution. So suppose $x$ is locally optimal and $y$ is optimal with $f_0(y) < f_0(x)$, where locally means within some norm ball $R$ constraint. Now suppose you have the two feasible points and make a line segment between them, then you know that the line set is feasible as it is convex, and all along that line segment is feasible.

### Optimality

$x$ is optimal if and only if it is feasible and 

$$
\nabla f_0(x)^T (y-x) \geq 0, \; \; \; x,y \in \text{dom } f 
$$

The gradient defines a supporting hyperplane to the feasible set $X$ at $x$.

> Examples:

> Equality constrainted problems

Minimize some function with an affine constraint, where the solution is given by

$$
\nabla f_0(x)^T ( z -x ) \geq 0 \; \; \forall z_{Az=b}
$$

where $z-x \in \mathcal{N}(A) = \{k \in R^n | Ak=0 \}$ and thus the solution is orthogonal to the kernel of A

$$
\nabla f_0(x)^T \in \mathcal{N}(A)^{\perp}
$$

### Equivalent convex problems

Two problems are equivalent if the solution of one is readily obtained from another, one example is to elimate equality constraint. 

> Equality constraints

> Slack variables for linear inequalities

> Epigraph form

> Minimizing variables

### Quasiconvex Optimization

If we are to minimize a quasiconvex objective function, then it may have locally optimal points that are not globally optimal. 
 
### Linear Programming

$$
\begin{matrix}
\text{minimize } &  c^Tx + d & \\
\text{s. t.} & Gx \preccurlyeq h \\
\text{} & Ax = b
\end{matrix}
$$

Everything is affine, the objective, inequality and equality constraints, the feasible set is a polyhedra.


> ``Diet problem``

Chose quantities $x_1, ... x_n$ of n foods,

- one unit of food j costs $c_j$, contains amount of $a_{ij}$ of nutrient $i$
- healthy diet requires nutrient $i$ in quantity at least $b_i$

to find cheapest healthy diet 

$$
\begin{matrix}
\text{minimize } &  c^Tx & \\
\text{s. t.} & Ax \succeq b & x \succeq 0 \\ 
\end{matrix}
$$

Now imagine $\max_{i=1,...,m} (a_i^T x + b_i)$, which pretty much approximates any convexx function, then it can be stated that

$$
\begin{matrix}
\text{minimize } &  t & \\
\text{s. t.} & a_i^T x + b_i \leq t_i
\end{matrix}
$$

