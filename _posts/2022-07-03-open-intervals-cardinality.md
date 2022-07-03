---
layout: post
title: "Cardinality 1: Any open interval (a,b) has the same cardinality as R"
comments: true
description: "math"
keywords: "analysis"
---


The big picture is to first show that $$\mathbb R$$ has the same cardinality as $$(-1,1)$$ (or any examples of open interval). Once established, we find a bijection mapping  $$(-1,1)$$ to a general case $$(a,b).$$ 

$$\begin{align*}
\mathbb R \xrightarrow{f^{-1}} (-1, 1) \xrightarrow{g} (a,b).
\end{align*}$$

Since the composition of two bijections is a bijection, having $$g \circ f^{-1}: \mathbb R \to (a,b)$$ will complete the proof.

For the first step, note that $$f: (-1,1) \to \mathbb R$$ is given by 


$$\begin{align*}
f(x) = \dfrac{x}{x^{2}-1}.
\end{align*}$$ 

As 

$$\begin{align*}
f^{\prime} &= -\dfrac{1+x^2}{(x^2-1)^{2}} \\
&<0,
\end{align*}$$

we know that it is strictly decreasing on $$(-1,1)$$ and continuous, which implies it is injective.[^1] Moreover since, 

$$\begin{align*}
\lim_{x \to -1} \dfrac{x}{x^{2}-1} = -\infty
\end{align*}$$

and 

$$\begin{align*}
\lim_{x \to 1} \dfrac{x}{x^{2}-1} = \infty,
\end{align*}$$

we know it is surjective.[^2]

The next step is to find $$g$$, which can be simply done by linearly transforming $$(-1,1)$$ to $$(a,b)$$ as follows:

1. First, apply the map $$x \mapsto x(b-a)/2$$ so that the endpoints are scaled by $$(b-a)/2$$. The resulting image interval is $$(\dfrac{a-b}{2}, \dfrac{b-a}{2})$$.
2. Next, shift the endpoints to $$a$$ and $$b$$ by mapping $$x \mapsto x + \dfrac{a+b}{2}$$. The image interval is $$(a,b)$$.

Thus $$g: (-1,1) \to (a,b)$$ is given by 


$$\begin{align*}
g(x) = \dfrac{(a+b) + x(b-a)}{2}.
\end{align*}$$ 

As $$g$$ is linear and $$g^{\prime}(x) = \dfrac{b-a}{2}>0$$, it is strictly increasing on $$(-1,1)$$ and continuous. By the same argument, $$g$$ is a bijection.

Footnote:

[^1]: By [Mean Value Theorem](https://en.wikipedia.org/wiki/Mean_value_theorem)

[^2]: By [Intermediate Value Theorem](https://en.wikipedia.org/wiki/Intermediate_value_theorem)








