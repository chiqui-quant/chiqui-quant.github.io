+++
date = '2025-02-11T12:29:26+01:00'
draft = true
title = 'My Second Post'
math = true
+++

**Questions** 
- What is the characterization of closed sets in terms of sequences? 
- What is the closure of a subset of a normed space? What are some important observations about it?
- Why the closure of an open ball is the closed ball?
- When do we say that a subset in a normed space is dense? What are two examples of dense sets that we have seen in $(\mathbb{R},| \cdot |)$?
- What does the lemma about density that we have seen say? How can we use it to check if a set is dense?
- What is an interior point? What are some important observations about it?
- What is a lemma that relats the closure and interior? What is an example?
- What is a limit point? What is an example of limit point?
- What does the proposition about limit points say?
- When do we say that norms are equivalent?
- What is an example of norms that are not equivalent? On $\mathscr{C}(I)$, $\lVert \cdot \rVert_{1}$ and $\lVert \cdot \rVert_{\infty}$.

How can we characterize closed sets in terms of sequences? Q: What does the previous question actually mean?

**P.** A subset $C$ of $X$ is a closed subset of $(X,\lVert \cdot \rVert)$ if the limit of any convergent sequence of $C$ remains in $C$, i.e. if $\forall \  \{x_{n}\}_{n}\subset C$, $\{x_{n}\}_{n}$ converges to $x$, then $x\in C$. (Q: isn't this an if and only if?)

**Proof.** "$\Rightarrow$" Assume that $C$ is closed and consider a sequence $\\{x\_{n}\\}\_{n}\subset C$ which converges to some $x\in X$. We need to prove $x\in C$. We argue by contradiction and assume $x\notin C$, i.e. $x\in X\setminus C$, but by assumption $C$ is closed so $X\setminus C$ is open, then by definition $x\in X\setminus C\Rightarrow  \exists \ r>0$ s.t. $B(x, r)\subset X\setminus C$. But since $\lim_{n}x_{n}=x$, $\forall \  \varepsilon>0: \exists \ N_{\varepsilon}\in \mathbb{N}$ s.t. $\lVert x_{n}-x \rVert<\varepsilon\ \ \forall \ n\geq N_{\varepsilon}$. In particular, for $\varepsilon=r: \exists \ N_{r}\in \mathbb{N}$ s.t. $\lVert x_{n}-x \rVert<r\ \ \forall \ n\geq N_{r}$, i.e. $x_{n}\in B(x, r)\ \ \forall \ n\geq N_{r}$, $x_{n}\in X\setminus C\ \ \forall \ n\geq N_{r}$ but $\{x_{n}\}_{n}\subset C$ (contradiction) $C \cap (X\setminus C)=\emptyset \Rightarrow  x\in C$. 

"$\Leftarrow$" (If any seq. conv. to $x\in C$, then $C$ is closed) Assume that **any** convergent sequence has its limit in $C$ and let us prove that $C$ is closed. We argue by contradiction and assume $C$ not to be closed. $C \neq \emptyset$, $X\setminus C$ is **not open**, $X\setminus C \neq \emptyset$, which means "$\forall \  x\in X\setminus C,\exists \ r>0$ s.t. $B(x, r)\subset X\setminus C$" is not true, i.e. $\exists \  x\in X\setminus C:r>0$, $B(x, r)\not \subset X\setminus C$, i.e. $\forall \  r>0:B(x, r)\cap C \neq \emptyset$. For $r=\frac{1}{n}$, $n\geq 1$, $n\in \mathbb{N}$, $B\left( x, \frac{1}{n} \right)\cap C \neq \emptyset$ **for all** $n\in \mathbb{N}$, i.e. $\forall \  n\in \mathbb{N}\ \ \exists \ x_{n}\in C \cap B\left( x, \frac{1}{n} \right)$ we have like this a sequence $\{x_{n}\}_{n}\subset C$ and $\lVert x_{n}-x \rVert<\frac{1}{n}\ \ \forall \ n\in \mathbb{N}$. So $\lim_{n}\lVert x_{n}-x \rVert=0$, i.e. $x=\lim_{n}x_{n}$, $x\in X\setminus C$ which contradicts our assumption, therefore $C$ is closed. $\square$

**Def.** Let $(X,\lVert \cdot \rVert)$ be a normed space and let $Y \subset X$. The **closure** $\overline{Y}$ of $Y$ is defined as $\overline{Y}=\{x\in X \ : \ \exists \ \{x_{n}\}_{n}\subset Y\text{ s.t. }x=\lim_{n}x_{n}\}$ (i.e. the set of all possible elements in $X$ which are limits of sequences in $Y$).

Note: (1) $Y \subset \overline{Y}$ (pick $x\in Y$, $\lim_{n}x_{n}=x\ \ \forall \ n$, $\{x_{n}\}_{n}\subset Y$, $x=\lim_{n}x_{n}$), (2) $\overline{Y}$ is closed (Proof: pick a sequence $\{y_{n}\}_{n}\subset \overline{Y}$ which cv. to $y\in X$, we need to prove that $y\in \overline{Y}$. For any $n\in\mathbb{N}$, $y_{n}\in \overline{Y}$ means that there is a sequence $\{x_{k}^{n}\}_{k}\subset Y$, i.e. a sequence $x_{k}$ depending on $n$, s.t. $\lim_{k}x_{k}^{n}=y_{n}$, definition of $y_{n}\in \overline{Y}$, then $y=\lim_{n}\lim_{k}x_{k}^{n}$, sequence with two indeces, $y$ is a limit of a sequence in $Y$ (PR: which one?) $\implies y\in \overline{Y}$. So, by construction $\overline{Y}$ is a closed set containing $Y$). Actually, this is the smallest possible closed set containing $Y$, i.e. 
$$\overline{Y}=\bigcap_{\substack{C\text{ closed} \\Y \subset C }}C$$
(the interseciton of all possible closed sets containing $Y$), to show it you need to prove that if $C$ is closed and $Y \subset C$ then $\overline{Y}\subset C$ (trivial).

**E.g.** $\overline{B(x_{0},r)}=B_{C}(x_{0}, r)$ (the closure of the open ball is the closed ball).

**Proof.** Indeed: $B_{C}(x_{0}, r)$ is a closed set and $B(x_{0}, r)\subset B_{C}(x_{0}, r)$ which means $\overline{B(x_{0}, r)}\subset B_{C}(x_{0}, r)$. Let us prove now that $B_{C}(x_{0}, r)\subset \overline{B(x_{0}, r)}$. Pick $x\in B_{C}(x_{0}, r)$, if $\lVert x-x_{0} \rVert<r$ then $\{x_{n}\}_{n}\subset \overline{B(x_{0}, r)}$, i.e. $x\in \overline{B(x_{0}, r)}$. Assume then $\lVert x-x_{0} \rVert=r$, if we construct a sequence $\{x_{n}\}_{n}\subset B(x_{0}, r)$ s.t. $x=\lim_{n}x_{n}$ then we would have $x\in \overline{B(x_{0}, r)}$. Let $u=\frac{1}{r}(x-x_{0})\in X$, $\lVert u \rVert=\frac{1}{r}\lVert x-x_{0} \rVert=1$ (what is the meaning of this?). 
![[FA03.excalidraw|250]]
Next, since $x=x_{0}+ru$ define $x_{n}=x_{0}+r\left( 1-\frac{1}{n} \right)u\in X$. Then 
$$\lVert x_{n}-x \rVert=r\left( 1-\frac{1}{n} \right)\lVert u \rVert=r\left( 1-\frac{1}{n} \right)<r$$
so $x\in B(x_{0},r)$ **for all** $n$. Now, we would like to show that the sequence converges to $x$, $x_{n}-x=x_{0}-r\left( 1-\frac{1}{r} \right)u-x_{0}-ru=-\frac{1}{n}u$. So 
$$\lVert x_{n}-x \rVert=\left|-\frac{1}{n}\right|\cdot \underbrace{\lVert u \rVert}_{=1}=\frac{1}{n}\stackrel{n\to  +\infty}{\to} 0$$
so we proved $\lim_{n}x_{n}=x$, which means $\{x_{n}\}_{n}\subset B(x_{0},r)\implies x\in \overline{B(x_{0},r)}$. $\square$

**Def.** Let $(X,\lVert \cdot \rVert)$ be a normed space, $Y \subset X$. We say that $Y$ is **dense** in $X$ if $\overline{Y}=X$.
Note: this means that we can approximate any element in $X$ with a sequence in $Y$.

**E.g.** In $(\mathbb{R},\left|\cdot \right|)$, $\mathbb{Q}$ is dense in $\mathbb{R}$, $\overline{\mathbb{Q}}=\mathbb{R}$, $x\in\mathbb{R}$ can be written as $x=\sum_{n\in \mathbb{Z}}a_{n}10^{n}$ (decimal representation), $a_{n}\in \{-9,-8,\ldots,8,9\}$, $=\lim_{N \to \infty}\sum_{n=-N}^{N}a_{n}10^{n}$ (note that this sum is in $\mathbb{Q}$). (TODO: Complement with 2022/2023 lecture notes)

**E.g.** In $(\mathbb{R},\left|\cdot \right|)$ also $\overline{\mathbb{R}\setminus \mathbb{Q}}=\mathbb{R}$.

**L.** Let $(X,\lVert \cdot \rVert)$ be a normed space, $Y \subset X$. Then $Y$ is dense in $X$ if and only if for any open set $O\subset C:Y \cap O \neq \emptyset$ (with $O \neq \emptyset$). $\boxed{Proof: exercise.}$

Note: so this gives a way of checking if a set is dense.

What is an interior point?
**Def.** Let $(X,\lVert \cdot \rVert)$ be a normed space, $Y \subset X$. An element $y\in Y$ is called an **interior point** of $Y$ if there is $\varepsilon>0$ s.t. $B(y, \varepsilon)\subset Y$.

What is the interior of a set?
We define then $\text{Int}(Y)=\overset{o}{Y}=Y^{o}=\{y\in Y : y\text{ interior point of }Y\}$ (the first equalities are just a matter of notation). Note: (1) $\text{Int}(Y)\subset Y$, $Y$ open $\iff$ $Y=\text{Int}(Y)$, (2) $\text{Int}(Y)$ is open (**Exercise.** check it). 

$\text{Int}(Y)$ is actually the biggest open set contained in $Y$, i.e. 
$$\text{Int}(Y)=\bigcup_{\substack{O\text{ open} \\ O\subset Y}}O$$
(by 1 and 2). Why is it exactly equal? 
$$\bigcup_{\substack{O\text{ open} \\ O\subset Y}}O\subset \text{Int}(Y)$$
because if $O\subset Y$, $O$ open, $O \neq \emptyset$ for $y\in O$, $y\in Y$, $\exists \ \varepsilon>0$ s.t. $B(y, \varepsilon)\subset O\subset Y$ which means $y$ is an interior point of $Y$, therefore $y\in \text{Int}(Y)$.

**L.** $(X,\lVert \cdot \rVert)$ normed space, $Y \subset X$. One has $\overline{X\setminus Y}=X\setminus \text{Int}(Y)$ (from above, simple exercise with de Morgan rule). **E. Prove it.**

**E.g.** $\text{Int}(\mathbb{Q})=\emptyset$ in $(\mathbb{R},\left|\cdot \right|)\iff \overline{\mathbb{R}\setminus \mathbb{Q}}=\mathbb{R}$.

What is a limit point?  
**Def.** $(X,\lVert \cdot \rVert)$, $\{x_{n}\}_{n}\subset X$ be given. We say that $x$ is a **limit point** of $\{x_{n}\}_{n}$ if there is a subsequence $\{x_{\varphi(n)}\}_{n}$ of $\{x_{n}\}_{n}$ which converges to $x$, i.e. $\lim_{n}\lVert x_{\varphi(n)}-x \rVert=0$.

**E.g** On $(\mathbb{R},| \cdot |)$, the sequence $\{(-1)^{n}\}_{n}$ has two limit points which are +1 and -1.

**P.** If $(X,\lVert \cdot \rVert)$ is a normed space and $Y \subset X$, then 
$$\overline{Y}=\{x\in X: x\text{ limit point of a sequence in }Y\}$$
When do we say that two norms are equivalent?
**Def.** Let $X$ be an $\mathbb{R}$-vector space. We say that two norms $\mathcal{N}_{1}$ and $\mathcal{N}_{2}$ are **equivalent** if there exist two positive constants $c_{1}>0$, $c_{2}>0$ such that $\mathcal{N}_{1}(x)\leq c_{1}\mathcal{N}_{2}(x)$ and $\mathcal{N}_{2}(x)\leq c_{2}\mathcal{N}_{1}(x)\ \ \forall \ x\in X$.

What is the idea behind this? If you have a ball on the norm $\mathcal{N}_{2}$ with radius $r$, then that ball is contained in the norm $\mathcal{N}_{1}$ (and viceversa). (Q: what does this actually mean?) Note: two equivalent norms on $X$ induce the same open sets (topology), $O$ open for $\mathcal{N}_{1}\Leftrightarrow  O$ open for $\mathcal{N}_{2}$.

**E.g.** $X=\mathscr{C}(I)$, $I=[0,1]$, $\lVert f \rVert_{1}=\int_{0}^{1}\left|f(t)\right|dt$, $\lVert f \rVert_{\infty}=\sup_{t\in [0,1]}\left|f(t)\right|$ are two norms on $X$ but they are **not** equivalent. Why? Consider 
$$f_{k}=\begin{cases} 0 & t\geq  \frac{1}{k} \\ 1-kt & t\in \left[0, \frac{1}{k}\right) \end{cases}$$
TODO: make more illustrative picture to see better how the sequence behaves.
![[FA03_0.excalidraw|250]]
Then we have $\lVert f_{k} \rVert_{1}=\frac{1}{2}\cdot \frac{1}{k}$ (Q: why? Review computation of integrals) and $\lVert f_{k} \rVert_{\infty}=1$. (Q: what is the actual reasoning behind this, how would you explain it to someone who is not familiar with sequences of functions? Try to plug in numbers in place of k and see how it behaves.) so we see that $\lim_{k \to \infty}\lVert f_{k} \rVert_{1}=0$, $\lVert f_{k} \rVert=1$, there is no $c_{1}>0$ s.t. $\lVert f \rVert_{\infty}\leq c_{1}\lVert f \rVert_{1}\ \ \forall \ f\in X$ (but there is $c_{2}=1$ s.t. $\lVert f \rVert_{1}\leq c_{2}\lVert f \rVert_{\infty}$).
