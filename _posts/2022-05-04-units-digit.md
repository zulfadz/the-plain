---
layout: post
title: "Units digit of sum 1! + 2! + ... + 8988!"
comments: true
description: "counting"
keywords: "math, probability"
---


Consider this problem[^1]:

```
What is the units digit of the sum 1! + 2! + ... + 8988!?
```

1. 1! has units digit of 1
2. 2! has units digit of 2 
3. 3! has units digit of 6 
4. 4! = 24 has units digit of 4
5. 5! = 120 has units digit of 0.

The key observation is that for each $$n \geq 5$$, $$n!$$  is a multiple of $$5.2=10$$. This means that the units digit of $$n!$$ is zero when $$n \geq 5$$. 

Therefore, it suffices to simply consider the sum of 1! + 2! +3! + 4!, for which the units digit is 3.

Footnote:

[^1]: Inspired by and adapted from [Introduction to Counting and Probability](https://www.amazon.com/gp/product/B007HQN4QM/ref=dbs_a_def_rwt_bibl_vppi_i7)
