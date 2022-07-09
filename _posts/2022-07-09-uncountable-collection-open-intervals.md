---
layout: post
title: "Cardinality 2: An uncountable collection of disjoint open intervals does not exist"
comments: true
description: "math"
keywords: "analysis"
---


There exists a countable collection of disjoint open intervals. For instance, $$\{(n,n+0.5)\}_{n \in \mathbb N}$$, or 

$$\begin{equation}
\{(1,1.5), (2,2.5), \cdots \}
\end{equation}$$

is an infinite, countable collection of disjoint open intervals.

What's interesting is that one would not be able to find an example of an uncountable collection of disjoint open intervals. Intuitively, what this means is that there isn't enough "room" to fit uncountably many open intervals into $\mathbb R$ without some overlap.[^1] 


To prove this, let $$\{A\}$$ be a collection of disjoint open intervals. Given any $$A$$, let $$x \in A$$.

Since $$A$$ is an open interval, there exists $$\epsilon >0$$ such that $$(x-\epsilon, x+\epsilon) \subseteq A$$.

As $$\mathbb Q$$ is dense in $$\mathbb R$$, there exists a rational number $$r \in $$(x-\epsilon, x+\epsilon)$$.

As $$A$$ is disjoint, it also implies that $$r$$ is distinct for each $$A$$.

We also know that $$\mathbb Q$$ is countable. It follows that there are countably many such $$r$$, which means there are countably many $$A$$.




Footnote:

[^1]: This geometric intuition is provided by [SE](https://math.stackexchange.com/questions/2803350/an-example-of-an-uncountable-collection-of-disjoint-open-intervals-possible) user Noah Schweber.










