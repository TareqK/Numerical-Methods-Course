# Chapter 5 : Cubic Spline and Curve Fitting

## Cubic Spline

Cubic Spline is one of the examples of what is called the piecewise polynomial interpolation.

Given $(x_0,y_0) ...... (x_n,y_n)$

We want to find a function $S(x)$ 

But what is the general form of $S(x)$?

well,

$$S(x) = \begin{pmatrix} S_0(x) = شلل نفسي بنقله بعدين  -.-\end{pmatrix}$$

We end up with $4n$ unknowns. For $S(x)$ to be a cublic spline, it needs to satisfy

1. $S(x)$ must pass through all of $(x_0,y_0) ...... (x_n,y_n)$, that is $S_0(x_0) = y_0, S_1(x_1) = y_1,...S_n(x_n) = y_n$

2. $S(x)$ is connected at the conjunctions, that is $S_0(x_1) = S_1(x_1), S_1(x_2) =S_2(x_2) .... S_{n-2}(x_{n-1}) = S_{n-1}(x_{n-1})$

3. $S(x)'$ is connected at the conjunctions, that is $S_0'(x_1) = S_1'(x_1), S_1'(x_2) =S_2'(x_2)  .... S_{n-2}'(x_{n-1}) = S_{n-1}'(x_{n-1}) $

3. $S(x)''$ is connected at the conjunctions, that is $S_0''(x_1) = S_1''(x_1), S_1''(x_2) =S_2''(x_2)  .... S_{n-2}''(x_{n-1}) = S_{n-1}''(x_{n-1}) $

    The sum of the conditions = $(n+1) +3(n-1) = 4n -2$

    So we are 2 assumtions short right now !

Now, According to the 2 missing conditions we add, there are 2 types of cubic splines.

1. Natural Cubic Spline

    a. $S''_0(x_0) = 0$

    b.  $S''_{n-1}(x_n) = 0$

2. Clamped Cubic Spline

    a. $S_0'(x_0) = f'(x_0) $

    b. $S_{n-1}'(x_n) = f'(x_n)$

### Curve Fitting

Say we have points $(x_1,y_1)...(x_n,y_n)$

we need to find a curve $f(x)$ that fits these points the most.


There are 3 types of error norms

1. Max Error = Let error $E = MAX_{1\le k\le n}|e_k|$
2. Average Error = Let error $E = \frac{\sum_{k=1}^{n}{|e_k|}}{n}$
3. Root Mean Square error = Let error $ E =  \sqrt{\frac{\sum_{k=1}^{n}{(e_k)^2}}{n}}$

We will be using the third norm to find the $f(x)$ that fits the data the most. This $f(x)$ is called the **least square curve **

### Lineraization 

The general idea is to change the shape of the curve to linear.  We do tis sby changing 

$$ y= f(x) \to \gamma = AX + B $$

we use the normal equations 

$$A\sum{X_k^2} + B\sum{X_k} = \sum{X_k\gamma_k}$$

and

$$A\sum{X_k} + nB = \sum{\gamma_k}\$$