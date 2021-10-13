---
layout: post
title: "El grupo fundamental"
date: 2021-03-10 11:00:00
categories: posts
tags: topologia, topologia-algebraica
---



![](https://upload.wikimedia.org/wikipedia/commons/a/a4/Fundamental_group_torus2.png)

---

**Definición.** Sea $X$ un espacio. Decimos que un **camino** en $X$ es un mapeo continuo $f: I \rightarrow X$. Los puntos $p = f(0)$ y $q = f(1)$ se les llaman **punto inicial** y **punto final** respectivamente. 



**Definición.** Sean $X$ y $Y$ espacios topológicos y sea $A \subset X$. Una [homotopía](https://www.luisgrivas.com/blog/posts/2021/02/28/homotopia.html) $H$ entre mapeos $f, g: X \rightarrow Y$ es **estacionaria** en $A$ si 
$$
H(x, t) = f(x) \ \ \ \ \text{para todo } x\in A, t\in I. 
$$
Si existe tal homotopía deficmos que $f$ y $g$ son **homotópicas relativas con** $A$ y $H$ es también llamada **homotopía relativa con** $A$.

**Definición.** Sean $f$ y $g$  caminos en $X$. Una **homotopía de caminos** de $f$ a $g$ es una homotopía estacionaria en el conjunto $\{0, 1\} \subset I$. Si existe una homotopía de caminos entre $f$ y $g$ decimos que son **homotópicos por caminos** y escribimos $f \sim g$. 

Siendo específicos, si $f$ y $g$ son caminos de $p$ a $q$, estos son homotópicos por caminos si existe una función continua $H: I \times I \rightarrow X$ tal que
$$
\begin{eqnarray}
H(s, 0) &=& f(s) \ \ \ & \forall s\in I,\\
H(s, 1) &=& g(s) \ \ \ & \forall s \in I,\\
H(0, t) &=& p \ \ \ & \forall t \in I,\\
H(1, t) &=& q \ \ \ & \forall t \in I.
\end{eqnarray}
$$


**Ejemplo.** Sea $X$ el plano ahujerado ? $\mathbb{R} \setminus \{0\}$. Sean $f, g: I \rightarrow X$ los caminos $f(s) = (\cos \pi s, \sin \pi s)$ y $g(s) = (\cos(\pi s), 2 \sin \pi s)$. El mapeo $H: I \times I \rightarrow X$ definido como $H(s, t) = (1 - t) f(s) + t g(s)$ es una homotopía de cominos entre $f$ y$g$. Por tanto $f \sim g$.

**Teorema.** Sea $X$ un espacio topológico. Para cualesquiera puntos $p, q\in X$, la homotopía de caminos es una relación de equivalencia en el conjunto de caminos en $X$ de $p$ a $q$. 

**Definición.** Un lazo en un espacio $X$ es un camino $f$ en $X$ tal que $f(0) = f(1)$. Al punto $p = f(0)$ le decimos **punto base** de $f$ y decimos que el lazo **está basado en** $p$. El conjunto de todos los lazos basados en un punto $p$ lo denotamos como $\Omega(X, p)$. 

**Definición.** Una reparametrización de un camino $f: I \rightarrow X$ es un camino de la forma $f \circ \phi$ donde $\phi: I \rightarrow I$ es un mapeo continuo que fija a $0$ y a $1$.

**Proposición.** Cualquier reparametrización de un camino $f$ es homotópico por caminos a $f$.

**Definición.** El Teorema (tal) establece que la homotopía por caminos es una relación de equivalencia en el conjunto $\Omega(X, p)$. Al conjunto de clases de equivalencia de $\Omega(X, p)$ lo denotaremos por $\pi_1(X, p)$ y lo llamamos como **el grupo fundamental de** $X$ **basado en** $p$. 

Para llamar a $\pi_1(X, p)$ propiamente grupo, es necesario demostrar que este posee  la estructura algebraica de grupo. Primero definamos una operación binaria en $\pi_1(X, p)$.

**Definición.** Sean $f, g: I \rightarrow X$ caminos en $X$. Decimos que $f$ y $g$ son caminos *composable* si $f(1) = g(0)$. Si $f$ y $g$ son *composable*, definimos el **producto** $f \cdot g: I \rightarrow X$ como
$$
(f \cdot g) (x) = \cases{f(2s), \ \ \ \ \ \ \ \ \ \ \ 0 \leq s \leq \frac{1}{2};\\ g(2s -1), \ \ \ \ \frac{1}{2} \leq s \leq 1.}
$$
Es claro que este producto es continuo por el [lema del pegado.](https://www.luisgrivas.com/blog/posts/2021/02/28/homotopia.html#Lema%20del%20pegado)

**Teorema (el producto está bien definido)**. Sean $f_0 \sim f_1$ y $g_0 \sim g_1$ y si $f_0$ y $g_0$ son *composable*, entonces $f_1$ y $g_1$ son *composable* y $f_0 \cdot \sim f_1 \cdot g_1$. 

**Teorema.** Sea $f$ un camino de $p$ a $q$ en un espacio $X$, y sean $g$ y $h$ caminos en $X$. Entonces el producto de caminos satisface:

1. $[c_p] \cdot [f] = [f] \cdot [c_q] = [f]$.
2. $[f] \cdot [\overline{ƒ}] = [c_p]$ y $[\overline{f}] \cdot [f] = [c_q]$.
3. $[f] \cdot ([g] \cdot [h]) = ([f] \cdot [g]) \cdot [h]$ cuando el lado izquierdo o derecho esté bien definido. 



**Ejemplo.** Sea $\mathbb{R}^n$ el espacio euclidiano de dimensión $n$. Entonces $\pi(\mathbb{R}^n, x_0)$ es el grupo trivial. Para ver esto, sea $f$ un lazo basado en $x_0$. Entonces el mapeo $H: I \times I \rightarrow \mathbb{R}^n$ definido como $H(s, t) = (1- t)f(s) + tx_0$ es una homotopía de caminos entre el lazo $f$ y el lazo constante $c: I \rightarrow \{x_0\}$. 

**Definición.** Un espacio $X$ es **simplemente conexo** si es conexo por caminos y si $\pi_1(X, x_0)$ es el grupo trivial para algún $x_0 \in X$.

---

**DRAFT**

