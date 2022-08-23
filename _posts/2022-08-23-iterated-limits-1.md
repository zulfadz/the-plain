---
layout: post
title: "Curious case of iterated limits"
comments: true
description: "math"
keywords: "analysis"
---

Consider a doubly indexed array $$a_{mn}$$ where $$m, n \in \mathbb N$$, which can be represented as follows:

$$\begin{array}{llllll}a_{11} & a_{12} & \cdots & \cdots & \cdots \\ a_{21} & a_{22} & \cdots & \cdots & \\ \vdots & & & & \end{array}$$

What can we say about the limit when $$n,m \to \infty$$. There are three ways to show this. First, is to fix $$n$$, find the limit when $$m \to \infty$$, before considering $$n \to \infty$$

$$\begin{align*}
\lim_{n \to \infty} (\lim_{m \to \infty} a_{mn})
\end{align*}.$$

Second, is to fix $$m$$, find the limit when $$n \to \infty$$, before considering $$m \to \infty$$

$$\begin{align*}
\lim_{m \to \infty} (\lim_{n \to \infty} a_{mn})
\end{align*}.$$

These two are called iterated limits. The third approach is to simply consider both $$m,n$$ at the same time. That is, define $$\lim_{m,n \to \infty} a_{mn} =a$$ as for all $$\epsilon >0$$ there exists an $$N \in \mathbb N$$ such that if both $$m,n \geq N$$, then $$\rvert a_{mn} −a \lvert <\epsilon$$. We call this the double limit.

Interestingly, the existence of double limit does not imply the existence of iterated limits. For instance, consider the array

$$\begin{array}{llllll}(-1/1) +(-1/1)& (-1/2)+(1/1) & (-1/3)+(-1/1) & \cdots & (-1/n)+((-1)^{n}/1) & \cdots \\ (1/1)+(-1/2) & (1/2)+(1/2) & (1/3)+(-1/2)& \cdots & (1/n)+((-1)^{n}/2) & \cdots\\ (-1/1)+(-1/3) & (-1/2)+(1/3) & (-1/3)+(1/3) & \cdots & (-1/n)+((-1)^{n}/3) & \cdots\\ \vdots & & & & & \end{array}$$

Indexing the rows by $m$ and the columns by $n$, this array can be represented by the sequence $$(\frac{(-1)^{m}}{n}+\frac{(-1)^{n}}{m})$$. Clearly, when both $$m,n \to \infty$$, the limit of the sequence is zero.


How about iterated limits? Fixing $$m$$ and considering $$n \to \infty$$, we find that there is no limit. Similarly if we fix $$n$$ and consider $$m \to \infty$$.

Similarly, the existence of iterated limits does not imply the existence of double limit. For example, consider $$a_{mn} =mn/(m^{2} +n^{2})$$. Fixing $$m$$, $$\lvert mn/(m^{2} +n^{2}) \rvert \leq \lvert mn/(n^{2}) \rvert = \lvert m/n \rvert$$, which goes to zero as $$n \to \infty$$. Therefore, 

$$\begin{align*}
\lim_{m \to \infty} (\lim_{n \to \infty} a_{mn}) = \lim_{m \to \infty} 0 =0.
\end{align*}$$

Meanwhile, double limit does not exist in this case -- because we can find different limits depending on how $$n$$ is defined relative to $$m$$. For instance, if $$n=m$$, then $$a_{mn}=m^{2}/2m^{2}=1/2$$. Meanwhile if $$n = 2m$$, then $$2m^{2}/5m^{2}=2/5$$. This contradicts the unique property of limit.






