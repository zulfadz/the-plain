---
layout: post
title: "Units digit of sum 1! + 2! + ... + 8988!"
comments: true
description: "counting"
keywords: "math, probability"
---


Consider this problem[^1]:

```
What is the unit digit of the sum 1! + 2! + ... + 8988!?
```

$1! = 1$ has a unit digit of $1$, $2!=2$ has a unit digit of $2$, $3!=6$ has a unit digit of 6, $4!=24$ has a unit digit of $4$, and $5!=120$ has a unit digit of $0$.
But note that $n!$ for each $n \geq 5$ is a multiple of $5.2=10$. Any integer that is multiple of 10 yields a unit digit of zero. 
Therefore, it suffices to simply consider the case of $1! + 2!+3!+4!$, which is equal to $33$, implying a unit digit of $3$.

---
[^1]: Inspired by [this](https://www.amazon.com/Introduction-Counting-Probability-Textbook-Solutions/dp/B0083C7A64)
