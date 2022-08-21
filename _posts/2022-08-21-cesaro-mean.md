---
layout: post
title: "Cesaro means"
comments: true
description: "math"
keywords: "analysis"
---

There is this cool problem from Abbott section 2.3 called "Cesaro means" which states that:

> Show that if $(x_{n})$ is a convergent sequence, then the sequence given by the averages $$y_{n} = \frac{x_{1} +x_{2} +···+x_{n}}{n}$$ also converges to the same limit.

Initially I thought it was a trivial case of algebraic limit theorem, but it turned out to be more interesting than that. 

Suppose $$x_{n} \to l$$. Then, there exists $$N_{1}$$ such that $$|x_{n}-l|<\epsilon$$ for all $$n> N_{1}$$. Note that

$$\begin{align*}
|y_{n}-l| &=  |\frac{x_{1} +x_{2} +\cdots+x_{N_{1}}+\cdots+x_{n}-nl}{n}|\\
&\leq \frac{1}{n}(|x_{1}-l|+|x_{2}-l|+\cdots + |x_{N_{1}}-l|+\cdots+|x_{n}-l|) \text{ by triangle inequality}.
\end{align*}$$

Select $$M > \max\{|x_{n}-l||\forall n \in \mathbb N\}$$ and $$\epsilon^{\prime} = \epsilon/2$$. Hence $$M>\epsilon^{\prime}$$. It follows that

$$\begin{align*}
|y_{n}-l| &\leq \frac{1}{n}(M+M+\cdots + \epsilon^{\prime}+\cdots+\epsilon^{\prime}) \\
&\leq \frac{1}{n}(N_{1}M+(n-N_{1})\epsilon^{\prime}) \\
&=\frac{N_{1}M}{n}-\frac{N_{1}\epsilon^{\prime}}{n}+\epsilon^{\prime} \\
&=\frac{N_{1}(M-\epsilon^{\prime})}{n} +\epsilon^{\prime}.
\end{align*}$$

Select $$N_{2}$$ such that for all $$n > N$$, $$0<\frac{N_{1}(M-\epsilon^{\prime})}{n}<\epsilon^{\prime}$$. Therefore, for all $$n > \max\{N_{1},N_{2}\}$$,

$$\begin{align*}
|y_{n}-l| &=\frac{N_{1}(M-\epsilon^{\prime})}{n} +\epsilon^{\prime} \\
&\leq \epsilon^{\prime} + \epsilon^{\prime} = 2\epsilon^{\prime} = \epsilon,
\end{align*}$$

hence $$y_{n} \to l$$.


