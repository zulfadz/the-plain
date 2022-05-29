---
layout: post
title: "Numerical method 1: Finite difference"
comments: true
description: "physics, math"
keywords: "physics, numerical methods"
---


Many physical phenomena can be described by partial differential equations. But these derivatives generally cannot be solved analytically. A numerical method called finite-difference method is often used to circumvent the need for analytical solution. 

In this method, the phenomenon of interest is discretized using evenly-spaced grid points. Divide the interval $$[a,b]$$ into $$n$$ evenly-spaced subintervals of length $$dx$$.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/fd0.png" width="400"/>

The first and second derivatives of the function can be approximated at each grid using these formulas respectively:[^1]

$$\begin{equation}

\dfrac{dy}{dx} = \dfrac{y_{i+1} - y_{i-1}}{2dx} \\
\dfrac{d^{2}y}{dx^{2}} = \dfrac{y_{i-1} - 2y_{i} + y_{i+1}}{(dx)^{2}}

\end{equation}$$


### Application to wave simulation

Consider a sinusoidal wave

$$\begin{equation}

f(x) = \sin (kx)

\end{equation}$$

with wavelength of $$2 \pi$$, 

$$\begin{equation}

\lambda = 2\pi \\
k = \dfrac{2\pi}{\lambda} = \dfrac{2\pi}{2\pi} = 1

\end{equation}$$

where $$k$$ is the wavenumber, which is equal to 1 in this case. We know that the derivative of $$\sin(kx)$$ is $$k\cos(kx)$$. The code below[^2] computes the derivative numerically for interval $$[0, 2 \pi]$$ and a grid increment of $$0.2$$:

```python
import numpy as np
from math import *
import matplotlib.pyplot as plt

#initialize wave parameters

#wavenumber
k = 1
#grid increment size
dx = 0.2
# set the grid
x = np.arange(0, 2*np.pi, dx) 
# wave function
f = np.sin(k*x) 
#number of grids
n = len(f) #or len(x)

# initiate numerical and analytical derivatives 
numeric=np.zeros(n)          # numerical derivative
analyt=np.zeros(n)          # analytical derivative

# undertake finite difference method
for i in range (1, n-1):
    numeric[i]=(f[i+1]-f[i-1])/(2*dx)

# undertake exact solution
analyt= k * np.cos(k*x)   
# Exclude boundaries
analyt[0]=0.
analyt[n-1]=0.

# Error (rms) 
rms = np.sqrt(np.mean((numeric-analyt)**2))

plt.figure(figsize = (12, 8))
plt.plot(x, numeric, '--', \
         label = 'Finite difference approximation')
plt.plot(x, analyt, \
         label = 'Exact solution')
plt.xlim([x[1], x[n-2]])
plt.legend()
plt.show()

print(rms)

```
<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/fd1.png" width="400"/>

> RMSE: 0.176221552194

The figure above shows that the finite-difference approximation is able to simulate the exact solution pretty well. The RMSE is 0.18. 
In fact, it can be made more precise by decreasing the grid increment $$dx$$.[^3] The code below plots the RMSE given different values of $$dx$$:

```python

# define initial grid increment
dx = 1
# define number of iterations to perform
iterations = 10 
# list to store our step sizes
dx_size = [] 
# list to store max error for each step size
rmse = [] 

for j in range(iterations):
    # halve the grid increment
    dx /= 2 
    # store this grid increment
    dx_size.append(dx) 
    # compute new grid
    x = np.arange(0, 2 * np.pi, dx) 
    # compute function value at grid
    f = np.sin(x) 
    
    #number of grids
    n = len(f) #or len(x)

    # initiate numerical and analytical derivatives 
    numeric=np.zeros(n)          # numerical derivative
    analyt=np.zeros(n)          # analytical derivative

    # undertake finite difference method
    for i in range (1, n-1):
        numeric[i]=(f[i+1]-f[i-1])/(2*dx)

        # undertake exact solution
        analyt= np.cos(x)   
        # Exclude boundaries
        analyt[0]=0.
        analyt[n-1]=0.
    
        # Compute rmse between 
        # numerical derivative and exact solution
    rmse.append(\
            np.sqrt(np.mean((numeric-analyt)**2)))
    

# produce log-log plot of rmse versus grid increment
plt.figure(figsize = (12, 8))
plt.loglog(dx_size, rmse, 'v')
plt.xlabel('log grid increment')
plt.ylabel('log rmse')
plt.show()

```

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/fd2.png" width="400"/>

As expected, smaller grid increment $$dx$$ (i.e., the step size) results in more precise approximation.

Footnote

[^1]: These formulas are called central difference formulas. Other options are forward difference and backward difference.
[^2]: Coded in Python 3.
[^3]: Or in other words, increasing the number of grids per wavelength.



