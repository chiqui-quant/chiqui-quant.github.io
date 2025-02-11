+++
date = '2025-02-11T12:29:26+01:00'
draft = true
katex = true
+++

**Questions** 
- What are some additional examples of normed spaces? $(\mathscr{C}(I),\lVert \cdot \rVert_{1,1})$, $(\mathscr{C}(I),\lVert \cdot \rVert_{1,\infty})$, $(\mathscr{C}_{0}^{1}(I),\lVert \cdot \rVert_{1})$.
- What is an open/closed ball and an open/closed set?
- Why an open ball is an open set?
- What are some properties about unions and intersections of open and closed sets? (What are 2 examples that we have seen in $\mathbb{R}$ with $\left|\cdot \right|$)?
- What is a sequence? What is a subsequence? When do we say that a sequence converges in a normed space? What is the first theorem that we have seen about the convergence of sequences in a normed space?

**Example.** $I=[a,b]\subset \mathbb{R}$, $\mathscr{C}^{1}(I)=\{f:I\to\mathbb{R}\text{ continuously differentiable}\}$ (recall that a continuously differentiable function $f(x)$ is a function whose derivative function $f'(x)$ is also continuous at the point in question). Set 
$$\lVert f \rVert_{1,1}=\int_{a}^{b}\left|f(t)\right|dt+\int_{a}^{b} \left|f'(t)\right|dt\qquad \qquad \lVert f \rVert_{1, \infty}=\sup_{t\in  I}(\left|f(t)\right|+\left|f'(t)\right|)$$
then $\lVert \cdot  \rVert_{1,1}$ and $\lVert \cdot  \rVert_{1, \infty}$ are norms on $\mathscr{C}^{1}(I)$. Note: without the parts with the derivatives they are only seminorms on $\mathscr{C}^{1}(I)$ (Q: why? how? What is that fails?). Note also that 
$$\lVert f \rVert_{1}=\int_{a}^{b} \left|f'(t)\right|dt\ \ \text{ and}\ \ \lVert f \rVert_{\infty}=\sup_{t\in  I}\left|f'(t)\right|$$
are seminorms on $\mathscr{C}^{1}$. **Exercise.** Check it! Help: 
$$\lVert f \rVert_{1}=0\iff\int_{a}^{b} \left|f'(t)\right|dt=0\iff  \left|f'(t)\right|=0\ \ \forall \  t\in  I\iff  f'(t)=0\ \ \forall \  t\in  I$$
which happens if and only if $f(t)$ is constant (not necessarily zero!).

**Example.** $\mathscr{C}^{1}_{0}(I)=\{f:I\to\mathbb{R}\text{ continuously differentiable with }f(x)=0\}$, $I=[a,b]$ is a vector space and 
$$\lVert f\rVert_{1}=\int_{a}^{b} \left|f'(t)\right|dt$$
with $f\in \mathscr{C}^{1}_{0}(I)$ defines a norm on $\mathscr{C}^{1}_{0}$. **Exercise.** Check it!

What is the topology of normed spaces? What do we mean by topology of a normed space? Why it is so important?

Crucial concepts are the ones of open/closed ball and open/closed sets.
**Definition.** Let $(X,\lVert \cdot \rVert)$ be a normed space. For any $x_{0}\in X$ and $r>0$, 
$$B(x_{0},r)=\{x\in  X \ : \  \lVert x-x_{0} \rVert<r\}$$
is the open ball centered at $x_{0}\in X$ with radius $r>0$, and 
$$B_{C}(x_{0},r)=\{x\in  X \ : \  \lVert x-x_{0} \rVert\leq  r\}$$
is the closed ball centered at $x_{0}\in X$ with radius $r>0$.

**Definition.** A subset $\mathcal{U}$ of $X$ is called an open set (for $(X,\lVert \cdot \rVert)$ a given normed space) if $\forall \ x\in \mathcal{U}\ \ \exists \ r>0$ such that $B(x_{0}, r)\subset \mathcal{U}$ (i.e. there is a radius $r$ such that there exists an open ball contained in the set). A subset $\mathcal{U}$ of $X$ is called a closed set if $\mathcal{U}^{C}=X\setminus \mathcal{U}$ is an open set.

