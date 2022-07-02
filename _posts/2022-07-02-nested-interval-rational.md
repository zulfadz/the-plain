---
layout: post
title: "Nested Interval Property doesn't work for rationals"
comments: true
description: "math"
keywords: "analysis"
---


Nested interval property states that

> For each $n \in \mathbf{N}$, assume we are given closed intervals $I_n = [a_{n},b_{n}]$. Assume that these intervals are nested, $I_n \supseteq I_{n+1}$. Then it follows that the this nested sequence has a nonempty intersection. Namely, $\bigcap_{n=1}^{\infty} I_{n} \neq \emptyset$.

The above can be shown to be true for real numbers. But the same cannot be said for rational numbers. To see this, consider a nested sequence of closed intervals around $\pi$. Namely $[3,4],[3.1,3.2],[3.12,3.13],...,$. While the infinite intersection is nonempty, the only element it includes is not rational.

