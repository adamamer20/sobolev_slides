---
theme: seriph
background: '#5d8392'
title: Sobolev Embeddings on a Bounded Domain
info: |
  ## Sobolev Embeddings on a Bounded Domain
  Presentation on Theorem 2, Theorem 3, and PDE Application
class: text-center text-white  
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Sobolev Embeddings on a Bounded Domain

**Theorem 2: Bounded Domain Embedding**  
**Theorem 3: Zero-Trace Embedding**  
**Application: Global Existence for Semilinear Heat Equation**

---

# Overview

- **Theorem 2**: Sobolev embedding on bounded domains
  - Extension and mollification technique
  - Full $W^{1,p}$-norm bound

- **Theorem 3**: Zero-trace Sobolev embedding  
  - Better bounds for $W_0^{1,p}$ functions
  - Only gradient norm needed

- **Application**: Semilinear heat equation
  - Global existence via energy methods

---

# Theorem 2: Sobolev Embedding on Bounded Domain 
 
&emsp;

**Assumptions**:
- $U \subset \mathbb{R}^n$ bounded with $C^1$ boundary
- $u\in W^{1,p}(U)$
- $1 \leq p < n$, $p^* = \frac{np}{n-p}$


**Goal**: For $u \in W^{1,p}(U)$, prove

$$
\boxed{
\|u\|_{L^{p^*}(U)} \leq C \|u\|_{W^{1,p}(U)}
}
$$


**Challenge**: Cannot apply GNS directly
- We Need extension + mollification

<!-- 
- We can allow a finite set of discontinuties thanks to sobolev space
- Bound is larger because no compact support. Decompose the effect of the norms
 -->

---

# Step 1: Extension to $\mathbb{R}^n$

- **Problem**: Naive zero-extension fails if $u \neq 0$ on $\partial U$

- **Solution**: Use Sobolev Extension Theorem 
  
&emsp;There exist an operator $E: W^{1,p}(U) \to W^{1,p}(\mathbb{R}^n)$

$$
Eu = \varphi \cdot u, \quad \varphi \in C_c^\infty(V), \quad \varphi \equiv 1 \text{ on } U
$$


**Properties**:
- $Eu = u$ a.e. on $U$
- $\text{supp}(Eu) \subset V (V \supset  U)$
- $\|Eu\|_{W^{1,p}(\mathbb{R}^n)} \leq C \|u\|_{W^{1,p}(U)}$
- $D(\varphi\,u)=\varphi\,Du + u\,D\varphi \;\;\Longrightarrow\;\; \|D E u\|_{L^p(\mathbb{R}^n)} \le \|Du\|_{L^p(U)} + \|D\varphi\|_{L^\infty(\mathbb{R}^n)}\,\|u\|_{L^p(U)}$

<br>

Set $\bar{u} := Eu \in W^{1,p}(\mathbb{R}^n)$

<!-- 
- Naive zero-extension fails because of jump discontinuties
- In practice we take phi such that 0<phi<1 in V\U
- Cutoff Tradeoff : Sharper = larger gradient. Smoother = larger support.
 -->

---

# Step 2: Mollification

- **Problem**: We need a function in $C_c^\infty$ to apply whole-space Sobolev theorem

- **Solution**: Use Mollification 

1. Choose mollifier $\eta \in C_c^\infty(B(0,1))$, $\eta \geq 0$, $\displaystyle \int_{\R^n} \eta = 1$


2. Local version:
   $$
   \forall{\varepsilon}>0, \space
   \eta_{\varepsilon}(x)
   \;=\; 
   \varepsilon^{-n}\,\eta\!\Bigl(\frac{x}{\varepsilon}\Bigr)
   $$

3. Convolve with $\bar u$: 
  $$
  \bar u_\varepsilon(x) \;=\; (\eta_\varepsilon * \bar u)(x) \;=\; \int_{\mathbb{R}^n} \eta_\varepsilon(x - y)\,\bar u(y)\,dy \;\to\; \bar u \;\text{in }W^{1,p}(U)\quad(\varepsilon \to 0)
  $$



