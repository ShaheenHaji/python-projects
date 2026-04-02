# 🌍 Global CO2 Emission Quantitative Analysis
## 📌 The Problem
Gradient descent is a fundamental optimization algorithm in machine 
learning but how well does it perform when applied to real-world 
environmental data with complex, non-linear growth patterns?

This project uses global CO2 emissions (1940–2024) as a case study 
to test gradient descent's ability to fit and optimize three 
mathematical models of increasing complexity: Linear, Quadratic, 
and Exponential.

## 🎯 Objective
To evaluate gradient descent as an optimization method across 
different model types, using CO2 emissions data as the testing 
ground — and determine which model it fits most effectively.

## Method: Gradient Descent
Rather than using built-in curve-fitting libraries, this project 
manually implements gradient descent to iteratively minimize 
prediction error (MAE loss) across 1000+ training epochs.

The gradient descent equation used:

$$\theta = \theta - lr * \frac{d}{d\theta}J(\theta)$$
Where:
- $\theta$ = model parameters $(w, b)$
- $lr$ = learning rate
- $J(\theta)$ = loss function (MAE)
__Loss Function (MAE):__
$$J(w,b) = \frac{1}{m}\sum_{i=1}^{m}|y_i - \hat{y}_i|$$


Models Applied

**Linear:**
$$\hat{y} = wx + b$$

**Quadratic:**
$$\hat{y} = w_1x^2 + w_2x + b$$

**Exponential:**
$$\hat{y} = b \cdot e^{wx}$$

## Programming 
- Python 3
