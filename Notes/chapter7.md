# Chapter 7 : Numerical Integration

The general idea is to estimate $\int_{a}^{b}{f(x) dx}$

We know that the value of $\int_{a}^{b}{f(x) dx}$ is the area under the curve. 

We also know that $\int_{a}^{b}{f(x) dx} = \sum_{1}^{n}{f(C_k)\triangle x_k}$ (Reemans Sum)

The idea is to replace Reemans Sum with other formulas called **Quadrature Formulas** to approximate $\int_{a}^{b}{f(x) dx}$, so

$$\int_{a}^{b}{f(x) dx} = Q[f] + E[f]$$

## Quadrature Formulas

### Closed Newton-Cotes Quadrature Formulas

1. Trapezoidal Rule --> $\int_{a}^{b}{f(x) dx} = \frac{h}{2}(f_0+f_1) - \frac{h^3f''(c)}{12}$, where $h$ is the distance between $x_0,x_1$

2. Simpsons Rule--> $\int_{a}^{b}{f(x) dx} = \int_{x_0}^{x_2}{f(x) dx} = \frac{h}{3}[f_0+4f_1 + f_2] - \frac{h^5f^{(4)}(c)}{90}$, where $h=\frac{b-a}{2}$

3. Simpsons $\frac{3}{8}$ rule--> $\int_{a}^{b}{f(x) dx} = \int_{x_0}^{x_3}{f(x) dx} = \frac{3h}{8}[f_0 + 3f_1 + 3f_2 + f_3] - \frac{3h^5f^{(4)}(c)}{80}$, where $h=\frac{b-a}{3}$



### Gauss-Legendre  Quadratures

1. Two points formula --> $\int_{-1}^{1}f(x)dx = f(-\frac{1}{\sqrt{3}}) + f(\frac{1}{\sqrt{3}}) $, $E=\frac{1}{135}f^{(4)}(c)$

2. Three points formula --> $\int_{-1}^{1}f(x)dx = \frac{5}{9}f(-\sqrt(\frac{3}{5})) + \frac{8}{9}f(0) +\frac{5}{9}f(\sqrt(\frac{3}{5}))$, $E=\frac{1}{15750}f^{(6)}(c)$


#### Shifting Gauss-legendre

say we want to find $\int_{a}^{b}f(x)dx$ using gauss-legendre. Then we need to perform the transform 
$t = \frac{a+b}{2} + \frac{b-a}{2} x$, which maps $[-1,1]\to[a,b]$, and $dt =\frac{b-a}{2}dx$,
and solve for $\int_{-1}^{1}f(t)dt$

## Degree Of Percision

Defn : given a $Q[f]$, the DOP of $Q[f]$ is the largest positive integer $n$ such that the formula is exact $\forall$ polynomials of degree $\le n$, In other terms, the DOP of $Q[f]$ is $n$ if $E[1]=E[x]=E[x^2]...=E[x^n] = 0 $, but $E[x^{n+1}]\ne 0$
