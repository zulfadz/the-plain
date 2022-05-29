---
layout: post
title: "Numerical method 2: Finite difference of higher order"
comments: true
description: "physics, math"
keywords: "physics, numerical methods"
---


In the previous post [Numerical method 1: Finite difference](https://zul.rocks/finite-difference), I showed how finite-difference method is useful to approximate derivatives. There, the formula used for second derivatives were based on three-point operators, namely:

$$\begin{equation}

f^{\prime\prime}(x)= \dfrac{f(x+dx)-2 f(x)+f(x-dx)}{dx^2}.

\end{equation}$$

In this post, I illustrate that using a higher-order finite-difference operators can yield an even more precise approximation. The formula for five-point operators is:

$$\begin{equation}
f^{\prime\prime}(x)=\dfrac{-\dfrac{1}{12}f(x-2dx)+\dfrac{4}{3}f(x-dx)-\dfrac{5}{2}f(x) +\dfrac{4}{3}f(x+dx)-\dfrac{1}{12}f(x+2dx)}{dx^2}.
\end{equation}$$

Assume for now that these formulas are valid. The derivation of these formulas are a subject of future posts.

### Application to Gaussian function[^1]

The Gaussian function is defined as follows:

$$\begin{equation} 
f(x)=\dfrac{1}{\sqrt{2 \pi a}}e^{-\dfrac{(x-x_0)^2}{2a}}.
\end{equation}$$

which is visually illustrated in figure below on domain $$[0,10]$$, and Gaussian exponent $$a$$ of 0.25:

```python
# initiate the Gaussian function

#maximum and minimum domain
xmax = 10
xmin=0
#number of samples/grids
n = 100
#grid increment/step size
dx = (xmax-xmin)/(n-1)
#Gaussian exponent
a=0.25
# Center of function
x0 = (xmax - xmin)/2

x=np.linspace(0,xmax,n)   # defining domain

# Gaussian function           
f=(1./sqrt(2*pi*a))*np.exp(-(((x-x0)**2)/(2*a)))

# Plotting of gaussian
plt.figure(figsize=(12,8))
plt.plot(x, f)
plt.title('Gaussian function')
plt.xlabel('x')
plt.xlim((0, xmax))
plt.show()
```
<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/gauss0.png" width="400"/>

The exact solution of the second derivatives of Gaussian function 

$$\begin{equation} 
f^{\prime\prime}(x)= \dfrac{1}{\sqrt{2\pi a}} ( \dfrac{(x-x_0)^2}{a^2}- \dfrac{1}{a} ) \ e^{-\dfrac{(x-x_0)^2}{2a}}
\end{equation}$$

is compared against the three-point operators below:

```python
# three-point operators

# initiate vectors of numerical and analytical derivatives
num3=np.zeros(n)          # numerical derivative
ana=np.zeros(n)          # analytical derivative

# undertake numerical approximation
for i in range (1, n-1):
    num3[i]=(f[i+1] - 2*f[i] + f[i-1])/(dx**2)

# undertake analytical solution
ana=1./sqrt(2*pi*a)*((x-x0)**2/a**2 -1/a)*np.exp(-1/(2*a)*(x-x0)**2)
# Exclude boundaries
ana[0]=0.
ana[n-1]=0.

# Plotting 
plt.figure(figsize = (12, 8))
plt.plot(x, num3, '--', \
         label = '3-point finite difference approximation')
plt.plot(x, ana, \
         label = 'Exact solution')
plt.xlim([x[1], x[n-2]])
plt.legend()
plt.show()
```
<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/gauss1.png" width="400"/>

```python
# Calculate rms error of numerical derivative
rms = np.sqrt(np.mean((num3-ana)**2))
print(rms)
```
> 0.00818613271699

Compare this finding with the approximation using five-point operators:

```python
# five-point operators

# initiate vectors of numerical and analytical derivatives
num5=np.zeros(n)          # numerical derivative


# undertake numerical approximation
for i in range (2, nx-2):
    num5[i] = (-1./12 * f[i - 2] + 4./3  * f[i - 1] - 5./2 * f[i] \
                       +4./3  * f[i + 1] - 1./12  * f[i + 2]) / dx ** 2


# Exclude boundaries for analytical solution
ana[1]=0.
ana[n-2]=0.

# Plotting 
plt.figure(figsize = (12, 8))
plt.plot(x, num5, '--', \
         label = '5-point finite difference approximation')
plt.plot(x, ana, \
         label = 'Exact solution')
plt.xlim([x[2], x[n-3]])
plt.legend()
plt.show()
```
<img src="https://raw.githubusercontent.com/zulfadz/zulfadz.github.io/master/pictures/gauss2.png" width="400"/>

```python
# Calculate rms error of numerical derivative
rms = np.sqrt(np.mean((num5-ana)**2))
print(rms)
```
> 0.000217774088003

The error term declined from 0.008 to 0.0002, which is equivalent to 97% decline.

Footnote

[^1]: Credit to [Computational Seismology: A Practical Introduction](https://www.amazon.com/Computational-Seismology-Introduction-Heiner-Igel/dp/0198717415), [Berkeley Python Numerical Methods](https://pythonnumericalmethods.berkeley.edu/notebooks/Index.html) and [Heiner Igel's course](https://www.coursera.org/learn/computers-waves-simulations) from which I learned and refer to for materials on this topic.



