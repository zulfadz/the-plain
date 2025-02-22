---
layout: post
title: "The axiom of completeness is equivalent to the cut property in R"
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

$$\implies$$ $$b \geq c$$ for all $$b \in B$$ by the definition of supremum.

Conversely, using the Cut property, it is possible to prove the Axiom of Completeness. That is, if $$\mathbf{R}$$ has the Cut Property, and let $$E$$ be nonempty set that is bounded above, then sup $$E$$ exists.

Let $$B$$ be the set of upper bounds of $$E$$. $$B$$ is nonempty as $$E$$ is bounded above. Morever, let $$B^c = \mathbf{R} - B$$ be the set of real numbers which are not in $$B$$. It follows that $$B \cup B^c = \mathbf{R}$$. By contradiction, suppose that $$E$$ has no supremum.

$$\implies$$ $$B \cap E = \emptyset $$ (To see this, show that if $$e$$ is an upper bound of $$E$$, and $$ e \in E$$, then $$e =$$ sup $$ E$$).

$$\implies$$ $$E \subseteq B^c$$. Thus, $$B^c$$ is a nonempty set. Moreover, $$ a < b$$ for all $$ a \in B^c$$ and $$b \in B$$.

$$ \implies$$ By the Cut Property, there exists $$c$$ such that $$x \leq c$$ whenever $$ x \in B^c$$ and $$ x \geq c$$ whenever $$ x \in B$$.

$$ \implies$$ $$c$$ is not an element of $$B$$ because otherwise it means that $$c$$ is the smallest element of $$B$$, i.e., sup $$E$$ which we have assumed to not exist. 

$$\implies$$ It follows that $$c \in B^c$$. But $$c$$ is an upper bound $$B^c$$, and because $$E \subseteq B^c$$, $$c$$ is also an upper bound $$E$$. This implies that $$c$$ has to be in $$B$$, which is a contradiction.

Footnote:

[^1]: Definitions taken from Understanding Analysis by Abbott.
