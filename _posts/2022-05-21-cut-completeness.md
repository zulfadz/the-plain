---
layout: post
title: "The Axiom of Completeness is equivalent to the Cut Property in R"
comments: true
description: "analysis"
keywords: "math, analysis"
---


The Axiom of Completeness states that:[^1]

> Every nonempty set of real numbers that is bounded above has a least upper bound.

The Cut Property states that:[^1]

> If $$A$$ and $$B$$ are nonempty, disjoint sets with $$A \cup B = \mathbf{R}$$ and $$a <b$$ for all $$a \in A$$ and $$b \in B$$, then
there exists $$c \in \mathbf{R}$$ such that $$x \leq c$$ whenever $$x \in A$$ and $$ x \geq c$$ whenever $$x \in B$$.

Using the Axiom of Completeness, it is possible to prove the Cut Property. Let $$A$$ and $$B$$ be nonempty, disjoint sets with $$A \cup B = \mathbf{R}$$ and $$a <b$$ for all $$a \in A$$ and $$b \in B$$.
Since $$A$$ is nonempty and bounded above, sup $$A$$ exists. Let $$ c = $$ sup $$A$$.

$$\implies$$ $$ a \leq$$ $$c$$ for all $$ a \in A$$ by the definition of supremum.

$$\implies$$ Given arbitrary $$b \in B$$, $$b > a$$ for all $$ a \ in A$$. By definition of supremum, $$b \geq$$ $$c$$
for all $$b \in B$$.

Conversely, using the Cut property, it is possible to prove the Axiom of Completeness. That is, if $$\mathbf{R}$$ has the Cut Property, and let $$E$$ be nonempty set that is bounded above, then sup $$E$$ exists.
Let $$B$$ be the set of upper bounds of $$E$$. Morever, let $$B^c = \mathbf{R} - B$$ be the set of real numbers which are not in $$B$$. It follows that
$$B \cup B^c = \mathbf{R}$$. By contradiction, suppose that $$E$$ has no supremum; that is, it does not have the least upper bound.

$$\implies$$ $$B \cap E = \empty$$, i.e., upper bound of $$E$$ is not an element of $$E$$ . Otherwise, there exists sup $$E$$.

$$\implies$$ $$E \subseteq B^c$$. Thus, $$B^c$$ is a nonempty set.

$$ \implies$$ Thus, by the Cut Property, there exists $$c$$ such that $$x \leq c$$ whenever $$ x \in B^c$$ and $$ x \geq c$$ whenever $$ x \in B$$.

$$ \implies$$ $$c$$ is not an element of $$B$$ because otherwise it means that $$c$ is the smallest element of $$B$$, i.e., the least upper bound of $$E$$ which we have assumed to be not in existence. 
It follows that $$c \in B^c$$. But $$c$$ is an upper bound $$B^c$$, and because $$E \substeq B^c$$, $$c$$ is also an upper bound $$E$$. This implies that $$c \in B$$, which is a contradiction.

Footnote:

[^1]: Definitions taken from Understanding Analysis by Abbott.
