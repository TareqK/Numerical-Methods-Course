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











