+++
date = '2025-02-11T12:29:26+01:00'
draft = true
title = 'My First Post'
katex = true
+++

**Big Disclaimer:** I would like to improve the notes in some future with better explanations, but for now this is the best I can provide, I hope it will still be useful for you.

**Questions** 
- What is functional analysis?
- What is a vector space?
- What is a norm?
- What is a normed space?
- What are some examples of normed spaces? $(\mathbb{R}^{n},\lVert \cdot \rVert_{e})$, $(\mathbb{R}^{n},\lVert \cdot \rVert_{1})$, $(\mathbb{R}^{n},\lVert \cdot  \rVert_{\infty})$, $(\ell^{1}(\mathbb{N}),\lVert \cdot \rVert_{1})$, $(\mathscr{C}(I),\lVert \cdot \rVert_{1})$, $(\mathscr{C}(I),\lVert \cdot \rVert_{\infty})$.

Personal Introduction: this is the set of lecture notes on Analysis B (basic), given by prof. Bertrand Lods during 2021/2022. They are written in an unpolished way and I hope to improve them with time and suggestions. They are intended for the student who started appreciating math quite late (like me) and lacks the mathematical familiarity or maturity that one usually develops during a bachelor in Mathematics but also can't wait to have a glance at more advanced stuff. For this reason, the approach I used was basically to transcribe everything the professor wrote and said, which allowed me to gradually become more familiar with how to read and interpret the mathematical notation. In retrospect it really represents a good example of trying to kill a fly with a bazooka, the format of the notes is considerably bloated (my fault). This helped me understand why math is the way it is, and why mathematics makes use of all its strange symbols, to achieve a great deal of compression of ideas. Depite its difficulty and increasing abstractness, do not feel discouraged, the scope of this course is not to perfectly understand and remember all the results, but rather to get in touch with some important ideas and understand why and how some technical difficulties emerge (elaborate more). For a condensed version of the notes there are already the lecture notes provided by the professor, this can be considered as the long-form version, for those who want to dig deeper. 

