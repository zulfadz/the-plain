---
layout: post
title: "sup (A + B) = sup A + sup B"
comments: true
description: "analysis"
keywords: "math, analysis"
---


Let $$A$$ and $$B$$ be nonempty subsets of real numbers, each bounded above. The supremum of $$A$$ is sup $$A$$ and the supremum of $$B$$ is sup $$B$$. How do we show that the sup ($$A + B$$) = sup $$A$$ + sup $$B$$?

Recall the lemma:

> $$s$$ = sup $$A$$ if and only if for every $$\epsilon > 0$$, there exists $$a \in A$$ such that $$s - \epsilon < a$$


Using the lemma, it suffices to show that every $$\epsilon > 0$$, there exist $$a \in A$$ and $$b \in B$$ such that sup $$A$$ + sup $$B - \epsilon < a + b.$$

Consider sup $$A$$ $$+$$ sup $$B - \epsilon$$

$$\implies$$ (sup $$A - \epsilon/2$$) $$+$$ (sup $$B - \epsilon/2$$)

$$\implies$$ (sup $$A - \epsilon/2$$) $$< a$$ for some $$a \in A$$, and (sup $$B - \epsilon/2$$) $$< b$$ for some $$b \in B$$.

Adding these last two inequalities completes the proof.

