---
layout: post
title: "Infinite collection of infinite sets, which do not overlap, which form natural numbers"
comments: true
description: "analysis"
keywords: "math, analysis"
---

Consider an infinite collection of sets $$B_1, B_2, B_3, \cdots $$ where
1. Each $$B_i$$ contains infinite number of elements.
2. $$B_i \cap B_j = \emptyset $$ for all $$i \neq j$$.

How do we design such collection of sets, such that $$ \cup_{i=1}^{\infty} B_i = \mathbf{N}$$?[^1]

It turns out to be quite straightforward. The key step is to arrange elements of natural numbers $$1,2,3,\cdots $$, in a way that can partion $$\mathbf{N}$$ into an infinite collection of infinite sets. In particular,
we can imagine a square, and arrange the natural numbers like the following:

$$\begin{array}{lccccc}
    1 & 2 & 4 & 7 & 11 & \cdots \\
    3 & 5 & 8 & 12 & \cdots & \\
    6 & 9 & 13 & \cdots & & \\
    10 & 14 & \cdots & & & \\
    15 & \ldots & & & & \\
    \vdots & & & & &
  \end{array}$$

Therefore, each row represents a set containing an infinite elements, and there are infinite number of such rows. The whole "square" forms $$\mathbf{N}$$.

Footnote:

[^1]: Inspired by [Abbot's Understanding Analysis](https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116).
