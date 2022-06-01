---
layout: post
title: "Density of irrational numbers in R"
comments: true
description: "analysis"
keywords: "math, analysis"
---


Assume the following is true:

> **Density of Q in R** For every two real numbers $$a$$ and $$b$$ with $$a < b$$, there exists a rational number $$r$$ satisfying $$a <r<b$$.

This is a well-known and proven theorem in analysis. What's interesting -- and I only realize this today[^1] -- is that the same statement also applies for irrational number! Namely:

> For every two real numbers $$a$$ and $$b$$ with $$a < b$$, there exists an irrational number $$t$$ satisfying $$a <t<b$$.

*Proof*

We only need to know that $$\sqrt{2}$$ is irrational. Take real numbers $$a- \sqrt{2}$$ and $$b - \sqrt{2}$$.
By the original theorem, there exists a rational number $$r$$ satisfying $$a- \sqrt{2} < r< b - \sqrt{2}$$.
Rearranging the inequality, $$a < r + \sqrt{2} < b$$. We are done.


Footnote:

[^1]: Abbott's exercise 1.4.5.
