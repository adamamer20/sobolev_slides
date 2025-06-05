## Theorem 3 (Zero‐trace Sobolev embedding)

**Assume**

1. $U \subset \mathbb{R}^n$ is bounded with $\partial U \in C^1$.
2. $1 \le p < n$ and

   $$
     p^* \;=\; \frac{n\,p}{\,n - p\,}.
   $$
3. $u \in W^{1,p}_0(U)$.

**Conclusion**
For every $1 \le q \le p^*$ there exists a constant

$$
  C = C\bigl(n,p,q,|U|\bigr)
$$

such that

$$
  \lVert u\rVert_{L^q(U)} 
  \;\le\; 
  C\,\lVert \nabla u\rVert_{L^p(U)}.
$$

In particular, when $q = p^*$ one has

$$
  \lVert u\rVert_{L^{p^*}(U)} 
  \;\le\; 
  C\,\lVert \nabla u\rVert_{L^p(U)}.
$$

---

### 1. Approximation by $C_c^\infty(U)$

Since $u\in W^{1,p}_0(U)$, choose

$$
  \{u_m\}_{m=1}^\infty 
  \;\subset\; 
  C_c^\infty(U)
  \quad\text{with}\quad
  u_m \;\longrightarrow\; u 
  \;\text{in }W^{1,p}(U).
$$

Thus

* $u_m \to u$ in $L^p(U)$.
* $\nabla u_m \to \nabla u$ in $L^p(U)$.
* ${supp}(u_m)\subset U$.

---

### 2. Zero‐extension to $\mathbb{R}^n$

Define

$$
  \overline{u}_m(x)
  :=
  \begin{cases}
    u_m(x), & x \in U,\\
    0, & x \notin U.
  \end{cases}
$$

Since $u_m\equiv0$ near $\partial U$,

1. $\overline{u}_m \in C_c^\infty(\mathbb{R}^n)$.
2. $\nabla \overline{u}_m(x)=\nabla u_m(x)$ on $U$ and $0$ off $U$, so

   $$
     \lVert \nabla \overline{u}_m\rVert_{L^p(\mathbb{R}^n)}
     = 
     \lVert \nabla u_m\rVert_{L^p(U)}.
   $$


---

### 3. Apply whole‐space Sobolev + limit argument

**(Identical to Theorem 2.)**

$$
  \boxed{\;
    \lVert u\rVert_{L^{p^*}(U)}
    \;\le\; 
    C_0(n,p)\,\lVert \nabla u\rVert_{L^p(U)}.
  \tag{1}}
$$

---

### 4. Extension to $1 \le q < p^*$

Since $\lvert U\rvert<\infty$, by *Lyapunov's inequality* for $1 \le q < p^*$ we have

$$
  \lVert u\rVert_{L^q(U)}
  \;\le\; 
  \lvert U\rvert^{\,\frac{1}{q} - \frac{1}{p^*}}\,
  \lVert u\rVert_{L^{p^*}(U)}.
$$

Combining with $(1)$ yields, for each $1 \le q \le p^*$:

$$
  \lVert u\rVert_{L^q(U)}
  \;\le\;
  \lvert U\rvert^{\,\frac{1}{q} - \frac{1}{p^*}}\,
  \bigl\lVert u\bigr\rVert_{L^{p^*}(U)}
  \;\le\;
  C_0(n,p)\,\lvert U\rvert^{\,\frac{1}{q} - \frac{1}{p^*}}\,
  \lVert \nabla u\rVert_{L^p(U)}.
$$

Set

$$
  C\bigl(n,p,q,|U|\bigr)
  \;=\; 
  C_0(n,p)\;\lvert U\rvert^{\,\frac{1}{q} - \frac{1}{p^*}}.
$$

Then

$$
  \boxed{\;
    \lVert u\rVert_{L^q(U)}
    \;\le\; 
    C\bigl(n,p,q,|U|\bigr)\,
    \lVert \nabla u\rVert_{L^p(U)},
    \quad 1 \le q \le p^*.
  \tag{2}}
$$

This completes the proof of Theorem 3.