# Functional Analysis
Functional analysis can be simply considered or summarized as the study of function spaces. A space is nothing else than another name for a set with some particular structure (generally a vector space structure, that is, closed under summation and scalar multiplication). This means we will consider sets of functions with some common property (eg. integrable or continuous over an interval) and we will call this a space of functions. Then by means of a norm ... (what do we actually do?). It is often also described as infinite dimensional analysis combined with linear algebra, with a pinch of topology. As far as I know it is an apparently important tool for solving Stochastic Differential Equations (even if I still don't know how). Note: from the course of stochastic processes, there is a part in which prof. highlighted a strong link between SDEs and functional analysis.

TODO: make a section and collect different views of what functional analysis is, i.e. the study of spaces of functions and their properties. 

A powerful and shocking claim about the philosophy behind functional analysis is the following: =="The basic idea of functional analysis is that functions are infinite dimensional vectors"== (of image values) Marcus Pivato in his notes titled "Analysis, Measure and Probability: A Visual Introduction". 

TODO: implement prof. Lods one sentence description of what the subject is about.

Plan:
- (1) Intro to functional analysis: normed spaces (we are interested in putting a norm on $\infty$-dimensional vector spaces). $\color{lime}\textbf{Q}$. why do we care about this? The norm is a way to measure the size of elements (and distances between them). Usually this is not enough, we would like to say more things.
- (2) Banach spaces (special case of normed spaces, with additional and interesting properties). $\color{lime}\textbf{Q}$. how are they are used? (Because of their nice properties, which ones? Completeness. Why completeness is very nice?). This is the core of functional analysis, the study of Banach spaces.
- (3) Inner product and Hilbert spaces (Banach spaces with additional structure, they mimic finite dimensional vector spaces, $\color{lime}\textbf{Q}$. how?). (Special case of the special case, look a lot like $\mathbb{R}^{2}$, $\mathbb{R}^{3}$)
- (4) (Complements about) Lebesgue spaces (which are important Banach spaces, link between measure and integration theory and functional analysis, study of spaces of functions, which are integrable, at some power, we can apply the nice properties of Banach spaces to Lebesgue spaces). ($\color{lime}\textbf{Q}$. why are lebesgue spaces important?). 
- (5) Fourier analysis. (Enters the game to help computations, more practical) ($\color{lime}\textbf{Q}$. why do we want to study this? How is this useful?)

## 1. Normed Spaces
A normed space is a space on which you define a norm. Now, we should try to understand what is a space and what is a norm. Note: this is not the most general framework. Topological space → metric space (pathological things you don't want to see [$\color{lime}\textbf{Q}$. for example?])→ normed space. We assume the space of elements are dealing with is a vector space.

We consider in general $\mathbb{R}$-vector spaces, but the theory extends to $\mathbb{K}$-vector spaces with $\mathbb{K}=\mathbb{C}$.

What is a vector space? Just a collection of elements, but we are able to do operations with those elements. This is a tool of construction. We will define or establish the rules on which the game will be based and work.  
**Definition.** A $\mathbb{K}=\mathbb{R}$ (or $\mathbb{K}=\mathbb{C}$) vector space $X$ is a set $X \neq \emptyset$ on which we can define two operations:
- SUM (addition): given $x,y\in X$ we can define a third element $x+y\in X$ which is the sum of $x$ and $y$.
- SCALAR MULTIPLICATION: given $x\in X$, $\alpha \in \mathbb{K}$ we can define $\alpha \cdot  x\in X$ (i.e. the product of $\alpha\in \mathbb{K}$ with $x\in X$).  

And the two operations are such that (they satisfy the following properties):  
(0) If you take $x\in X$, $y\in X$ (the operation is still inside), $\Rightarrow x+y\in X$. If you take $x\in X,\lambda \in \mathbb{K}\Rightarrow \alpha \cdot x\in X$ (the scaled element still belongs to $X$).  
(1) Commutativity of $+$: $x+y=y+x \ \ \forall \  x,y\in X$ (that element is the same thing, but life is not like this, life is not commutative at all, the operations you make in life are not commutative, it is not the same if you put first your underwear and then your pants, than putting first your pants and then the underwear, you would look very different).  
(2) Associativity of +: $(x+y)+z=x+(y+z)\ \ \forall \ x,y,z\in X$ (the order of the sum doen't even count if you make the sum of 3 elements). ($x+y$ produce someone in $X$...)  
(3) Neutral element of +: there is a neutral element, that we call $0_{X}\in X$ "the zero of $X$", with respect to the sum such that $0_{X}+x=x+0_{X}=x\ \ \forall \ x\in X$. (the zero is the element which summed to another element gives the element itself).  
(4) Uniqueness: there is a unique element $y=-x\in X$ (this is just notation) (or if you prefer $z_{x}\in X$) such that $x+y=0_{X}=y+x\ \ \forall \ x\in X$. (or $x+z_{x}=0_{X}=z_{x}+x$ and we will write $z_{x}=-x$) (is it possible to sum $x$ with someone to obtain the neutral element?) There is no subtraction, just the sum of the opposite.  
(5) Commutativity of $\cdot$ (the product): $\forall \  \alpha,\beta \in \mathbb{K}$, $\forall \ x\in X$ we have    
$$\alpha \stackrel{(1)}{\cdot  } (\beta \stackrel{(2)}{\cdot  }  x)=(\alpha \stackrel{(3)}{\cdot  } \beta)\stackrel{(4)}{\cdot  }x$$
where (1) is a product in $X$, (2) is a product in $X$, (3) is a product in $\mathbb{K}$ and (4) is a product in $X$ (Q: what does it mean?) The element $\beta\cdot x$ is multiplied by $\alpha$, and this is the same element as... (and the property is that this is the same result, note that they are not the same object, [$\color{lime}\textbf{Q}$. in which sense?]).  
(6) Distributivity of $\cdot$ (in  $\mathbb{K}$): $\forall \  \alpha,\beta \in\mathbb{K}, \ \ \forall \ x\in X$ we have  
$$(\alpha\stackrel{(1)}{+} \beta)\cdot  x=\alpha x\stackrel{(2)}{+} \beta x$$
where (1) is a sum in $\mathbb{K}$ (so $\alpha+\beta$ is an element in $\mathbb{K}$) and (2) is a sum in $X$. (we compare this to the sum between $\alpha x$ and $\beta x$), and what happens is that those elements are the  same. Note: I can do the opposite (see below).  
(7) Distributivity of scalar: $\forall \  \alpha\in \mathbb{K}, \forall \ x,y\in X$ we have $\alpha\cdot (x+y)=\alpha\cdot x+\alpha\cdot y$. I sum $x$ and $y$, this is an element in $X$...  
(8) Neutrality of $\cdot$ (neutral element in $\mathbb{K}$): $1x=x\ \ \forall \ x\in X$.  
TODO: how to visualize all these operations in abstract space mapping to spherical space for example, intuitively? This requires more thought, it may be easier from R1 to R2 (or R1 to R3, R2 to R3).

Q (a posteriori): why do we start from this definition? Just to define the rules of the game?
Q: try to check the properties of vector space for $\mathbb{C}$.
All those are choices (about classical sum on $\mathbb{R}^{2}$), but you could take the sum as the first component plus twice the second one for example.
[$\color{lime}\textbf{Q}$. What is meant by "space"? A set of elements with some property?]

What are some examples of vector spaces?  
[$\color{lime}\textbf{Q}$. Why the choice of capital $N$ instead of $n$?]  
**Example.** $\mathbb{R}^{N}=\{\underline{x}=(x_{1},\ldots,x_{N}), x_{i} \in \mathbb{R}\}$ is a vector space. Sum on $\mathbb{R}^{N}$: given $\underline{x}=(x_{1},\ldots,x_{N})$ and $\underline{y}=(y_{1},\ldots,y_{N})$ we have $\underline{x}+\underline{y}=(x_{1}+y_{1},\ldots,x_{N}+y_{N})\in \mathbb{R}^{N}$. For the scalar multiplication we have that for $\underline{x}=(x_{1},\ldots,x_{N})$ and $\alpha\in \mathbb{R}$, $\alpha\cdot \underline{x}=(\alpha x_{1},\ldots,\alpha x_{N})\in \mathbb{R}^{N}$. Therefore $(\mathbb{R}^{N},+,\cdot )$ is a vector space on $\mathbb{R}$. Check it as exercise. Q: how do I check it? I have to show it is closed by addition and scalar multiplication, how in practice? Note: what is the zero of $\mathbb{R}^{N}$? $0_{\mathbb{R}^{N}}=(0,\ldots,0)$ with $N$ zeros.

**Example.** $X=\mathscr{C}(\mathbb{R})=\{f:\mathbb{R}\to\mathbb{R} \text{ continuous}\}$. Is it possible to define a vector space structure on this space? What we need to do is to define the sum and scalar multiplication to make $X$ and $\mathbb{R}$-vector space. Pick $f,g\in X$ and define $f+g=h$ (let me call $h$ the sum of the two, let me choose the convenient one), $h:\mathbb{R}\to\mathbb{R}$, $t\mapsto h(t)=f(t)+g(t)$ (I could put $f(t)+2g(t)$ it would still be a func. and still have the property of the sum, but if you don't do the same thing on $f$ and $g$, you lose commutativity, so it would not be a good def., a good def. would be if I put 2 in front of both and you can check this would produce a sum which is completely lecit), $h\in X$? Yes, because sum of continuous functions is continuous. (It is not enough to ... it has also to be continuous.) So we have a nice def. (internal operation). Now, $f\in X$, $\lambda \in \mathbb{R}$, $\lambda \cdot f:\mathbb{R}\to\mathbb{R}$, $t\mapsto (\alpha \cdot f)(t)=\alpha f(t)$ (this is not the same meaning, product of images vs scalar of the image). Here I do not want $\lambda=2$, because if I multiply $f$ I still want to get $f$ (identity). The result is still continuous (when you play with $\varepsilon$ and $\delta$...). We can take this for granted, $\lambda \cdot f\in X$ (continuous). With these two operations, $X$ is a vector space on $\mathbb{R}$. But to be sure I should check all the properties. What is $0_{X}$? I.e. what is the func. st. when you take the sum of two functions you still get $f$? (It is the func.) $0_{X}:\mathbb{R}\to\mathbb{R}$, $t\mapsto 0_{X}(t)$ st. $f+0_{X}=f\ \ \forall \ f\in X$, i.e. $f(t)+0_{X}(t)=f(t)\ \ \forall \ f\in X,\ \ \forall \ t\in \mathbb{R}$ (1) (I fix $t$, and for any time there is a, continuous, function $f$ which does that). 

"The moon is just a very very big apple" (about common sense, it should fall on Netwon's head just like the apple, but science explains what truly happens).

Given $t\in\mathbb{R}$ (arbitrary, for that choice of that one I am sure I can find a cont. func. which) $f\in X$ s.t. $f(t)\neq 0$ (it doesn't vanish, at that specific point). For that $f$, $(1)\Rightarrow 0_{X}(t)=0$ (has to be zero). Therefore $0_{X}(t)=0\ \ \forall \ t\in\mathbb{R}$. ("O X of t" for any possible choice of the point) i.e. $0_{X}$ is the constant function equal to zero. "It is more complicated than you think, but less complicated than what I said".

You always have to keep in mind what is the def. of the sum, scalar mult. and most importantly the 0 of the space (which can be a bit tricky).

**Example.** $X=\mathscr{C}(I,\mathbb{R})=\{f:I\to\mathbb{R}\text{ continuous}\}$, with $I=[a,b]\subset \mathbb{R}$ (i.e. the space of continuous functions on a closed interval). Sum on $X$: $f\in X$, $g\in X$. $f+g:I\to\mathbb{R}$ is the function which to an element $x\in I$ associates $(f+g)(x)=f(x)+g(x)$. Scalar multiplication: $f\in X$, $\alpha\in\mathbb{R}$. then we have $\alpha\cdot f:I\to\mathbb{R}$ is the function which $x\mapsto (\alpha f)(x)=\alpha f(x)$. Q: is $(X, +,\cdot )$ a vector space on $\mathbb{R}$? What about $0_{X}$? We have $0_{X}:I\to\mathbb{R}$, which to $x$ associates 0. E.g. what happens if we consider $2f+2g$? (what does this mean?)

What is a seminorm? What is a norm?  
**Definition.** Given $X$ an $\mathbb{R}$-vector space. A seminorm on $X$ is a function $\mathcal{N}:X\to\mathbb{R}$ (note, what is important here, on $\mathbb{R}$, is that it is finite) such that:
(1) $\mathcal{N}(x)\geq 0\ \ \forall \ x\in X$ (non-negativity) (alternatively, more correctly $0\leq \mathcal{N}(x)<+\infty$).
(2) $\mathcal{N}(\alpha\cdot x)=\left|\alpha\right|\mathcal{N}(x)\ \ \forall \ \alpha\in\mathbb{R}, \forall \ x\in X$ (homogeneity). Note: $\alpha\mathcal{N}(x)$ would not be true, if $\alpha$ is negative, but it would be true if I take the abs. val. (actually hom. of degree 1 because I have power 1 for the abs. val.)
(3) $\mathcal{N}(x+y)\leq \mathcal{N}(x)+\mathcal{N}(y)\ \ \forall \ x,y\in X$ (triangle inequality) (it would be too strong to have the equality, usually this is not possible, but we can ask this to be less than the sum of the norms).
A seminorm is called a norm if it also satisfies (4) $\mathcal{N}(x)=0\Leftrightarrow  x=0_{X}$ (uniqueness, of the neutral element, i.e. the only element which has norm zero is the zero of the space) (note that $\Leftarrow$ is always true, i.e. when $x$ is the zero of the space, then its norm is zero) then we call the seminorm a norm on $X$.

[$\color{lime}\textbf{Q}$. Is there some relationship between norms and measures?]

If $\mathcal{N}$ is a norm, we usually write (prefer the notation $\lVert \cdot  \rVert$ for $\mathcal{N}$) $\lVert x \rVert=\mathcal{N}(x)$, and the pair $(X, \mathcal{N})=(X,\lVert \cdot  \rVert)$ is called a normed space. In other words, a normed space is a set endowed with a norm, which is a particular function that we defined above and generalizes the notion of distance to more abstract spaces.

Q: I heard ("Beginning functional analysis" p5) that norms always give rise to metrics, what does it mean? Why have norms and metrics if they both generalize distance? (See intructive example p.6) A metric is something more general than a norm right?

Note: once you have a norm you have a notion of topology (sequences, convergence, continuity etc.).

What are some examples of norms?  
**Example.** $X=\mathbb{R}$, $\left|x\right|=\mathcal{N}(x)\ \ \forall \ x\in\mathbb{R}$ then $\mathcal{N}$ is a norm on $\mathbb{R}$, and $(\mathbb{R},\left|\cdot \right|)$ is a normed space. Q: why is this obvious? By def. or construction (properties) of abs val? Yes, the important thing is that any number has a finite absolute value (bec. $+\infty$ and $-\infty$ do not belong to $\mathbb{R}$). $\left|\cdot \right|$ is non-negative, homogeneous $\left|\alpha \cdot x\right|=\left|a\right|\cdot \left|x\right|$ and $\left|a+b\right|\leq \left|a\right|+\left|b\right|$ (this is the triangle inequality which is known to be true for the absolute value), $\forall \ a,b\in\mathbb{R}$. Recall the def. of the abs. val.
$$\left|a\right|=\begin{cases} a & a\geq  0 \\ -a & a<0 \end{cases}$$
and try to recall the proof using the definition (the shortest path between two points is the straight line).

**Example.** On $X=\mathbb{R}^{N}$, $N\geq 2$, i.e.
$$X=\mathbb{R}^{N}=\{\underline{x}=(x_{1},\ldots,x_{N}):x_{i}\in \mathbb{R},i=1,\ldots,n\}=\underbrace{\mathbb{R}\times  \ldots\times  \mathbb{R}}_{N\text{ times}}$$

Set $\lVert \underline{x} \rVert=\sqrt{\sum_{i=1}^{N}x_{i}^{2}}$ with $\underline{x}=(x_{1},\ldots,x_{N})\in \mathbb{R}^{N}$, this is a norm on $X=\mathbb{R}^{N}$ (called Euclidean norm). Indeed: (i) $\lVert \underline{x} \rVert\geq 0\ \ \forall \ \underline{x}\in \mathbb{R}^{N}$ as $\sqrt{\cdot }$, (ii) 
$$\lVert \alpha\cdot \underline{x} \rVert=\sqrt{\sum_{i=1}^{N}(\alpha x)^{2}}=\sqrt{\sum_{i=1}^{N}\alpha_{i}^{2}x_{i}^{2}}=\sqrt{\alpha^{2}}\lVert \underline{x} \rVert=\left|\alpha\right|\lVert \underline{x} \rVert \qquad \ \ \forall \  \underline{x}\in  \mathbb{R}^{N}$$
(iv) $\lVert \underline{x} \rVert=0\iff \sqrt{\sum_{i=1}^{N}x_{i}^{2}}=0$, $\underline{x}=(x_{1},\ldots,x_{N})$ $\iff \sum_{i=1}^{N}\underbrace{x_{i}^{2}}_{\geq 0}=0$ 
$$\iff  x_{i}^{2}=0\ \ \forall \  i=1,\ldots,N\iff  x_{i}=0\ \ \forall \  i=1,\ldots,N\iff  \underline{x}=0_{\mathbb{R}^{N}}$$
(iii) (triangle inequality) Let $\underline{x}=(x_{1},\ldots,x_{N})\in \mathbb{R}^{N}$, $\underline{y}=(y_{1},\ldots,y_{N})\in \mathbb{R}^{N}$ then:
$$\begin{aligned} & \lVert \underline{x}+\underline{y} \rVert^{2}=\sum_{i=1}^{N} (x_{i}+y_{i})^{2}=\sum_{i=1}^{N} (x_{i}^{2}+y_{i}^{2}+2x_{i}y_{i})=\sum_{i=1}^{N} x_{i}^{2}+\sum_{i=1}^{N} y_{i}^{2}+2\sum_{i=1}^{N} x_{i}y_{i}  \\  &  = \lVert \underline{x} \rVert^{2}+\lVert \underline{y} \rVert^{2}+2\sum_{i=1}^{N}x_{i}y_{i} \end{aligned}$$
Q: shouldn't we have the square root somewhere here since we consider euclidean norm? I think yes (like in homogeneity) but just omitted for simplicity, i.e. 
$$\small \lVert x+y \rVert^{2}=\sqrt{\sum_{i=1}^{n}(x_{i}+y_{i})^{2}}=\sqrt{\sum_{i=1}^{n} (x_{i}^{2}+2x_{i}y_{i}+y_{i}^{2})}=\sqrt{\sum_{i=1}^{n} x_{i}^{2}}+\sqrt{\sum_{i=1}^{n} y_{i}^{2}}+\sqrt{2\sum_{i=1}^{n} x_{i}y_{i}}$$
Wait, this above is wrong, that is the computation of $\lVert x+y \rVert$, not $\lVert x+y \rVert^{2}$. Precisely because we compute the square of the norm, we get rid of the square root. Nevermind.

Now the question is, is this, i.e. $\lVert \underline{x}+\underline{y} \rVert^{2}$, $\leq (\lVert \underline{x} \rVert+\lVert \underline{y} \rVert)^{2}$? First of all 
$$(\lVert \underline{x} \rVert+\lVert \underline{y} \rVert)^{2}=\lVert \underline{x} \rVert^{2}+\lVert \underline{y} \rVert^{2}+2\lVert \underline{x} \rVert\lVert \underline{y} \rVert$$
so if we are able to prove that $\sum_{i=1}^{N}x_{i}y_{i}\leq 2\lVert \underline{x} \rVert\lVert \underline{y} \rVert\ \ \forall \ \underline{x},\underline{y}\in X$ then the triangle inequality would hold. For simplicity, let us denote by $\langle \underline{x} , \underline{y} \rangle=\sum_{i=1}^{N}x_{i}y_{i}$ where $\underline{x}=(x_{1},\ldots,x_{N})$, $\underline{y}=(y_{1},\ldots,y_{N})$. Let us prove that $\left|\langle \underline{x} , \underline{y} \rangle\right|\leq \lVert \underline{x} \rVert \lVert \underline{y} \rVert\ \ \forall \ \underline{x},\underline{y}\in \mathbb{R}^{N}$ (i.e. the Cauchy-Schwarz inequality in $\mathbb{R}^{N}$). Set $g(t)=\lVert \underline{x}+t\underline{y} \rVert^{2}$, $t\in\mathbb{R}$, ($\underline{x}, \underline{y}$ are fixed). Then 
$$\begin{aligned} & 0\leq g(t)=\lVert \underline{x}+t\underline{y} \rVert^{2}=\sum_{i=1}^{N}(x_{i}+ty_{i})^{2}=\sum_{i=1}^{N}x_{i}^{2}+t^{2}\sum_{i=1}^{N}y_{i}^{2}+2t^{2}\sum_{i=1}^{N}x_{i}y_{i}\\ & =\lVert \underline{x} \rVert^{2}+t^{2}\lVert \underline{y} \rVert^{2}+2t\langle \underline{x} , \underline{y} \rangle  \end{aligned}$$
Now, let $a=\lVert \underline{y} \rVert^{2}$, $b=2\langle \underline{x} , \underline{y} \rangle$, $c=\lVert \underline{x} \rVert^{2}$, $0\leq g(t)=at^{2}+b+c\ \ \forall \ t\in\mathbb{R}$, i.e. we have an upward quadratic function (parabola), $\Delta\leq 0$, $\Delta=b ^{2}-4ac\leq 0$ so $4\langle \underline{x} , \underline{y} \rangle^{2}-4\lVert \underline{x} \rVert^{2}\lVert \underline{y} \rVert^{2}\leq 0$ which means $\left|\langle \underline{x} , \underline{y} \rangle\right|\leq \lVert \underline{x} \rVert\lVert \underline{y} \rVert$ (CS). $\square$
Note: another norm on $X=\mathbb{R}^{N}$ would be (2) $\lVert \underline{x} \rVert_{1}=\sum_{i=1}^{N}\left|x_{i}\right|$, $\underline{x}=(x_{1},\ldots,x_{N})$ if we do this, this is also a norm on $\mathbb{R}^{N}$, i.e. $(\mathbb{R}^{N},\lVert \cdot \rVert_{1})$ is a normed space.
(3) Setting $\lVert \underline{x} \rVert_{\infty}=\max_{1\leq i\leq N}\left|x_{i}\right|$ (i.e. the largest component), where (again) $\underline{x}=(x_{1},\ldots,x_{N})$, then $(\mathbb{R},\lVert \cdot  \rVert_{\infty})$ is a normed space. Let us check it.

(2) Non-negativity is obvious (sum of absolute values, absolute values are nonnegative, if you sum they it becomes less nonnegative), $\lVert \underline{x} \rVert\geq 0\ \ \forall \ \underline{x}\in \mathbb{R}^{N}$. Homogeneity: $\lVert \alpha\underline{x} \rVert_{1}=\sum_{i=1}^{N}\left|\alpha x_{i}\right|=\sum_{i=1}^{N}\left|\alpha\right|\left|x_{i}\right|$ (property of the abs val) $=\left|\alpha\right|\sum_{i=1}^{N}\left|x_{i}\right|$ which is exacty $=\left|\alpha\right|\lVert \underline{x} \rVert_{1}$. Triangle ineq.: $\lVert \underline{x}+\underline{y} \rVert=\sum_{i=1}^{N}\left|x_{i}+y_{i}\right|$ but I know $\forall \ i$, $\left|x_{i}+y_{i}\right|\leq \left|x_{i}\right|\left|y_{i}\right|$, so $\leq \sum_{i=1}^{N}(\left|x_{i}\right|+\left|y_{i}\right|)$ and from this we go there $\lVert \underline{x}+\underline{y} \rVert\leq \sum_{i=1}^{N}\left|x_{i}\right|+\sum_{i=1}^{N}\left|y_{i}\right|=\lVert \underline{x} \rVert_{1}+\lVert \underline{y} \rVert_{1}$. This tells us that this is a seminorm, but we would like to know if it is a norm. Uniqueness: asking the norm to be zero is asking $\lVert \underline{x} \rVert_{1}\Leftrightarrow \sum_{i=1}^{N}\left|x_{i}\right|=0$ (the only way for this to be true is that all of them are zero) $\Leftrightarrow \left|x_{i}\right|=0\ \ \forall \ i\Leftrightarrow x_{i}=0\ \ \forall \ i\Leftrightarrow \underline{x}=(0,\ldots,0)=0_{X}$. So we proved $\lVert \cdot \rVert_{1}$ is a norm. 

**Exercise.** Do the same for $\lVert \cdot \rVert_{\infty}$ and try the same for the Euclidean norm (triangle ineq. a bit tricky, because you have srt outside of the sum).

Q: what is the logic behind the very first step in both homogeneity and triangle inequality in the previous example? We consider $x+y$ as a new element, and $\alpha x$ as a new element? Yes, you can call it z if you want for simplicity.

**Example.** $X=\mathbb{R}^{N}$, define $\lVert \underline{x} \rVert_{1}=\sum_{i=1}^{N}\left|x_{i}\right|$, and $\lVert \underline{x} \rVert_{\infty}=\max_{1\leq i\leq N}\left|x_{i}\right|$ with $\underline{x}=(x_{1},\ldots,x_{N})$, these two are norms on $\mathbb{R}^{N}$.

Q: can you make a visual/stupid computation example of the difference between this norms in $\mathbb{R}^{n}$?

**Example.** (Space of sequences, which are absolutely summable) $\underline{x}=(x\_{n})\_{n}$, $\underline{y}=(y_{n})_{n}$ real sequences. The sum is $\underline{x}+\underline{y}=(x_{n}+y_{n})_{n}$ real sequence, and the scalar multiplication is $\lambda \cdot \underline{x}=(\lambda x_{n})_{n}$ real sequence $\forall \  \lambda\in\mathbb{R}$. Now, consider 
[$\color{lime}\textbf{Q}$. So with this definition below for example the sequence $(\frac{1}{n})$ is not in $X=\ell^{1}$, correct?]
$$X:=\ell^{1}(\mathbb{N})=\left\{ \underline{x}=(x_{n})_{n}\subset \mathbb{R}\ : \ \sum_{n=1}^{\infty}\left|x_{n}\right|<\infty \right\}$$
$(X,+,\cdot )$ is a vector space on $\mathbb{R}$ since given $\underline{x}=(x_{n})_{n}\in X$, $\underline{y}=(y_{n})_{n}\in X$ we have $\underline{x}+\lambda\underline{y}=(x_{n}+\lambda y_{n})_{n}$ for $\lambda\in\mathbb{R}$ which is in $X$ since 
$$\sum_{i=1}^{\infty} \left|x_{n}+\lambda y_{n}\right|\leq  \sum_{i=1}^{\infty} (\left|x_{n}\right|+\left|\lambda\right|\left|y_{n}\right|)=\underbrace{\sum_{n=1}^{\infty} \left|x_{n}\right| }_{ <\infty }+\left|\lambda\right|\underbrace{ \sum_{n=1}^{\infty} \left|y_{n}\right| }_{ <\infty }$$
then $\underline{x}+\lambda\underline{y}\in \ell^{1}(\mathbb{N})$.

**Exercise.** Prove that $(\ell^{1},\lVert \cdot  \rVert_{1})$ is a normed space (where $\lVert \underline{x} \rVert_{1}=\sum_{n=1}^{\infty}\left|x_{n}\right|$).  

**Example.** $X=\mathscr{C}(I)=\{f:I\to\mathbb{R}\text{ continuous}\}$, $I=[a,b]$. Define $\lVert f \rVert_{\infty}=\sup_{t\in I}\left|f(t)\right|$ (the supremum norm, also called uniform norm) for $f\in X$ and 
$$\lVert f \rVert_{1}=\int_{a}^{b} \left|f(t)\right|dt=\int_{[a,b]} \left|f\right|dt$$
$(X,\lVert \cdot  \rVert_{\infty})$ and $(X,\lVert \cdot  \rVert_{1})$ are normed spaces. **Exercise.** check it!

Hints: $\lVert f \rVert_{\infty}<\infty$ (Weierstrass theorem, $I=[a,b]$), $\lVert f \rVert_{1}<\infty$ (classical result in integral calculus, the Riemann integral of a continuous function on some finite interval is well-defined and finite) $\forall \ f\in X$, $\lVert \cdot  \rVert_{\infty}$ and $\lVert \cdot  \rVert_{1}$ are seminorms (easy exercise), indeed (proof of uniqueness, so proof that they are norms)
$$\lVert f \rVert_{\infty}=0\iff \sup_{t\in  I}\left|f(t)\right|=0\iff  \left|f(t)\right|=0\ \ \forall \  t \iff  f(t)=0\ \ \forall \  t\in  I \iff  f=0_{X}$$
(i.e. the supremum norm of $f$ is zero if and only if $f$ is the function which is constantly equal to 0 for each point in the interval). For $\lVert f \rVert_{1}$ we have 
$$\lVert f \rVert_{1}=0\Leftrightarrow  \int_{a}^{b} \left|f(t)\right|dt=0\Leftrightarrow  \left|f(t)\right|=0\ \ \forall \  t\in  [a,b]$$
(which is a property of continuous functions) $\Leftrightarrow  f=0_{X}$.



