# Chapter 9 : Ordinary Differential Equations

## How to solve an IVP
1. Eulers Method
2. Taylor's Method of Order 2 
3. Taylor's Method of Order 3
4. Taylor's Method of Order 4
5. Heun's Method
6. Runge-Kutta  of order 4
note that unless otherwise specified, $h= \frac{t_n - t_0}{n}$, $y_0 = f(t_0)$
### Eulers Method

$$y_{k+1} = y_k + hf(t_k,y_k) \quad, E_n = \frac{h^2}{2}y''(c) \quad, E[y(b),h] = \frac{(b-a)h}{2}y''(c)\quad,  k=0,....,n $$

### Taylor's Method of Order 2

$$y_{k+1} = y_k + h(f(t_k,y_k) +\frac{f`(t_k,y_k)h}{2!})+ \quad, E_n = \frac{h^2}{2}y'(c) \quad, E[y(b),h] = \frac{(b-a)h}{2}y'(c)\quad,  k=0,....,n $$

### Heun's Method

$$y_{k+1} = y_k + \frac{h}{2}[f(t_k,y_k) + f(t_{k+1},y_k+hf(t_k,y_k))]$$

### Runge-Kytta of Order 4
$f_1 = f(t_k,y_k)$

$f_2 = f(t_k+\frac{h}{2}, y_k+\frac{h}{2}f_1)$

$f_3 = f(t_k+\frac{h}{2}, y_k+\frac{h}{2}f_2)$

$f_4 = f(t_{k+1},y_k + hf_3)$

$$y_{k+1} = y_k +\frac{h}{6}[f_1 + 2f_2 +2f_3 +f_4]$$

