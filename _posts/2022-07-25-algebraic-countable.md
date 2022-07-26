---
layout: post
title: "Algebraic numbers are countable"
comments: true
description: "math"
keywords: "analysis"
---

A real number is algebraic if it is the root of a polynomial with integer coefficients. For instance $$\sqrt{2}$$ is algebraic because it is the root of $$x^{2} -2 =0$$. 

The question therefore is, how many algebraic numbers are there?

We start with the set of all polynomials of degree $$n$$. These are all polynominals of the form:

$$\begin{align*}
  a_{n} x^{n}+a_{n-1} x^{n-1}+\cdots+a_{1} x+a_{0}=0
  \end{align*}.$$

This set can also be represented by a set of $$n+1$$ tuples of integers coefficient, that is, $$\{(a_{1}, a_{2}, \cdots, a_{n})\}$$. But we know that $$ \lvert \mathbb Z \rvert  = \lvert \mathbb N \rvert$$, therefore, this set can also be represented by $$n+1$$ tuples of natural numbers, that is, $$\{(\alpha_{1}, \alpha_{2}, \cdots, \alpha_{n})\}$$, where $$\alpha_{i} \in \mathbb N$$.

Additionally, consider a special case of the above set, one where the natural coefficients must sum up to less or equal to some $$k \in \mathbb N$$, that is, $$\alpha_{1}+ \alpha_{2}+ \cdots+ \alpha_{n} \leq k$$. The key observation is that there is a finite number of such tuples. This is because each of the member of the tuples must be less than or equal to $$k$$.

Let $$A_{nk}$$ be the roots of this set of polynomials. We know from above that there a finite number of such polynomials. We also know that for a polynomial of degree $$n$$, its number of roots is less than or equal to $$n$$. Therefore, there is a finite number of elements of $$A_{nk}$$.

Next, we generalize $$A_{nk}$$ for all $$k \in \mathbb N$$:

$$\begin{align*}
  A_{n} = \bigcup_{k \geq 1} A_{nk} 
  \end{align*}.$$

But this is an infinite union of finite sets, which is countable. 

Finally, we consider the set of algebraic numbers for all $$n \in \mathbb N$$: 

$$\begin{align*}
  A = \bigcup_{n \geq 1} A_{n} 
  \end{align*}.$$

But this is an infinite union of countable sets, which is countable. Therefore, there are countably many algebraic numbers.