Note: by convention $\emptyset$ is an open set (why? Take a look at mathstackexchange). Now, consider $X$ open set, then $X^{C}=\emptyset$ is closed so $\emptyset$ is also a closed set (and also $X$ is a closed set). Also, there are sets $\mathcal{U}$ of $X$ which are neither open nor closed.

**Proposition.** If $x_{0}\in X$, $r>0$ then $B(x_{0}, r)$ is an open set.

**Proof.** Indeed: let $x\in B(x_{0}, r)$, $\lVert x-x_{0} \rVert=\rho$, $0\leq \rho\leq r$ (this $r$ is the same as the one in $B(x_{0}, r)$) we look for $\varepsilon>0$ such that $B(x, \varepsilon)\subset B(x_{0}, r)$. 
![[FA02.excalidraw|250]]
Pick $y\in B(x, \varepsilon)$, then $\lVert y-x \rVert<\varepsilon$, we wish to choose $\varepsilon>0$ in such a way that $\lVert y-x_{0} \rVert<r$ (wait, shouldn't be $y-x_{0}<r$ instead of $y-x$? Yes, I did a typo). We have 
$$\lVert y-x_{0} \rVert=\lVert (y-x)+(x-x_{0}) \rVert\stackrel{\text{tr.ineq.}}{\leq} \underbrace{\lVert y-x \rVert}_{<\varepsilon}+\underbrace{\lVert x-x_{0} \rVert}_{=\rho}<\varepsilon+\rho.$$
If we choose $\varepsilon$ such that $\varepsilon+\rho\leq r$ then $\lVert y-x_{0} \rVert<\varepsilon+\rho<r$, $\varepsilon=r-\rho$ works (Q: why? Don't we include boundary points in this way? What happens in the extreme case? We have no problems because we chose y at distance strictly less than epsilon, which is greater than 0 so we chose a point for which it is impossible to be exactly in the boundary, that's the key point right?) $\implies$ $\forall \  x\in B(x_{0}, r)$, $\exists \  \varepsilon=r-\lVert x-x_{0} \rVert>0$ such that $B(x, \varepsilon)\subset B(x_{0}, r)\implies B(x_{0}, r)$ is an open set. $\square$

Personal comment: changing notation, instead of $x$, $x_{0}$, $y$ to $x$, $y$ and $z$ may make it easier to understand, at least it did for me.

Personal observation: actually the figure above can be misleading, when we have an open ball we don't consider the points which are in the boundary, by definition of the open ball, since we just consider the points strictly inside the radius $r$. The following is more illustrative (from "Functional Analysis, an elementary Introduction" by Marcus Haase).
![[open-ball-is-open.png|250]]
We also have the following results.
**P.** $B_{C}(x_{0}, r)$ is a closed set. Indeed: $X \setminus B_{C}(x_{0}, r)=\{x\in X \ : \ \lVert x-x_{0} \rVert>r\}$ is open (**Exercise.** check this is an open set).

**P.** Finite intersections of open sets of $(X,\lVert \cdot \rVert)$ is an open set of $(X,\lVert \cdot \rVert)$.
**P.** Any union of open sets of $(X,\lVert \cdot \rVert)$ is still an open set of $(X,\lVert \cdot \rVert)$.
**P.** Finite unions of closed sets is closed.
**P.** Any intersection of closed sets is closed. (**Exercise.** use de Morgan's rule to prove it) 

**E.g.** $X=\mathbb{R}$, $\lVert \cdot  \rVert=\left|\cdot \right|$, then:
(1) $(a,b)$, $(b,+\infty)$, $(-\infty, a)$ are open subsets of $(\mathbb{R},\left|\cdot \right|)$, 
(2) $[a,b]$, $\left[b, \infty\right)$, $\left(-\infty, a\right]$ and $\{a\}$ are closed (Q: why closed also with infinity? Is this related to the characterization in terms of limits?)
(3) $\left[a,b\right)$, $\left(a,b\right]$ are neither open nor closed.

Note: one has 
$$[0,1]=\bigcap_{n\geq 1}\left( -\frac{1}{n}, 1+\frac{1}{n} \right)$$
i.e. $B_{C}\left( \frac{1}{2},\frac{1}{2} \right)$ is not open. Note: this illustrates how the intersection of infinitely many open sets is not necessarily open. Moreover 
$$(0,1)=\bigcup_{n\geq  1} \left[ \frac{1}{n}, 1-\frac{1}{n} \right]$$
i.e. the union of infintitely many closed sets is not necessarily a closed set.

What are some fundamental concepts about the convergence of sequences?
**Def.** A sequence is a function $f:\mathbb{N}\to X$, $n \mapsto f(n)=x_{n}$ (i.e. that yields the n-th element of a set $X$?) and we write it $\{x_{n}\}_{n}$ or $(x_{n})_{n}$.

**Def.** A subsequence of $\{x_{n}\}_{n}$ is a sequence of the form $\{x_{\varphi(n)}\}_{n}$ with $\varphi:\mathbb{N}\to \mathbb{N}$ strictly increasing (e.g. $\varphi(n)=2n$).

**Def.** Let $(X,\lVert \cdot \rVert)$ be a normed space. A sequence $\{x_{n}\}_{n}\subset X$ is said to converge to $x\in X$ if 
$$\lim_{n \to \infty} \lVert x_{n}-x \rVert=0$$
i.e. $\forall \  \varepsilon>0$, $\exists \  N\in \mathbb{N}$, s.t. $\lVert x_{n}-x \rVert<\varepsilon\ \ \forall \ n\in \mathbb{N}$ (shouldn't be $\forall \ n\geq N$? Yes actually, it was a typo), so instead of $\forall \ n\in \mathbb{N}$ it should be $n\geq N$. We write $\lim_{n}x_{n}=x$ (or $x_{n}\stackrel{\lVert \cdot  \rVert}{\to}x$) and $x$ is called the limit of $\{x_{n}\}_{n}\subset X$.

**Thm.** Let $\{x_{n}\}_{n}\subset X$ be a convergent sequence of $(X,\lVert \cdot \rVert)$. Then: 
(1) the limit $x=\lim_{n}x_{n}$ is unique
(2) any subsequence of $\{x_{n}\}_{n}\in X$ converges to $x\in X$
(3) one has $\lim_{n}\lVert x_{n} \rVert=\lVert x \rVert$ (in $\mathbb{R}$), in particular $\sup_{n}\lVert x_{n} \rVert<\infty$
(4) if $\{x_{n}\}_{n}\subset X$ converges to $x\in X$, $\{y_{n}\}_{n}\subset X$ converges to $y\in X$ and $\{\alpha_{n}\}_{n}\subset \mathbb{R}$ converges to $\alpha\in\mathbb{R}$, then $\{x_{n}+\alpha_{n}y_{n}\}_{n}\subset X$ converges to $x+\alpha y\in X$.

**Proof of (1) (sketch).** Assume (by contradiction) $x$ and $y$ are two elements of $X$ such that $\lim_{n}x_{n}=x$ and $\lim_{n}x_{n}=y$, i.e. $\lim_{n}\lVert x_{n}-x \rVert=0$ and $\lim_{n}\lVert y_{n}-x \rVert=0$, then $\forall \  \varepsilon>0$ (fixed, this is important), $\exists \  N_{1}\in \mathbb{N}$ such that $\lVert x_{n}-x \rVert<\varepsilon\ \ \forall \ n\geq N_{1}$ and for the same reason $\exists \  N_{2}\in \mathbb{N}$ s.t. $\lVert x_{n}-y \rVert<\varepsilon\ \ \forall \ n\geq N_{2}$ (at some point both distances are less than $\varepsilon$). Pick $n\geq \max(N_{1},N_{2})$, then 
$$\lVert x-y \rVert=\lVert x-x_{n}+x_{n}-y \rVert\leq \lVert x-x_{n} \rVert+\lVert x_{n}-y \rVert<\varepsilon+\varepsilon$$
(where the first epsilon is for $n\geq N_{1}$ and the second is for $n\geq N_{2}$), so what we proved is that $\forall \  \varepsilon>0$, $0\leq \lVert x-y \rVert<2\varepsilon \implies \lVert x-y \rVert=0 \stackrel{\text{uniqueness}}{\implies }x-y=0_{X} \implies x=y$. $\square$ 

**Proof of (3) (sketch).** We use the reverse triangle inequality: $\left|\lVert x \rVert-\lVert y \rVert\right|\leq \lVert x-y \rVert\ \ \forall \ x,y\in X$, $[\lVert x \rVert=\lVert x-y+y \rVert\leq \lVert x-y \rVert+\lVert y \rVert\to \lVert x \rVert-\lVert y \rVert\leq \lVert x-y \rVert]$.




