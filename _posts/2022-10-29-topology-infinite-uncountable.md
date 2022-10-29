---
layout: post
title: "Topologies on an infinite set"
comments: true
description: "math"
keywords: "topology"
---

It's been a while since I last studied topology (about 8 years?) and I've been reading up topology stuffs recently for fun when I'm not busy with work. My brain is not yet wired to internalize it, but these two findings about topologies on an infinite set are pretty cool.

> Finding 1: Let $$X$$ be an infinite set. Then there are infinitely many distinct topologies on $$X$$.

Proof: For each $$x \in X$$, define topology $$\tau_{x} = \{X, \emptyset, \{x\}\}$$. Since there are infinitely many distinct $$x$$, there are infinitely many distinct $$\tau_{x}$$. These are quite useless topologies, but they are fun.

> Finding 2: Let $$X$$ be an infinite set. Then there are uncountably many distinct topologies on $$X$$.

Proof: Let $$P(X)$$ be the set consisting of all subsets of $$X$$. As known from analysis $$P(X)$$ is uncountable. Let $$Q(X) = P(X) - \{X, \emptyset\}$$. We know that $$Q(X)$$ is uncountable. For each element $$S \in Q(X)$$, define topology $$\tau_{S} = \{X, \emptyset, S\}$$. As there are uncountably many $$S$$, there are uncountably many $$\tau_{S}$$.