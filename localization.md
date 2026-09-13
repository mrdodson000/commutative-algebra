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

To expand on what we mean by taking $M \times U$ modulo "the relation that the elements of $U$ would satisfy if they were invertible", notice that if all the elements of $U$ were invertible, then there exists $v \in U$ such that $v(u'm - um')$ if and only if $mu^{-1} = m'(u')^{-1}$. Since we want the ordered pair $(m, u)$ to correspond to the element $mu^{-1}$, or $\frac{m}{u}$, we must identify all ordered pairs such that this relation holds. 

## Some Properties of the Localized Module
Firstly, it can, in fact, be made into an $R$-module. We define:
$$
\frac{m}{u} + \frac{m'}{u'} = \frac{u'm + um'}{uu'} \\
$$
$$
r\left(\frac{m}{u}\right) = \frac{(rm)}{u}
$$
These definitions should be familiar from the case of $\mathbb{Q}$, but let us try to see why they make sense. In particular the bit that is a little bit confusing is to remember why addition should be defined that way. The thing you ought to remember is that we must have that if $(m_1, u_1) \sim (m_2, u_2)$ then for any $(m', u')$,
$$
(u'm_1+u_1m', u_1u') \sim (u'm_2+u_2m', u_2u')
$$
Once you remember that this is what you have to check, it is easy to verify.

There is a natural map of $R$-modules $M \to M[U^{-1}]$ given by $m \mapsto m / 1$, as one would expect. We will also define $M[U^{-1}]$ for an arbitrary subset $U$ of $R$. In this case, one simply takes the localization with respect to the multiplicative closure of $U$. We should also note that if $M = R$, then we can make $R[U^{-1}]$ into a ring where the addition is as above and the multiplication is:
$$
\left(\frac{r}{u}\right)\left(\frac{r'}{u'}\right) = \frac{rr'}{uu'}
$$
Again, it is not too hard to see that this makes sense and that this forms a ring. In this case, we find that in fact $M[U^{-1}]$ is actually a $R[U^{-1}]$-module with the action given by:
$$
\frac{r}{u}\left(\frac{m}{u'}\right) = \frac{rm}{uu'}
$$
One has to do two checks here to make sure that this is well defined both for any choice of representative of $m / u'$ as well as any choice of representative of $r / u$. As before, it is not hard. This fact is useful, so we best not forget it.

Finally, we have a useful proposition about localized modules.
**Proposition:** Let $U$ be a multiplicatively closed subset of $R$ and let $M$ be an $R$-module. An element $m \in M$ goes to $0$ under the natural map if and only if $m$ is annihilated by some element of $U$. Furthermore, if $M$ is finitely generated, then $M[U^{-1}] = 0$ if and only if $M$ is annihilated by some element of $U$.

*Proof.* The first claim is easy because if $m / 1 = 0$ then by construction we have that there exist $v$ and $u$ in $U$ so that $v(um - 0) = 0$. Since $U$ is multiplicatively closed, $vu$ is an element of $U$ and it clearly annihilates $m$. For the second claim, note that if $M[U^{-1}] = 0$, then by the previous fact its generators must be annihilated by elements of $U$. Suppose that $m_i$ is annihilated by $u_i$. Then, we see that $\prod u_i$ annihilates every element of $M$. And conversely (obvious).

## Examples of Localization
**Example 1:** If $R$ is an integral domain, then $U = R \setminus \{0\}$ is multiplicatively closed. We call $R[U^{-1}]$ the **total quotient ring**, or as I have heard it, the ring of fractions, of $R$ and denote it $K(R)$. For instance, $K(\mathbb{Z}) = \mathbb{Q}$, so this is quite a fundamental construction.

**Example 1.5:** Even if $R$ is not an integral domain, we can consider the set $U$ of all non-zero-divisors of $R$. This is again multiplicatively closed and so in this case we can say that $K(R) = R[U^{-1}]$. What is useful about this construction is that it is the largest localization we can take while $R \to R[U^{-1}]$ is an injection under the natural map (since, if we added any more elements to $U$, we would have elements that are annihilated and so map to $0$ in $R[U^{-1}]$).

**Example 2:** Let $P$ be a prime ideal, then by definition $R \setminus P$ is multiplicatively closed. This is a situation of considerable importance and so we give it special notation. If $U = R \setminus P$, then we write $R_P$ for $R[U^{-1}]$ and $M_P$ for $M[U^{-1}]$. We will write $\kappa(P)$ for $R_P / P_P$ and call this the **residue class field**. For instance, if $R$ is an integral domain as before $\kappa(0) = K(R)$.

As a sanity check, the reason this works is because $R_0$ is exactly $K(R)$ and then $0_0 = 0$ since under our equivalence relation, every element of this localized ideal is exactly the same.

**Example 3:** We discussed above what localizing "around" $p \in \mathbb{A}^1_k$ by a single function $f$ in $k[x]$, not vanishing at $p$, does geometrically. To recap, it lets us look at the ring corresponding to the open neighborhood of $p$ given by $X \setminus V(f)$. We now have the definitions to inspect the ring corresponding to an arbitrarily small open neighborhood of $p$. Let $P$ be the ideal of functions vanishing at $p$. This ideal is prime, since if $fg(p) = 0$ then at least one of $f$ or $g$ must vanish. Then, $A(X)_P$ is the local ring at $p$. For now, there is no clear geometric object that $A(X)_P$ corresponds to, since $X$ minus the union of vanishing sets of all functions not vanishing at $p$ is just $\{p\}$. Astra tells me that in the land of schemes ahead, there will be such an object, though. For now, we should think of this as representing the limiting behavior of an arbitrarily small open neighborhood of $p$.  

## Some Categorical Features of Localization
There are a number of "categorical" implications of localization. Proving these shall make our lives much easier going forward. 

We begin with the observation that if $\varphi : M \to N$ is a map of $R$-modules, then there is naturally a map $\varphi[U^{-1}] : M[U^{-1}] \to N[U^{-1}]$ of $R[U^{-1}]$-modules given by $m / u \mapsto \varphi(m) / u$. We call this induced map the **localization of $\varphi$**. Thus, localizing by $U$ is a functor from the category of $R$-modules to the category of $R[U^{-1}]$-modules. We shall show that if $M$ is finitely presented, then every homomorphism between $M[U^{-1}]$ and $N[U^{-1}]$ is a localization. This is not obvious! Additionally, we shall see that many important categorical operations, such as direct sums, are preserved by this functor. 