<!-- Required extensions:  mathjax -->
# Chapter 2 : How To Solve An Equation Numerically

There are six(actually five, but one of them is a special case of another) main methods we will be using to solve equations numerically :

1. Bisection Method
2. False-Position(Regula-Falsi) Method
3. Fixed Point Iteration
4. Newtons(Newton-Raphson) Method
5. The Seacant Method
6. Accelarated Newton Method

----

## Bisection Method

Recall 

>if f &isin; c[a,b] and f(a).f(b) &lt; 0,
>&exist; at least one r &isin; c(a,b) such that  
>f(r) = 0.

By this principle, we know that if the sign of f changes over the domain, then we know that there is a root. We can find this root if we keep halving the interval, until we eventually zero in on the root.

$$f \in [a,b]; [a,b] = [a_0,b_0]$$
$$f(a_0)*f(b_0) \lt 0 $$

Then the first iteration is $ C_0 = \frac{a_0+b_0}{2} \to f(C_0)$

if $f(C_0) \lt 0  \to [a_1,b_1] = [a_0,C_0]$

and the second iteration is $C_1 = \frac{a_1,b_1}{2} $

The general formula for calculating the nth iteration using the bisection method is 

$$ C_n = \frac{a_n,b_n}{2} $$

And the **upper bound of error** for the bisection method is given by : 

$$ \frac{b-a}{2^{n+1}}$$

There are 4 ways we stop when using the bisection method : 

1. We reach the desired number of iterations.
2. We have reached a certain **accuracy**.

    The accuracy in the bisection method is given by :

    $$ |C_n - C_{n_1}| \lt \epsilon $$

    That is to say, the accuracy is the difference between the last 2           
    successive iterations. 

3. Stop when $f(C_n) \lt \epsilon $.
4. Stop when $ \frac{|C_n - C_{n-1}|}{C_n} \le \epsilon$.

The main advantage of the Bisection method is that C always converges, and it always converges to the true root. The main disadvantage is that it is really slow, ie, it takes a lot of time and iterations to get within a reasonable degree of error of the root.


### Bisection Method Proof

Prove that $\lim_{n\to\infty} C_n = r$

$b_1 - a_1 = \frac{b-a}{2}$ --> their length is equal when we bisect

$b_2 - a_2 = \frac{b_1-a_1}{2} = \frac{b-a}{2^2}$

$b_3 - a_3 = \frac{b_2-a_2}{2} = \frac{b-a}{2^3}$

Then we can say that

$b_n - a_n = \frac{b-a}{2^n}$

and

$|r-C_n| \lt \frac{b_n-a_n}{2}$ --> the difference between the real root and the iteration is less than the length.

and

$ 0 \lt |r-C_n| \lt \frac{b-a}{2^{n+1}}$ --> the diffrence is less than the upper bound of error and bigger than 0.

then by the sandwich theorem, since $\lim_{n\to\infty}\frac{b-a}{2^{n+1}} = 0$

and $\lim_{n\to\infty} = 0$,

then $\lim_{n\to\infty} r-C_n = 0$,

therefore, $ r = \lim_{n\to\infty}C_n$.

### Calculating The Number Of Iterations

since we know that the upper bound for the error is given by : 

$$ \frac{b-a}{2^{n+1}}$$

and that the upper bound of the error is higher than the real error, then we can say $\frac{b-a}{2^{n+1}} \lt \frac{\epsilon}{1}$.

$\frac{2^{n+1}}{b-a} \gt \frac{1}{\epsilon} = 2^{n+1} \gt \frac{b-a}{\epsilon}$. 

take ln of both sides $ln(2^{n+1}) \gt ln(\frac{b-a}{\epsilon})$

--> $(n+1)ln(2) \gt ln(\frac{b-a}{\epsilon}) $
--> $n+1 \gt \frac{ln(\frac{b-a}{\epsilon})}{\ln(2)}$
--> $ n \gt \frac{ln(\frac{b-a}{\epsilon})}{\ln(2)} -1$

Generally then, to find the **minimum** number of iterations for the bisection method to reach a certain accuracy, we use the inequality 

$$ n \gt \frac{ln(\frac{b-a}{\epsilon})}{\ln(2)} -1$$

or 

$$ n \gt \log_2(\frac{b-a}{\epsilon}) -1$$

---

## Converting To f(x) = 0

Eg Estimate $\root^4 \of 7$ in the range [1,2]

let $x = \root^4 \of 7$ 

$ x^4 = 7 $

$ x^4 -7 = 0$

$ f(x) = x^4 -7$

Always convert to the form f(x) = 0 when attempting to solve numerical methods.

Eg Find the intersection point between $y = e^x, y=x^2 + 5 $

