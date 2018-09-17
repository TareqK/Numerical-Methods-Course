# Chapter 1 : Review of Calculus, Errors and Rounding

## Review of Calculus

### Continuity

A function f(x) is continuous on [a,b] if f(x) &isin; C[a,b] and f(x) &isin; C`[a,b], that is, 
f(x) and its derivative are continous on [a,b].

In laymans terms, a function is continous over [a,b] if there are no points where there are problems, such as division by zero, or the function is not a piecewise function that does not cover every point in [a,b]

---

### Increasing and Decreasing Functions
 
A function is classified as increasing or decreasing depending on its derivative. 

- if f`(x) > 0 then the function is increasing
- if f`(x) < 0 then the function is decreasing

if f`(x) = 0, then that is called an inflection or critical point.

if f(x) is continuous on [a,b] then f has an absolute **upper bound** = M and an absolute **lower bound** = m, such that :

$$ m \le f(x) \le M \forall x \in [a,b] $$

---

### Initial Value Theorem

Lets say  that f &isin; [a,b], L is between  f(a),f(b) &exist; c &isin; [a,b] such that f(c) = L

---

### Bolzano Theorem

let us assume that :

1. f &isin; C[a,b]
2. f(a).f(b) &lt; 0

Then &exist; c in (a,b) such that f(c) = 0.

x = c is a root(a zero) for f(x), and x = c is a solution for the equasion.

---

### Mean Value Theorem

if f &isin; C[a,b] and f\`&isin; C(a,b), then &exist; c &isin; (a,b) such that  : 

$$ f`(c) = \frac{f(b) - f(a)}{b-a} $$

alternatively, this can be expressed as 

$$ |f(b) - f(a)| = |f`(c)| |(b-a)| $$

Recall that :

$$ | x \pm y | \le |x|+ |y| $$

---

#### Rolle's Theorem

Rolle's Theorem is a special case of the MVT, which states :
 
>If f is continuos and differentiable on (a,b) and if f(a) &le; f(b) ,
then &exist; c &isin; (a,b) such that f`(c) = 0 .

In simple terms, if f is generally decreasing on an open interval, then there is a critical point in that interval.

---

### Taylor Series 

The Taylor Series/ Taylor Expansion is a way to express a function that isn't very "nice" as a series of polynomials that can be used to express the function. In more technical terms, the taylor series can be formally defined as follows : 

> Given f(x) and a center x = a, then the taylor expantion series for f(x) about x = a is given by :

$$ f(x) = f(a) + f`(a)(x-a) + \frac{f``(a)(x-a)}{2!} + ....+ \frac{f^{n}(a)(x-a)^{n}}{n!}$$

Which is used to approximate f(x) when x is close to a. 

The error of this approximation is given by :   

$$ E(x) = \frac{f^{n+1}(c)(x-a)^{n+1}}{(n+1)!}$$

where c is a number between x and a.

---

## Errors and Rounding

### Significant Digits

A digit is said to be significant when a change in its value changes the number. To find out the number of significant digits in a number, start counting from the the first non-zero number on the left. For example, 

> 0.0012341

has 5 significant digits, and

> 1200

has 4 significant digits. 

---

### Sources of Errors

There are 2 sources of errors :

1. Round-off Error : an error when a number is approximated by another number.
2. Truncation Error : an error when a function is approximated by another function.

The reason we have round-off error is because computers use **finite digit arithematic**. There are only a finite number of digits a computer can handle at a time. Numbers in computers are represented in **floating point representation**. Normalized floating point representation is a special form of this, where all the **significant digits** are to the right of the decimal point.

---

#### Floating Point Representation

FPR is a way of representing numbers such that we reduce the number of uneeded digits/zeros. Basically, lets say we have the number

> 0.0023141

then we can represent this as 

> 2.3141 * 10<sup>-3</sup>

It is called floating point because we are moving the decimal point around. Normalized floating point is simply rewriting the number as 

> 0.dddddddd * 10<sup>n</sup>

where the first digit is non-zero.

---

### Round-off

There are 2 types of round-off :

1. Chopping --> simple cut off after a certain amount of significant digits.

2. Rounding --> estimating using the last significant digit, such that if it is &ge; 5, then we add one, otherwise, we add zero.
 
---

### Propagation of Error

given that

$$ p = \hat{p} + E_{p}$$

and

$$ q =\hat{q} + E_{q}$$

then

$$ p + q =\hat{p} + \hat{q} + E_{p} + E_{q}$$

That is to say, error may be increased in operations. 


---

### Order Of Approximation

Let us say that we are approximating e<sup>h</sup> using the taylor expantion : 

$$ e^{h} = 1 + h + \frac{h^2}{2}$$ 

Then we know that the error is given by 

$$ E = \frac{f^3(c)h^3}{6} \to \frac{e^ch^3}{6}$$

so we can say 

$$ E \approx ch^3 $$ 

we can express this error by saying :

$$ O(h^3)$$

That is to say, the error is about some constant between 0 and h times h<sup>3</sup>.

Formally, we say :

$$ f(h) = p(h) + O(h^n )$$

then 

$$ f(h) \approx p(h) $$

with 

$$E \approx C*h^n$$

---
#### Determening The Order Of Approximation In Operations. 

Say that we have 

$$ f(h) = p(h) + O(h^n )$$

$$ g(h) = k(h) + O(h^m )$$

Then

$$ f(h)+ g(h) =  p(h) + k(h)+ O(h^r)$$

where 

1. r = min [n,m]
2. h<sup>l</sup> + O(h<sup>r</sup>) = O(h<sup>r</sup>), if l &ge; r

---


