# Chapter 6 : Numerical Differentiation

Remember : 

$$f'(x_0)=\lim_{h->0}{\frac{f(x_0+h)-f(x_0)}{h}}$$

where $h$ is the step size or bandwidth.

But now, we will use numerical methods to find $f'(x_0)$ or higher order derivatives. These formulas are called **difference formulas** or finite difference formulas.

### Difeerence Formulas

There are three types of  difference formulas :

1. Central Difference Formulas $\to$ CDF
2. Forward Difference Formulas $\to$ FDF
3. Backwards Difference Formulas $\to$ BDF

There are five formulas we are going to be studying

1. CDF of order $O(h^2)$ for $f'(x_0)$

    $f'(x_0) \approx \frac{f(x_0+h) - f(x_0-h)}{2h}   
    $ with error $E = \frac{-h^2f'''(c)}{6}$.

    Notation : $f(x_0+kh) = f_k, k=\pm1,\pm2,..$

    so we can express the above as $f'(x_0)=\frac{f_1-f_{-1}}{2h}$ with error $E = \frac{h^2f'''(c)}{6}$

    
2. FDF of order $O(h^2)$ for $f'$ 

    $f'(x_0) \approx \frac{-3f_0 + 4f_1 -f_2}{2h} $ Where error $E =\frac{h^2f'''(c)}{3}$ 

3. BDF of order $O(h^2)$ for $f'$

    $f'(x_0) \approx \frac{3f_0+4f_{-1}+f_{-2}}{2h}$  with error $E = \frac{h^2f'''(c)}{3}$  

4. CDF of order $O(h^4)$ flor $f'$

    $f'(x_0) \approx \frac{-f_2+8f_1-8f_{-1}+f_{-2}}{12}$ with error $E = \frac{h^4f^{(5)}(c)}{30}$

5. CDF of order $O(h^2)$ for $$f''$

    $f''(x_0) \approx \frac{f_1-2f_0+f_{-1}}{h^2}$ with error $E = \frac{-h^2f^{(4)}(c)}{12}$


But how do we derive a difference formula?

### Deriving Difference Formulas

There are 3 ways to do this

1. Taylor Series
2. Lagrange Interpolation
3. Newton's Polynomial

#### Deriving Difference Formulas : Taylor Series

Notice that the numerator always contains $x_0$ somwhere. Say we apply the taylor series of $f(x)$ about $x_0$. We get $f(x) = f(x_0) + (x-x_0)f'(x_0) + \frac{(x-x_0)^2f''(x_0)}{2!}+...$

Now, lets replace $x$ with $x_0+kh$. Then we get

$f(x) = f(x_0) + (x_0+kh-x_0)f'(x_0) + \frac{(x_0+kh-x_0)^2f''(x_0)}{2!}+...+\frac{(x_0+kh+x_0)^{n+1}f^({n+1})(c)}{(n+1)!}$

Simplifying, we get

$f_k = f_0 +khf'(x_0) + \frac{(kh)^2}{2}f''(x_0)+....+\frac{(kh)^{n+1}f^{(n+1)}(c)}{(n+1)!}$

let $k=1$ 

$f_1 = f_0 +hf'(x_0) + \frac{(h)^2}{2}f''(x_0)+....+\frac{(h)^{n+1}f^{(n+1)}(c)}{(n+1)!}$

let $k=2$ 

$f_2 = f_0 +2hf'(x_0) + \frac{(2h)^2}{2}f''(x_0)+....+\frac{(2h)^{n+1}f^{(n+1)}(c)}{(n+1)!}$


Simplifying results in our above formulas.

#### Deriving Difference Formulas : Lagrange and Newton Polynomials.

The general idea is to find $P_n(t)$, so we have

$f(t) =  P_n(t) + E_n(t)$

Now, deriving this, we get

$f'(t) = P_n'(t) + E_n'(t)$
