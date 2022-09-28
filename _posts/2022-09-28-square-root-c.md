---
layout: post
title: "Sequence that converges to a square root of c"
comments: true
description: "math"
keywords: "analysis"
---

> Find a sequence $$(x_{n})$$ that converges to $$\sqrt{c}$$, where $$c \geq 0.$$

A theorem that is helpful when looking for this sequence is the Monotone Convergence Theorem:

> If a sequence is monotone (increasing or decreasing), and it is bounded, then it converges to some limit.

To show this, consider the sequence $$(x_{n})$$ such that $$x_{1}=c$$, and $$x_{n+1} = \frac{1}{2}(x_{n} + \frac{c}{x_{n}}).$$

Note that $$x_{n}>0$$ for all $$n.$$ So it is bounded. Now, I need to only show that the sequence is monotone decreasing:

$$\begin{align*}
x_{n} - x_{n+1} &= x_{n} - \frac{1}{2}(x_{n} + \frac{c}{x_{n}}) \\
& = \frac{x_{n}}{2}-\frac{c}{2x_{n}}\\
&= \frac{1}{2}\frac{(x^{2}_{n}-c)}{x_{n}}
\end{align*}.$$

Note that

$$\begin{align*}
x_{n}^{2}-c &= \frac{1}{4}(x_{n-1} + \frac{c}{x_{n-1}})^{2}-c \\
&= \frac{1}{4}x_{n-1}^{2} -\frac{1}{2}c + \frac{1}{4}c^{2}/x_{n-1}^{2} \\
&= \frac{1}{4}(x_{n-1} - \frac{c}{x_{n-1}})^{2} \\
&\geq 0
\end{align*}.$$

Thus, $$x_{n} - x_{n+1} \geq 0$$ hence it's monotone decreasing. It follows that the limit of the sequence exists. Set $$x$$ to be the limit. Then,

$$\begin{align*}
x &= \frac{1}{2}(x + \frac{c}{x}) \iff 2x = x+\frac{c}{x} \iff x^{2} = c
\end{align*}.$$

