---
layout: post
title: "Given a set B of positive real numbers. The sum of any finite subset of B is 2 or less. B must be countable"
comments: true
description: "math"
keywords: "analysis"
---

Today, I found this very cool exercise from Abbott:

> Let $$B$$ be a set of positive real numbers with the property that adding together any finite subset of elements from $B$ always gives a sum of 2 or less. Show $B$ must be finite or countable.

To re-phrase, what the statement is saying is that if we take any finite subset of $$B$$, the elements of the subset will always add up to 2 or less.

Intuitively, the implication of this condition is that $$B$$ can be decomposed into countably many finite subsets. Together with Theorem 1.5.8 in Abbott:

> If $$A_{n}$$ is a countable set for each $$n \in \mathbb N$$, then $$\bigcup_{n \in \mathbb N} An $$ is countable,

we can establish that $$B$$ is countable.

To see this argument more clearly[^1], for each $$n \in \mathbb N $$ define 

$$\begin{align*}
A_{n}= \{x \in B \vert x \geq \frac{2}{n}  \} \subseteq B
\end{align*}.$$

Each $$A_{n}$$ is finite because the number of distinct elements cannot exceed $n$, otherwise the sum of the elements would be greater than 2. 

Note that 
$$\begin{align*}
B = \bigcup_{n \in \mathbb N} A_{i}.
\end{align*}$$

But this means that $$B$$ is a union of countably many finite sets. By Theorem 1.5.8, $$B$$ is countable.

Footnote:

[^1]: While several proof variations can be shown to prove this statement, I found this [argument](https://math.stackexchange.com/questions/1724016/countability-of-set-of-positive-reals-with-bounded-sum-for-all-finite-subsets) by Jose Carlos Santos to be succinct and intuitive.










