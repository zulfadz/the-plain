---
layout: post
title: "Induction does not imply the validity of infinite case"
comments: true
description: "analysis"
keywords: "math, analysis"
---


Induction is used to show that a statement is valid for each natural number $$n$$. However, induction does not imply the validity of infinite case. Consider a collection of sets $$B_{1}, B_{2}, B_{3}, \cdots$$ where 

$$\begin{align*}
B_1 &= \mathbf{N} = \{1,2,3, \cdots\} \\
B_2 &= \{2,3,4,\cdots\} \\
B_3 &= \{3,4,5,\cdots\}
\end{align*}$$ 

and so on. Clearly, $$B_1 \cap B_2 = B_2.$$ Using induction, it can also be shown that 

$$\begin{align*}
\bigcap_{i=1}^{n} B_{i}=B_n.
\end{align*}.$$ 

Assume the above is true for $$n$$. In the case of $$n+1$$, using associative law, 

$$\begin{align*}
B_1 \cap B_2 \cap  \cdots B_n \cap B_{n+1} =  (B_1 \cap B_2 \cap  \cdots B_n) \cap B_{n+1}
\end{align*}$$ 

which means 

$$\begin{align*}
B_n \cap B_{n+1}
\end{align*}$$ 

which is equal to $$B_{n+1}$$. Therefore $$\bigcap_{i=1}^{n} B_{i}=B_n$$ holds for all $$n \in \mathbf{N}$$.

Nonetheless, don't be misled to think that it also holds for infinite case, because the fact is that

$$\begin{align*} 
\bigcap_{i=1}^{\infty} B_{i}=\emptyset
\end{align*}.$$ 

To see why, suppose there is $$x \in \mathbf{N}$$ which satisfies $$x \in \bigcap_{i=1}^{\infty} B_{i}$$. This means that $$x$$ is an element of all $$B_i$$ in our collection. However, this is a contradiction because $$x$$ is not an element of $$B_{x+1}$$.

Footnote:

[^1]: Inspired by [Understanding Analysis](https://www.amazon.com/Understanding-Analysis-Undergraduate-Texts-Mathematics/dp/1493927116).
