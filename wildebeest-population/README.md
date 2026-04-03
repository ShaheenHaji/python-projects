# 📐 Euler vs Runge-Kutta — Wildebeest Population in Tanzania

## The challenge
Differential equations describe how things change over time
but most real-world ODEs cannot be solved analytically by hand. 
This project focus on two questions:

(1) How accurately are the two classical numerical methods , Euler 
and 4th-Order Runge-Kutta (RK4)  in solving a logistic growth ODE?

(2) What is the trade-off between step size, computational 
cost, and accuracy for each method?

The wildebeest Population of Serengeti National Park(1960-200) will
serves as the real-world ODE test case, a diologically dataset where the exactly 
analytical solution is known, which make its ideal for benchmarking both method. 

## The mathematical Model 

The population growth of Wildebeest is goverbed by this differential equation: 

$$\frac{dy}{dt} = ry\left(1 - \frac{y}{K}\right), \quad y(0) = y_0$$

Where:
- $y$ = population at time $t$
- $r$ = growth rate (0.08)
- $K$ = carrying capacity (1,300,000)
- $y_0$ = initial population (200,000 in 1960)

### Exact Analytical Solution (used as benchmark):

$$y(t) = \frac{Ky_0e^{rt}}{K + y_0(e^{rt} - 1)}$$

The logistic ODE gives us the true population for every year from 1960 to 2000, 
which will compared with the result both methods against:

If we calculate population of 2000, then
t = 40 (representing the 40-year span from 1960 to 2000)

$$y(40) = \frac{(1{,}300{,}000)(200{,}000)e^{0.08 \times 40}}
{1{,}300{,}000 + 200{,}000(e^{0.08 \times 40} - 1)}$$

$$y(40) = 1{,}061.92 \text{ thousand}$$

## ⚙️ Numerical Methods

### 1️⃣ Euler Method
The simplest numerical approach , it approximates the next value 
using a single slope at the current point:

$$y_{i+1} = y_i + h f(t_i, y_i)$$

Where $h$ is the step size. 

### 2️⃣ 4th-Order Runge-Kutta (RK4)
A far more sophisticated approach , it calculates four 
intermediate slopes per step and combines them in a 
weighted average:

$$y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)$$

Where:
$$k_1 = f(t_n, y_n)$$
$$k_2 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_1\right)$$
$$k_3 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_2\right)$$
$$k_4 = f(t_n + h, y_n + hk_3)$$

