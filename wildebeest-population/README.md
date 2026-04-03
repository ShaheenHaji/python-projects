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

This gives us the ground truth to measure both methods against:
$$y(40) = 1{,}061.92 \text{ thousand}$$
