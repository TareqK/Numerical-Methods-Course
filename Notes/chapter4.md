# Chapter 4 : Interpolation 

part of polinomial approximatin

general idea : given $f(x), x \le b$, how do you approxmiate $f(x)$ by a polinomial $P_n(x)$ ? 

Answer : You find some points of $f(x)$ and you use these points to find $P_n(x)$ where $P_n(x) \approx f(x)$ for $a\le x \le b$

Given the following points $(x_0,y_0),(x_1,y_1),....,(x_n,y_n)$ where $x_0 \lt x_1 \lt .... \lt x_n$,
then $\exists!$ Polimomial $P_n(x)$ of degree **at most** $n$ that passes through these points.

## Newton Polynomial

$$P_n(x) = a_0 + a_1(x-x_0) + a_2(x-x_0)(x-x_1) + .... + a_n(x-x_0)(x-x_1)...(x-x_{n-1})$$

where $a_n$ is the value of $f[x_0,....x_n]$

### Larange

1. for 2 points : $f(x) = \frac{(x-x_1)}{x_0-x_1}f_0 + \frac{(x-x_0)}{(x_1-x_0)}f_1$

2. for 3 points : $\frac{(x-x_1)(x-x_2)}{(x_0-x_1)(x_0-x_2)}f_0 + \frac{(x-x_0)(x-x_2)}{(x_1-x_0)(x_1-x_2)}f_1 + \frac{(x-x_0)(x-x_1)}{(x_2-x_0)(x_2-x_1)}f_2$

### Divided Difference

The general form of the divided difference is 

$$f[x_0,x_1.....,x_n] = \frac{f[x_0,......x_{n-1}] - f[x_1,....,x_n]}{x_0-x_n}$$

and 

$$f[x] = f(x)$$

so

$$f[x_0,x_1] = \frac{f_0-f_1}{x_0-x_1}$$

## Uniform Partition(Equally Spaced Nodes)

- divide the range into $n$ points
- Find $h =\frac{x_0-x_n}{n} $
- Find $x_n = x_0 + n*h $
- Find $y(x)$ for all $x$
- Solve like before

## Interpolation Error

Interpolation Error is a type of **truncation error**. The general idea is that
you have a set of points $(x_0,y_0)...(x_n,y_n)$ that you use to approximate $f(x)$.
however, it is not the complete function, so $f(x) = P_n(x) + E_n(x)$ it is similar to the error in taylor series, given by :

$$E_n(x) = \frac{(x-x_0)(x-x_1)...(x-x_n)f^{(n+1)}(c)}{(n+1)!}$$

We cannot find the true error, but we can fin the upper bound of the error

Uniform : 

1- $|E_1(x)| \le \frac{h^2M_2}{8}$

2- $|E_2(x)| \le \frac{h^3M_3}{9 \sqrt{3}}$

3- $|E_3(x)| \le \frac{h^4M_4}{24}$

Where $M_k$ is the max of $f^{n+1}(x)$ 

Non-Uniform

- Use the general formula, then find the max of $Q(x) = (x-x_0)....(x-x_n)$

- Find the max of $M_k = f^{n+1}(x)$

- calculate $|E(x)| = \frac{MAX(Q(x))*MAX(f^{(n+1)}(x))}{(n+1)!}$ 

----

## Proofs

Proof that the upper bound of the uniform of error is given by $|E_1(x)| \le \frac{h^2M_2}{8}$

proof

$$E_1(x)\frac{(x-x_0)(x-x_1)f''(x)}{2}$$