4. Reindex by integers: set  
   $$
   u_m \;=\; \bar u_{\,1/m}, 
   \quad m \in \mathbb{N}.
   $$

<!-- 
- u_e in C^c infinity by compact support + eta epsilon being smooth
- supp(u^-e) C V + B(0,epsilon)
- u_m in C^c infinity for all m
-->

---

# Step 3: Convergence in $L^{p^{*}}$

- **Problem**: We haven't proved $u_{m}\to \bar u$ in $L^{p^{*}}$

- **Solution**: Apply GNS to differences

$$
\|u_m - u_\ell\|_{L^{p^*}(\mathbb{R}^n)} \leq C \| D(u_m - u_\ell)\|_{L^p(\mathbb{R}^n)}
$$

1. Take the limit for $m,\ell\to\infty$

2. Since $\{ D u_m\}$ is Cauchy in $L^p$, then  $\{u_m\}$ is Cauchy in $L^{p^*}(\mathbb{R}^n)$.

3. By completeness of $L^{p^*}(\mathbb{R}^n)$,  $u_m \to v$ in $L^{p^*}(\mathbb{R}^n)$.

4. Since we have convergence in $L^{p^*}$ and in $L^{p}$, then by uniqueness of a.e. limits: 
  
$$v = \bar u \rArr u_m \to \bar u \text{ in } L_p^* \rArr \bar u \in L_p^*$$

---

# Step 4: Whole-space Sobolev

&emsp;

Now we can now apply Theorem 1 directly on $u_m$ and take the limit for $m\to\infty$:

$$
\|\bar u\|_{L^{p^{*}}(\mathbb{R}^{n})}
\;\le\;
C\,\|D \bar u\|_{L^{p}(\mathbb{R}^{n})}
$$

Next use $\bar u \big|_U = u$, plus the definition of the weak derivative of $\bar u$:
$$
\lVert D\bar u\rVert_{L^p(\R^n)}
\;\le\;
\lVert Du\rVert_{L^p(U)}
\;+\;\|D\varphi\|_{L^\infty}\,\lVert u\rVert_{L^p(U)}.
$$


Putting these into the Sobolev inequality for $\bar u$ yields

$$
\|\,u\|_{L^{p^*}(U)}
\;=\;
\|\bar u\|_{L^{p^*}(\R^n)}
\;\le\;
C\,\|D \bar u\|_{L^p(\R^n)}
\;\le\;
C'\|u\|_{W^{1,p}(U)}.
$$

Hence the desired embedding on $U$:
$$
\boxed{
\|\,u\|_{L^{p^*}(U)} 
\;\le\; 
C\,\|\,u\|_{W^{1,p}(U)}, 
\quad
}
$$


---

# Theorem 3: Zero-Trace Sobolev Embedding

&emsp;

**Assumptions**: 
-  $U \subset \mathbb{R}^n$ bounded with $C^1$ boundary
- $u \in W_0^{1,p}(U)$ (zero trace on $\partial U$)
- $1 \leq p < n$, $p^* = \frac{np}{n-p}$

&emsp;

**Goal**:

$$
\boxed{
\|u\|_{L^q(U)} \leq C(n,p,q,|U|) \| D u\|_{L^p(U)}
}
$$

for all $1 \leq q \leq p^*$


---

# Proof of Theorem 3

&emsp;

**Step 1**: We can use a zero-extension  
$$
\overline{u}(x) \;=\; 
\begin{cases}
u(x), & x\in U,\\
0,    & x\notin U.
\end{cases}
$$

**Steps (2-5) are the same as Theorem 2**: Mollification, Convergence in $L^{p^*}$, Whole-space Sobolev, Limit

**Step 6**: Extension to $1 \leq q < p^*$

We use **Lyapunov's inequality**:

$$
\|u\|_{L^q(U)} \leq |U|^{\frac{1}{q} - \frac{1}{p^*}} \|u\|_{L^{p^*}(U)}
$$

