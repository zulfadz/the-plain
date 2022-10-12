---
layout: post
title: "Interesting topology of open rays"
comments: true
description: "math"
keywords: "topology"
---

I recently started studying [this](https://www.math.stonybrook.edu/~oleg/easymath/topoman/index.html) topology book by Oleg Viro, Ivanov, Kharlamov, Netsvetaev. It was pretty nicely-written, and I'd like to share this problem from the section on topological structure:


> Let $$X$$ be the ray $$[0,+\infty)$$, and let $$\Omega$$ consist of $$\emptyset$$, $$X$$, and all rays $$(a,+\infty)$$ with $$a \geq 0$$. Prove that $$\Omega$$ is a topological structure.

We wish to show that firstly, $$\Omega$$ contains $$X$$ and $$\emptyset$$. This is already verified by the definition above. Secondly, the intersection of finitely many elements in $$\Omega$$ is itself and element in $$\Omega$$. Thirdly, the union of any elements in $$\Omega$$ is itself an element in $$\Omega$$. 

To prove the second criterion, note that given finitely many elements $$(a,+\infty)$$ with $$a \geq 0$$, there exists a maximum $$a_{\max}$$. It follows that the intersection of these elements is $$(a_{\max}, \infty)$$.

For the third criterion, we wish to show that $$\bigcup_{a \geq 0} (a, \infty) = (\inf a, \infty).$$ 

Let $$x \in \bigcup_{a \geq 0} (a, \infty)$$. Then $$x>a$$ for at least one $$a$$. As $$a \geq \inf a$$ for all $$a$$, $$x>\inf a$$. Thefore, $$x \in (\inf a, \infty)$$, which means $$\bigcup_{a \geq 0} (a, \infty) \subset (\inf a, \infty).$$

Similarly, let $$x \in (\inf a, \infty).$$ Then $$x > \inf a$$. By definition of infimum, for any $$\epsilon>0$$, there exists $$a$$ satisfying $$a < \inf a + \epsilon$$. Thus, picking $$\epsilon = x - \inf a$$ there exists $$a$$ satisfying $$a < x$$. Hence, $$x \in \bigcup_{a \geq 0} (a, \infty)$$, which means $$(\inf a, \infty) \subset \bigcup_{a \geq 0} (a, \infty).$$ And we are done.

A side note is to see the implication if we change the problem statement, instead of open rays $$(a,+\infty)$$, we consider closed rays $$[a,+\infty)$$. We see that $$\Omega$$ now is _not_ a topological structure. For instance, let $$a = 1\frac{1}{n}$$. Then the infinite union of the closed rays is an open ray $$(1, \infty)$$, which is not in $$\Omega$$.

