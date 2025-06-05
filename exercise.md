Below is an expanded “slide-by-slide” storyboard: every item is still short enough to fit on a single slide (or a couple of blackboard lines), but contains the essential equations and constants you will want to display.

---

### **1 · Problem statement**

* **PDE (semilinear heat, cubic):**

  $$
    u_{t}=\Delta u+u^{3},
    \qquad (x,t)\in\Omega\times(0,\infty),
  $$

  with **Dirichlet BC** $u|_{\partial\Omega}=0$ and data $u_{0}\in H^{1}_{0}(\Omega)$.
* **Domain:** bounded $C^{1}$ set $\Omega\subset\R^{3}$.
* **Goal:** obtain a *global* $H^{1}$–solution and show it cannot blow up; key tool is the Sobolev embedding $W^{1,2}_{0}\hookrightarrow L^{6}$.

---

### **2 · Energy identity**

Define

$$
  E(t)=\|u(\cdot,t)\|_{L^{2}}^{2},\quad 
  G(t)=\|\nabla u(\cdot,t)\|_{L^{2}}^{2}.
$$

1. Multiply PDE by $u$, integrate over $\Omega$:

   $$
     \int u_{t}\,u=-\int|\nabla u|^{2}+\int u^{4}.
   $$
2. Hence

   $$
     \boxed{\;\frac{dE}{dt}+2G=2\int_{\Omega}u^{4}\,dx.  \tag{EI}\;}
   $$

   *Interpretation:* diffusion $+\,2G$ dissipates energy; $u^{3}$ supplies energy via $\int u^{4}$.

---

### **3 · Sobolev embedding controls $\int u^{4}$**

* **Theorem 3 (Dirichlet $H^{1}\to L^{6}$)**

  $$
    \|u\|_{L^{6}}\le C_{S}\,\|\nabla u\|_{L^{2}}.
  \tag{S}
  $$
* Finite-measure drop $6\to4$:

  $$
    \|u\|_{L^{4}}
    \;\le\;
    |\Omega|^{\frac{1}{12}}\|u\|_{L^{6}}.
  $$
* Combine:

  $$
    \int u^{4}
    =\|u\|_{4}^{4}
    \le
    (C_{S}^{4}|\Omega|^{1/3})\,G^{2}.
  $$

  Set $\displaystyle A=C_{S}^{4}|\Omega|^{1/3}$.

---

### **4 · Energy inequality with pure gradient**

Insert bound into (EI):

$$
  \boxed{ \;
    \frac{dE}{dt}+2G
    \;\le\;
    2A\,G^{2}.
  \tag{IE}\;}
$$

---

### **5 · Link $G$ and $E$ (Poincaré)**

* Dirichlet Poincaré:

  $$
    G(t)\;\ge\;\lambda_{1}\,E(t),
  $$

  where $\lambda_{1}>0$ is the first Laplacian eigenvalue of $-\Delta$ on $\Omega$.

Use $G\ge\lambda_{1}E$ inside (IE):

$$
  \frac{dE}{dt}
  \;\le\;
  -2\lambda_{1}E\bigl(1-A\lambda_{1}E\bigr).
\tag{ODE}
$$

This is a logistic-type differential inequality for $E(t)$.

---

### **6 · Dynamics of the logistic inequality**

* **Critical threshold:** $E_{*}=1/(A\lambda_{1})$.

* **If** $E(0)<\dfrac{E_{*}}{2}$:

  $$
      \frac{dE}{dt}\le -\lambda_{1}E
      \;\Longrightarrow\;
      E(t)\le E(0)\,e^{-\lambda_{1}t}.
  $$

* **If** $E(0)\ge E_{*}$:
  RHS of (ODE) is initially positive, drives $E(t)$ *down* until $E(t)=E_{*}$, after which $dE/dt\le0$.  So in all cases

  $$
    0<E(t)\le \max\bigl\{E(0),E_{*}\bigr\}\quad\forall t.
  $$

---

### **7 · Consequences**

1. **Global existence:**
   Energy never blows up ⇒ $H^{1}$-norm bounded ⇒ local solution extends for all $t$.
2. **Uniqueness:**
   Apply the same steps to the difference $w=v-u$; Sobolev embedding absorbs the cubic term ⇒ $w\equiv0$.
3. **Higher regularity:**
   With $u\in H^{1}$ uniformly bounded and $u^{3}\in L^{2}$, elliptic/parabolic regularity boosts $u$ to $H^{2}$, then $C^{\alpha}$, etc.
4. **Small data decay:**
   If $\|\nabla u_{0}\|_{2}^{2}<1/(2A)$, then $E(t)\le E(0)e^{-\lambda_{1}t}$ ⇒ exponential decay to zero.

---

### **8 · Role of Sobolev embedding (one-liner)**

$$
  \text{\bf Theorem 3:}\quad
  W_{0}^{1,2}(\Omega)\xrightarrow{\;\;\subset\;\;}L^{6}(\Omega)
  \;\Longrightarrow\;
  \boxed{\;\int u^{4}\le A\,\|\nabla u\|_{2}^{4}\;}.
$$

That single inequality converts an uncontrolled $u^{4}$ source into a **pure-gradient** term, closes the energy estimate, and ultimately underwrites global existence, uniqueness, and decay.