$$
C(n,p,q,|U|) = C_0(n,p) \cdot |U|^{\frac{1}{q} - \frac{1}{p^*}}
$$

$$
\boxed{
\|u\|_{L^q(U)} \leq C(n,p,q,|U|) \| D u\|_{L^p(U)}
}
$$


--- 

# Alternative derivation for Theorem 3 in 1D

&emsp;


In 1D we can also derive it from the Fundamental Theorem of Calculus:

&emsp;

* $u(x)=\displaystyle\int_{y}^{x} D u\cdot d\gamma$ along a segment from a boundary point $y$ 
* Hölder on that 1-D integral gives $\lvert u(x)\rvert\le \lVert D u\rVert_{L^{p}}\lvert x-y\rvert^{1-\frac1p}$.
* Since $\lvert x-y\rvert\le\mathrm{diam}(U)$, integrating this bound over $x\in U$ yields $\lVert u\rVert_{L^{p^*}(U)}\;\lesssim\;\lVert D u\rVert_{L^{p}(U)}$ → the Sobolev embedding $W^{1,p}\hookrightarrow L^{p^*}$.


---

# Application: Semilinear Heat Equation

&emsp;

**Problem**

* Domain: $\Omega\subset\mathbb{R}^3$, bounded, $C^1$ boundary
* PDE:

  $$
    u_t = \Delta u + u^3,
    \quad (x,t)\in\Omega\times(0,\infty),
  $$

  with $u|_{\partial\Omega}=0,\;\;u(x,0)=u_0\in H_0^1(\Omega)$.

&emsp;

**Goal**: Show global existence by controlling the $H^1$–norm via energy methods.

---

# Energy Method

* Define

  $$
    E(t)\;=\;\|u(\cdot,t)\|_{L^2}^2,
    \qquad
    G(t)\;=\;\| D u(\cdot,t)\|_{L^2}^2.
  $$
* Multiply $u_t=\Delta u+u^3$ by $u$ and integrate over $\Omega$:

  $$
    \frac{dE}{dt}
    \;+\;2\,G
    \;=\;2\int_\Omega u^4\,dx.
  $$

  $$
    \boxed{\quad
      \frac{dE}{dt} + 2\,G(t) \;=\; 2\int_\Omega u^4\,dx. 
    \quad}
  $$

&emsp;

We can use Theorem 3 to bound the LHS.

---

# Sobolev Embeddings for Energy Inequality

1. **Sobolev Embedding**

$$
  \|u\|_{L^4} \;\le\; A|| D u\|_{L^2}=\;A\,G^2(t).
$$


2. **Insert into energy identity**

   $$
     \frac{dE}{dt} + 2\,G 
     \;\le\; 2\,A\,G^2.
   $$

3. **Poincaré inequality** 
   $$
     G(t)\;\ge\;\lambda_1\,E(t)
     \quad
   $$
   

$$...$$


$$
  \boxed{
    \frac{dE}{dt} 
    \;\le\; -\,2\,\lambda_1\,E\,\bigl(1 \;-\; A\,\lambda_1\,E\bigr).
  }
$$

---

# Global Existence via ODE Analysis

* **Define** $E_* := \tfrac{1}{A\,\lambda_1}$.

* The differential inequality

  $$
    \frac{dE}{dt} \;\le\;-\,2\,\lambda_1\,E\,\bigl(1 - A\,\lambda_1\,E\bigr)
  $$

  shows $E(t)$ cannot exceed $E_*$, and for $E(0)<E_*$ it decays.

 $E(t)$ remains bounded for all $t$.
Since $\|u\|_{H^1}^2 \approx E(t) + G(t)$ and $G(t)\ge\lambda_1E(t)$, the $H^1$–norm of $u$ never blows up.

$$
\boxed{\text{Hence a global \(H_0^1\)-solution exists for all }t>0.}
$$

---
layout: center
class: text-center
---

# Thank You!
