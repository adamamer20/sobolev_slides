### Theorem 2 — Sobolev embedding on a bounded domain

**Setting**

* Let $U\subset\mathbb{R}^{n}$ be **bounded** with **$C^{1}$** boundary.
* Fix $1\le p<n$ and write

  $$
    p^{\star}\;=\;\frac{np}{n-p}.
  $$
* Assume $u\in W^{1,p}(U)$ (so **finite set of discontinuities** allowed).
* Bound is larger because no compact support

> **Goal (full‐norm Sobolev bound)**
>
> $$
  \boxed{\;
     \|u\|_{L^{p^{\star}}(U)}
     \;\le\;
     C\,\bigl(
       \|u\|_{L^{p}(U)}\;+\;\|Du\|_{L^{p}(U)}
     \bigr)
     \;=\;
     C\,\|u\|_{W^{1,p}(U)}
   \;}
 $$

---                     

## 1.  Extension to $\mathbb{R}^{n}$

We need to extend $u$ because GNS THM is stated for functions in $R^n$.

### 1.1  Why naïve zero–extension fails

If $u\not=0$ on $\partial U$, the function

$$
  \bar u(x)=
  \begin{cases}
    u(x), & x\in U,\\[2pt]
    0, & x\notin U
  \end{cases}
$$

has a **jump discontinuity** on $\partial U$.  The gradient picks up delta‐type singularities, so $\bar u\notin W^{1,p}(\mathbb{R}^{n})$.  Hence we first need a *genuine* $W^{1,p}$-extension.

### 1.2  Extension theorem $(E)$

> **Theorem A (Extension operator).**
> There is a bounded linear map
>
> $$
  E:W^{1,p}(U)\;\longrightarrow\;W^{1,p}(\mathbb{R}^{n})
 $$
>
> and a bounded open set $V\supset\overline U$ such that for every $u\in W^{1,p}(U)$
>
> 1. $Eu=u$ a.e. on $U$;
> 2. $\operatorname{supp}(Eu)\subset V$;
> 3. $\displaystyle\|Eu\|_{W^{1,p}(\mathbb{R}^{n})}\le C\,\|u\|_{W^{1,p}(U)}.$


In practice one can take

$$
  Eu \;=\;\varphi\,u,
  \qquad 
  \varphi\in C_{c}^{\infty}(V),\;
  \varphi\equiv1\;\text{on }U.
$$

*Trade-off note* A **sharper** cutoff kills the support quickly but has large $\|D\varphi\|_{\infty}$;
a **smoother** cutoff has small $\|D\varphi\|$ but larger support.

Set

$$
  \widetilde u \;:=\; Eu\;\in\;W^{1,p}(\mathbb{R}^{n}).
$$

By the weak product rule

$$
  D(\varphi\,u)=\varphi\,Du + u\,D\varphi,
$$

so
$$
\lVert D\widetilde u\rVert_{L^p(\R^n)}
\;\le\;
\lVert Du\rVert_{L^p(U)}
\;+\;\|D\varphi\|_{L^\infty}\,\lVert u\rVert_{L^p(U)}.
$$
---

## 2. Local mollification (smooth approximation)

The other assumption we need to apply Theorem 1 is to have a continuously differentiable function.

Choose a standard mollifier $\eta\in C\_{c}^{\infty}(B(0,1))$, $\eta\ge0$, $\displaystyle\int\_{\R^{n}}\eta=1$.
For $\varepsilon>0$, put

$$
\eta_{\varepsilon}(x) \;=\; \varepsilon^{-n}\,\eta\bigl(x/\varepsilon\bigr)
$$

and define

$$
u_{\varepsilon} \;=\; \eta_{\varepsilon}\ast\widetilde u.
$$

* **Support:** $\operatorname{supp}(u\_{\varepsilon})\subset V$.
* **Smoothness:** $u\_{\varepsilon}\in C\_{c}^{\infty}(\R^{n})$.
* **Convergence:** $u\_{\varepsilon}\to \widetilde u$ in $W^{1,p}(\R^{n})$ as $\varepsilon\to0$.

Finally, reindex by setting $m = 1/\varepsilon$.  Then ${u\_{m}}*{m\in\N}\subset C*{c}^{\infty}(\R^{n})$ and

$$
u_{m}\;\to\;\widetilde u 
\quad\text{in }W^{1,p}(\R^{n}) 
\quad\text{as }m\to\infty.
$$

## 3. Whole‐space Sobolev on each $u_{m}$

### 3.1. Why we cannot apply Theorem 1 directly to $u_{m}$

If we naively apply Theorem 1 (the homogeneous Gagliardo–Nirenberg–Sobolev inequality on $\mathbb{R}^n$) to each $u_{m}$, we get

$$
\|\,u_{m}\|_{L^{p^{*}}(\mathbb{R}^{n})}
\;\le\;
C\,\|\nabla u_{m}\|_{L^{p}(\mathbb{R}^{n})}
\quad\text{for every }m,
$$

