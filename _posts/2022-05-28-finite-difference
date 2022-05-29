---
layout: post
title: "Numerical method 1: Finite difference"
comments: true
description: "physics, math"
keywords: "physics, numerical methods"
---


Many physical phenomena can be described by partial differential equations, but the challenge is that these partial derivatives cannot be solved analytically
in general case. One way to solve this issue is by using a numerical method called finite-difference method. It is a method whereby the phenomenon
of interest is discretized using evenly-spaced grid points.

In this method, the derivatives are approximated using finite-difference formulas. Divide the interval $$[a,b]$$ into $$n$$ evenly-spaced subintervals of length $dx$.

<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/fd0.png" width="400"/>

The first and second derivatives of the function can be approximated at grid point $$x_{i}$$, using these formulas respectively:

$$\begin{equation}

\dfrac{dy}{dx} = \dfrac{y_{i+1} - y_{i-1}}{2dx}
\dfrac{d^{2}y}{dx^{2}} = \dfrac{y_{i-1} - 2y_{i} + y_{i+1}}{(dx)^{2}}

\end{equation}$$



Take a sinusoidal wave

$$\begin{equation}

f(x) = \sin (kx)

\end{equation}$$

with wavelength of $$2 \pi$$, 

$$\begin{equation}

\lambda = 2\pi
k = \dfrac{2pi}{\lambda} = \dfrac{2pi}{2pi} = 1

\end{equation}$$

where $$k$$ is the wavenumber. We know that the derivative of $$\sin(kx)$$ is $$k\cos(kx)$$. The code below computes the derivative numerically for interval $$[0, 2 \pi]$$:

```Python
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
#analyt[n-1]=0.

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

The figure above shows that finite-difference approximation is able to simulate the exact solution pretty well. The root mean squared error is 0.18. 
In fact, the estimation error is expected to decrease with decreasing grid increment $$dx$$. The code below calculates the error at decreasing values of $$dx$$:

```Python

# define grid increment
dx = 1
# define number of iterations to perform
iterations = 10 
# list to store our step sizes
dx_size = [] 
# list to store max error for each step size
rmse = [] 

for j in range(iterations):
    # halve the step size
    dx /= 2 
    # store this step size
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





