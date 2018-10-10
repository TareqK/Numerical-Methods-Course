# Chapter 3 : Solving (Square) Systems of Equations

There are 2 kinds of systems : linear and nonlinear systems.

## Non-Linear Systems

Non linear systems are systems of equations where
there is an exponent to the variables. A solution to a system satisfies all the equations.

In general, a 2x2 system looks like

$f_1(x,y)=0$

$f_2(x,y)=0$

with exact solution

$(p,q)$

a 3x3 system looks like

$f_1(x,y,z)=0$

$f_2(x,y,z)=0$

$f_3(x,y,z)=0$

with exact solution

$(p,q,r)$

There are three methods we are going to be using to solve nonlinear systems.

1. Newton's Method --> only for 2x2
2. Fixed Point Iteration --> 2x2 or 3x3
3. Gauss-Seidel Iteration --> 2x2 or 3x3

### Newtons Method for Non-Linear Systems

We need $p_0,q_0$ and $f_1(x,y)=0, f_2(x,y)=0$

Note : The solution can be written as a vector

The iteration is given by :

$$\begin{pmatrix}p_1\\ q_1 \end{pmatrix} =\begin{pmatrix}p_0\\ q_0 \end{pmatrix} - J^{-1}|_{(p_0,q_0)}\begin{pmatrix}f_1(p_0,q_0)\\ f_2(p_0,1_0) \end{pmatrix}$$


where $J$ is the **jacobian matrix** of the 2x2 system is given by

$$
\begin{pmatrix} \frac{\delta f_1}{dx} \frac{\delta f_1}{dy} \\ \frac{\delta f_2}{dx} \frac{\delta f_2}{dy} \end{pmatrix}
$$

This can be considered the derivative of the system. Therefore, the above iteration equation is equivalent to $p_{n+1}=p_n - \frac{f(p_))}{f'(p_n)}$


---

### Fixed Point Iteration for Non-Linear Systems

(For 2x2 systems)We need $p_0,q_0$ and $g_1(x,y)=x, g_2(x,y)=y$

This means that $g_1(p,q) = p$ and $g_2(p,q) = q$


The iteration is given by :


$$p_{n+1} = g_1(p_n,q_n)$$

$$q_{n+1} = g_2(p_n,q_n)$$

---

### Gauss-Seidel Iteration for Non-Linear Systems

It is almost identical to Fixed Point Iteration, with some improvment.

(For 2x2 systems)We need $p_0,q_0$ and $g_1(x,y)=x, g_2(x,y)=y$

$p_1=g_1(p_0,q_0)$

$q_1=g_2(p_1,q_0)$

notice that we are substituting the found value of $p_{n+1}$ to find $q_{n+1}$. Generally

$$ p_{n+1}=g_1(p_n,q_n)$$ 

$$ q_{n+1} = g_2(p_{n+1},q_n)$$

---