where $p^{*}=\tfrac{n\,p}{\,n-p\,}$.  Letting $m\to\infty$ shows only that
$\{u_{m}\}$ is bounded in $L^{p^{*}}(\mathbb{R}^{n})$.  Boundedness in $L^{p^{*}}$ does **not** imply convergence in $L^{p^{*}}$.  In other words, from
$\|u_{m}\|_{L^{p^{*}}}\le C\,\|\nabla u_{m}\|_{L^{p}}$
we obtain
$\sup_{m}\|u_{m}\|_{L^{p^{*}}}<\infty$, but we do not know that $u_{m}\to \widetilde u$ in $L^{p^{*}}$.
To conclude convergence in $L^{p^{*}}$, we must show $\{u_{m}\}$ is Cauchy in $L^{p^{*}}$.  The standard approach is to apply Theorem 1 not to $u_{m}$ alone but to the difference $u_{m}-u_{\ell}$ for $m,\ell\in\mathbb{N}$.

---

### 3.2. Applying Theorem 1 to the difference $u_{m}-u_{\ell}$

Since $\{\nabla u_{m}\}$ is Cauchy in $L^{p}(\mathbb{R}^{n})$, for every $\varepsilon>0$ there exists $M$ such that whenever $m,\ell\ge M$,

$$
\|\nabla u_{m} - \nabla u_{\ell}\|_{L^{p}(\mathbb{R}^{n})}
\;<\;\varepsilon / C,
$$

where $C$ is the constant from Theorem 1.  Now $u_{m}-u_{\ell}\in C_{c}^{\infty}(\mathbb{R}^{n})$, so Theorem 1 gives

$$
\bigl\|\,u_{m} - u_{\ell}\bigr\|_{L^{p^{*}}(\mathbb{R}^{n})}
\;\le\;
C\,\bigl\|\nabla\bigl(u_{m} - u_{\ell}\bigr)\bigr\|_{L^{p}(\mathbb{R}^{n})}
\;=\;
C\,\|\nabla u_{m} - \nabla u_{\ell}\|_{L^{p}(\mathbb{R}^{n})}
\;<\;C \cdot \frac{\varepsilon}{C} 
\;=\;\varepsilon.
$$

Hence $\{u_{m}\}$ is Cauchy in $L^{p^{*}}(\mathbb{R}^{n})$.  Since $L^{p^{*}}(\mathbb{R}^{n})$ is complete, there exists

$$
v \;\in\; L^{p^{*}}(\mathbb{R}^{n})
\quad\text{with}\quad
u_{m}\;\longrightarrow\;v 
\quad\text{in }L^{p^{*}}(\mathbb{R}^{n}).
$$

---

### 3.3. Identifying the limit and concluding

We already know $u_{m}\to \widetilde u$ in $L^{p}(\mathbb{R}^{n})$, so by passing to a subsequence if necessary, $u_{m}\to\widetilde u$ almost everywhere.  Likewise, $u_{m}\to v$ in $L^{p^{*}}$ implies a further subsequence converges almost everywhere to $v$.  By uniqueness of almost‐everywhere limits, $v=\widetilde u$ a.e., and therefore

$$
u_{m}\;\longrightarrow\;\widetilde u 
\quad\text{in }L^{p^{*}}(\mathbb{R}^{n}),
\quad\text{so in particular }\widetilde u\in L^{p^{*}}(\mathbb{R}^{n}).
$$

Since $\widetilde u = E(u)$ agrees with $u$ on $U$, we conclude $u\in L^{p^{*}}(U)$.  Finally, apply Theorem 1 once more to $\widetilde u$:

$$
\|\widetilde u\|_{L^{p^{*}}(\mathbb{R}^{n})}
\;\le\;
C\,\|\nabla \widetilde u\|_{L^{p}(\mathbb{R}^{n})}.
$$

Because the extension operator $E\colon W^{1,p}(U)\to W^{1,p}(\mathbb{R}^{n})$ satisfies
$\|\nabla \widetilde u\|_{L^{p}(\mathbb{R}^{n})}\le C'\,\|u\|_{W^{1,p}(U)},$
we obtain

$$
\|u\|_{L^{p^{*}}(U)}
\;=\;\|\widetilde u\|_{L^{p^{*}}(\mathbb{R}^{n})}
\;\le\;
C\,\|\nabla \widetilde u\|_{L^{p}(\mathbb{R}^{n})}
\;\le\;
C\,C'\,\|u\|_{W^{1,p}(U)}.
$$

Setting $C''=C\,C'$ yields the desired estimate in Theorem 2:

$$
\|u\|_{L^{p^{*}}(U)} \;\le\; C''\,\|u\|_{W^{1,p}(U)}.
$$

This completes the proof of Theorem 2.


## Conclusion

By carefully **extending** first (to avoid boundary jumps) and **mollifying** second (to apply the whole-space Sobolev inequality), we arrive at the desired full $W^{1,p}$-norm Sobolev embedding on the bounded domain $U$.  The extra $\|u\|_{L^{p}}$-term is unavoidable unless we impose a zero-trace condition, which is precisely the setting of Theorem 3.