let $ y = y$

$ e^x = x^2 +5$

$ e^x -x^2 -5 =0 $

$ f(x) = e^x -x^2 -5$

Eg $p(x) =e^x + x^2 - \root \of x +1$ is a profit function. Estimate the number of units that leads to maximum profit in [a,b]

$ p`(x) = e^x +2x - \frac{1}{(2)({\root \of x})}$

and find $p`(x) = 0$
---

## False Position Method

It is similar to bisection, and needs 

$f(x) = 0, [a,b]$

where $f(a)*f(b) \lt 0$

But the value of $C_n$ is not of $f(\frac{b_n-a_n}{2})$

It relies on a geometric method using the **seacant line** between $a_n,b_n$

![seacant](https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/False_position_method.svg/351px-False_position_method.svg.png)

Mathemtically, this is expressed as :

$$ C_n = b_n- \frac{f(b_n)(b_n-a_n)}{f(b_n)-f(a_n)}$$

then $C_0 = b_0 -\frac{f(b_0)(b_0-a_0)}{f(b_0)-f(a_0)}, f(C_0)$

and $C_1 = b_1 - \frac{f(b_1)(b_1-a_1)}{f(b_1)-f(a_1)}, f(C_1)$

so on and so forth.

The slope of the resultant line is given by 

$$S = \frac{f(b_0)-f(a_0)}{b_0-a_0}$$

then   $S = \frac{f(b_0)-f(a_0)}{b_0-a_0}  = \frac{0-f(b_0)}{C_0-b_0}$

$ \frac{C_0-b_0}{-f(b_0)} = \frac{b_0-a_0}{f(b_0)-f(a_0)}$


$ C_0-b_0 = \frac{f(b_0)(b_0-a_0)}{f(b_0)-f(a_0)} $

$C_0 = b_0 -\frac{f(b_0)(b_0-a_0)}{f(b_0)-f(a_0)}$

We determine the next [a,b] depending on the sign of $C_n$

if $C_n \lt 0$, then $[a_{n+1},b_{n+1}] = [C_0,b_n]$, given that $f(a) \lt 0$and $f(b) \gt 0$ 

This method always converges to the true root, but it is very slow as well.


---

## Fixed Point Iteration

Say we have a function $f(x)$ with root $p$.  The general idea is that we have some function taken from $f(x)$, called $g(x)$. We used the **fixed point** of $g(x)$, which will be the roots of $f(x)$. Not all functions derived are suitable however.

### What is a Fixed Point?

$x=p$ is a fixed point of $g(x)$ if $g(p)=p$

For example, given the function $g(x) =  x^2$, then $0,1$ are fixed points of $g(x)$. For more complex functions, we solve $g(x) = x$, since we want all images of x that are equal to x. so in this case :

$x^2 = x$

$x(1-x) = 0 $

$x=0,1$

Geomertrically speaking, the fixed points of $g(x)$ are the intersection points between $g(x)$ and $y=x$, for example,for $g(x) = 4x - x^2 $  : 

![intersect](https://d2gne97vdumgn3.cloudfront.net/api/file/P7AhayfOQj6gs7y9o9KB)

In this case, $0,3$ are fixed points of $4x- x^2$

---

### Where do we get g(x) from?


We need to bring $f(x) = 0$ to the form $x-g(x) = 0 $, for example $f(x) = x^2 -5x +6 = 0$ becomes $x^2 = 5x -6 \to x = \root \of{5x - 6} \to x-\root \of{5x-6}$, so in this case $g(x) = \root \of{5x-6} $. We can extract more than one $g(x)$ from $f(x)$, for example, we can extract $x= \frac{x^2+6}{5}$ by reearanging as well.

We can do this reerangement because we assumed that $f(x) = 0$

---

### Why are Fixed Points of g(x) Roots of f(x)?

let $g(p) = p$

then $p-g(p) = 0$

but $p-g(p) = f(p)$

and since $p-g(p)=0$, then $p-g(p)=f(p)=0$ and $p$ is a root of $f(x)$

---

FPI is a method where we find approximations of the fixed points of $g(x)$. we need : 

1. $g(x)$.
2. $p_0$, or the initial value/guess value.


The formula of FPI is given by :

$$p_{n+1} = g(p_n)$$

then, $p_1=g(p_0)$, $p_2=g(p_1)$, so on and so forth.

If the sequence $p_0,p_1,p_2,...p_n$ convrges to some $p$, then $p$ is a fixed point of $g(x)$, and a root of $f(x)$

This can be proven as follows :

$\lim_{n \to \infty} p_n = g(p_{n-1})$

$p_\infty = g(p_{\infty-1}) = g(p_\infty)$







---