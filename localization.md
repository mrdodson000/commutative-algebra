# Localization
## The Geometric Idea of Localization
This is a somewhat confusing idea, so let us try to digest it. Let $p \in X$, with $X$ being an affine algebraic set. We may, and evidently often do, want to understand the way that $X$ behaves "near" $p$. For this, we want to study arbitrarily small open neighborhoods of $p$. In the Zariski topology, such an open neighborhood is of the form $X \setminus Y$ for some algebraic set $Y$ (being closed in that topology, as one will recall). If the neighborhood of $p$ is sufficiently small, then $Y$ will be a large algebraic set. Thus, we may assume that $Y$ is the vanishing set of exactly one function $f$ that does not vanish at $p$. It will turn out that in this case, $X \setminus Y$ will be an affine algebraic set and so $A(X \setminus Y)$ will be a coordinate ring. As we will see, we will obtain $A(X \setminus Y)$ from $A(X)$ by adjoining a multiplicative inverse for $f$.

## An Example of Geometric Localization
As before, let $Y$ be the vanishing set of one polynomial $f$ in $k[x_1, ..., x_n]$. In particular, suppose $x \in X \setminus Y$. Then $f(x) \neq 0$ and so there exists some number $y \in k$ such that $yf(x) = 1$. We can consider the function $z(x)$ such that $z(x)f(x) = 1$. We wish for $z(x)$ to be a regular (i.e. polynomial) function. For now, let us pretend that it is.
We then say that if $X$ corresponds to the ideal $I \in k[x_1, ..., x_n]$, then $X \setminus Y$ corresponds to the ideal 
$$
J = I + (zf - 1) \in k[x_1, ..., x_n, z]
$$
Does this actually make any sense? Yes, I think so. The way I am currently conceptualizing this is that the $I$ in that expression ensures that the geometric object we obtain has the same "shape" as the one we had before. For example, if $X$ is a curve in $\mathbb{A}^2_k$, then the projection of V(J) onto $\mathbb{A}^2_k$ will be the same curve, with the points of $Y$ removed. Then, the component $(zf - 1)$ serves to annihilate all points of $Y$. Since $f = 0$ on $Y$, there are no points $z$ that can give $zf = 1$ and so when we do the projection back onto $\mathbb{A}^2_k$ (for example) those points in $Y$ will just be absent.
In terms of rings, we have that
$$
A(X \setminus Y) = A(X)[z]/(zf - 1)
$$
This is the "freest" way to adjoin an inverse of $f$.

## Fractions
In general, we will invert many polynomials at the same time to create the local ring. Since if we invert $f$ and $g$, we get an inverse for their product for free, we will look at adjoining the inverses for entire multiplicatively closed sets $U$ at once. One detail of note is that we require the result of the empty product to be in $U$, i.e. $1 \in U$. The definition for how we perform this adjoining will be motivated by the idea of creating fractions of the form $r/u$ with $r \in R$ and $u \in U$. We can do this arbitrarily by considering pairs $(r, u)$ modulo the relations that elements of $U$ would satisfy if they were invertible.
**Definition:** Let $R$ be a ring, $M$ an $R$-module, and $U$ a multiplicatively closed subset of $R$. Then, we define the **localization of $M$ at $U$**, written $M[U^{-1}]$, to be the equivalence class of pairs $(m, u)$ modulo the following equivalence relation: $(m, u) \sim (m', u')$ if there exists $v \in U$ such that $v(u'm - um') = 0$.
