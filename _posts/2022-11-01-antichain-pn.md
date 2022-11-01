---
layout: post
title: "Forming an uncountable antichain from P(N)"
comments: true
description: "math"
keywords: "analysis"
---

For some reason, I have problem retaining the concept of antichain, so I'm writing this proof out to reinforce my understanding. 

> Consider the power set of natural numbers, $$P(\mathbb N)$$. A subset $$A$$ of $$P(\mathbb N)$$ is defined as antichain if no element in $$A$$ is a subset of another element in $$A$$. Show that there exists an antichain that is uncountable.

As an example, this is not antichain, $$\{\{1\},\{1,2,3\}\}.$$ Whereas this is antichain $$\{\{4\},\{1,2,3\}\}.$$

To prove that there exists an antichain that is uncountable, we observe two facts. First, the set $$S = \{(a_{1},a_{2},a_{3}, \cdots :a_{i} \text{ is either } 0 \text{ or } 1\}$$ is uncountable. Second, the set of even numbers $$E=\{2,4,6,\cdots\}$$ and the set of odd numbers $$O = \{1,3,5,\cdots\}$$ are disjoint.

For each $$s \in S, s= (s_{1},s_{2},s_{3}, \cdots)$$, construct a set $$A_s$$ in the following way:

$$\begin{align}
2n \in A_{s} &\text{ if } s_{n}=1 \\
2n-1 \in A_{s} &\text{ if } s_{n} =0.
\end{align}$$

Repeat the same procedure to construct a collection of sets $$\{A_{s}:s \in S \}.$$

Note that for $$s \neq j$$, $$A_{s}$$ and $$A_{j}$$ are disjoint because $$E$$ and $$O$$ are disjoint. There are also uncountably many distinct $$A_{s}$$ because there are uncountably many distinct elements of $$S$$. Finally, we need to ascertain that each $$A_{s}$$ is a subset of $$\mathbb N$$ to satisfy the definition of antichain. This follows from each $$A_{s} \subseteq E \cup O = \mathbb N$$. Therefore, the collection $$\{A_{s}:s \in S \}$$ forms an uncountable antichain.

