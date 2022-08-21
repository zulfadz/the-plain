---
layout: post
title: "Cesaro means"
comments: true
description: "math"
keywords: "analysis"
---

There is this cool problem from Abbott section 2.3 called "Cesaro means" which states that:

> Show that if $$(x_{n})$$ is a convergent sequence, then the sequence given by the averages $$y_{n} = \dfrac{x_{1} +x_{2} +···+x_{n}}{n}$$ also converges to the same limit.

Initially I thought it was a trivial case of algebraic limit theorem, but it turned out to be more interesting than that. 

Suppose $$x_{n} \to l$$. Then, there exists $$N_{1}$$ such that $$\lvert x_{n}-l\rvert<\epsilon$$ for all $$n> N_{1}$$. Note that

$$\begin{align*}
\lvert y_{n}-l \rvert &=\lvert \frac{x_{1} +x_{2} +\cdots+x_{N_{1}}+\cdots+x_{n}}{n}-l \rvert\\
&=  \lvert \frac{x_{1} +x_{2} +\cdots+x_{N_{1}}+\cdots+x_{n}-nl}{n} \rvert \\
&\leq \frac{1}{n}(\rvert x_{1}-l \lvert + \lvert x_{2}-l \rvert +\cdots + \lvert x_{N_{1}}-l \rvert +\cdots+ \lvert x_{n}-l \rvert) \text{ by triangle inequality}.
\end{align*}$$

Select $$M > \max\{\lvert x_{n}-l \rvert : \forall n \in \mathbb N\}$$ and $$\epsilon^{\prime} = \epsilon/2$$. Hence $$M>\epsilon^{\prime}$$. It follows that

$$\begin{align*}
\lvert y_{n}-l \rvert &\leq \frac{1}{n}(M+M+\cdots + \epsilon^{\prime}+\cdots+\epsilon^{\prime}) \\
&\leq \frac{1}{n}(N_{1}M+(n-N_{1})\epsilon^{\prime}) \\
&=\frac{N_{1}M}{n}-\frac{N_{1}\epsilon^{\prime}}{n}+\epsilon^{\prime} \\
&=\frac{N_{1}(M-\epsilon^{\prime})}{n} +\epsilon^{\prime}.
\end{align*}$$

Select $$N_{2}$$ such that for all $$n > N_{2}$$, $$0<\frac{N_{1}(M-\epsilon^{\prime})}{n}<\epsilon^{\prime}$$. Therefore, for all $$n > \max\{N_{1},N_{2}\}$$,

$$\begin{align*}
\vert y_{n}-l \rvert &=\frac{N_{1}(M-\epsilon^{\prime})}{n} +\epsilon^{\prime} \\
&< \epsilon^{\prime} + \epsilon^{\prime} = 2\epsilon^{\prime} = \epsilon,
\end{align*}$$

hence $$y_{n} \to l$$.


