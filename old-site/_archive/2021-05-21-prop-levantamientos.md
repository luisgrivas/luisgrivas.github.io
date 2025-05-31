---
layout: post
title: "Propiedades de levantamientos"
date: 2021-05-21 10:50:00
categories: posts
tags: topología-algebraica topología n-esfera toro
---

La teoría de [espacios cubrientes]() en conjunto con la teoría de levantamientos nos permite estudiar el grupo fundamental del espacio base. En estas notas veremos los principales teoremas de levantamientos y como consecuencia de estos daremos una primera aplicación: calcular el grupo fundamental de $\mathbb S^1$. 

**Definición.** Sean $q: E \rightarrow X$ un mapeo cubriente y $\phi: Y \rightarrow X$ un mapeo continuo. Un **levantamiento de** $\phi$ es un mapeo continuo $\widetilde \phi: Y \rightarrow E$ tal que $q \circ \widetilde \phi = \phi$. En otras palabras, el siguiente diagrama conmuta:

![](/assets/images/levantamiento.png)

Intuitivamente hablando, un espacio cubriente es enrollado en el espacio base mediante el mapeo cubriente. Así pues, si tenemos un mapeo continuo sobre el espacio base, un levantamiento son las *instrucciones* de enrollamiento de este este mapeo.

**Teorema 1 (Unicidad de levantamiento).** Sea $q: E \rightarrow X$ un mapeo cubriente. Suponga que $Y$ es conexo, $\phi: Y \rightarrow X$ es un mapeo continuo y que $\widetilde\phi_1, \widetilde\phi_2: Y \rightarrow E$ son levantamientos de $\phi$ que coinciden en un punto de $Y$. Entonces $\widetilde \phi_1$ es igual a $\widetilde \phi_2$.

*Demostración:* Sea $A = \{y\in Y: \widetilde \phi_1 (y) = \widetilde \phi_2(y) \}$. Puesto que $Y$ es conexo y por hipótesis $A\neq \emptyset$, si demostramos que $A$ es abierto y cerrado, implicaría que $A = Y$.  

Demostremos primero que $A$ es abierto. Si $a \in A$, entonces $e = \widetilde \phi_1(a) = \widetilde \phi_2 (a)$. Hagamos $x = q(e)$. Sea $U$ 



**Teorema 2 (de levantamiento de homotopía).** Sea $q: E \rightarrow X$ un mapeo cubriente y sea $Y$ un espacio localmente conexo. Suponga que $\phi_0, \phi_1 : Y \rightarrow X$ son mapeos continuos, $H: Y \times I \rightarrow X$ una homotopía de $\phi_0$ en $\phi_1$ y $\widetilde \phi_0: Y \rightarrow E$ un levantamiento de $\phi_0$. Entonces existe un único levantamiento de $H$ a una homotopía $\widetilde H$ que satisface que $\widetilde H_0 = \widetilde \phi_0$. Si $H$ es estacionaria en un subconjunto $A\subset Y$, entonces también lo es $\widetilde H.$

*Demostración:*



**Corolario 1 (Levantamiento de caminos).** Sea $q: E \rightarrow X$ un mapeo cubriente. Sea $f: I \rightarrow X$ un camino y $e \in E$ un punto en la fibra de $q$ sobre $f(0)$. Entonces existe un único levantamiento $\widetilde f : I \rightarrow E$ de $f$ tal que $\widetilde f(0) = e$.

*Demostración:*  Considere el espacio de un solo punto $Y=\{y\}$. Entonces $f$ puede verse como una homotopía entre los mapeos continuos $y \mapsto f(0) $ y $y \mapsto f(1)$. Como el mapeo $y \mapsto f(0)$ puede levantarse al mapeo $y \mapsto e$, por el Teorema 2,  $f$ se puede levantar a una única homotopía $\widetilde f$ tal que $\widetilde f(0) = $ e.



**Teorema 3 (de Monodromía) .**. Sea $q: E \rightarrow X$ un mapeo cubriente. Sean $f$ y $g$ caminos en $X$ con el mismo punto inicial y mismo punto final. Sean $\widetilde f_e, \widetilde g_e$ levantamientos de $f$ y $g$ respectivamente con el mismo punto inicial $e \in E$. Entonces

(a) $\widetilde f_e \sim \widetilde g_e$ si y solo si $f \sim g$.

(b) Si $f \sim g$, entonces $\widetilde f_e(1) = \widetilde g_e (1)$.

*Demostración:* (a) Si $\widetilde f_e \sim \widetilde g_e$, entonces existe una homotopía de caminos $\widetilde H: I \times I \rightarrow E$ de $\widetilde f_e$ en $\widetilde g_e$.  Como $\widetilde f_e $ y $\widetilde g_e$ son levantamientos de $f$ y $g$ respectivamente, se tiene que $H: I \times I \rightarrow X$ definida como $H = q \circ \widetilde H$ es una homotopía de $f$ en $g$. Por el Teorema 2, existe un levantamiento de homotopía de caminos $\widetilde H$ de $H$ tal que $\widetilde H_0 = \widetilde f_e$. Como $\widetilde H_1$ es un levantamiento de $g$ con punto inicial $e$,  por el Teorema $1$,  $\widetilde H_1 = \widetilde g_e$. Por tanto $\widetilde f_e \sim \widetilde g_e$. 

(b) Finalmente, si $f \sim g$, sus levantamientos correspondientes $\widetilde f_e$ y $\widetilde g_e$ son homotópicos (por (a)), por lo que tienen el mismo punto final.



<img src="https://upload.wikimedia.org/wikipedia/commons/b/b9/Monodromy_action.svg" style="zoom:220%;" />



**Teorema 4 (de inyectividad).**. Sea $q: E \rightarrow X$ un mapeo cubriente. Para cualquier punto $e \in E$, el homomorfismo inducido $q_\ast: \pi_1(E, e) \rightarrow \pi_1(X, q(e))$ es inyectivo. El subgrupo imagen $q_\ast \pi_1(E, e)$ en $\pi_1(X, x_0)$ consiste en todos los lazos basados en $q(e)$ cuyos levantamientos en $E$ que comienzan en $e$ son lazos.

*Demostración:* Sea $[f] \in Ker(q_\ast)$. Entonces $q \circ f \sim c_{q(e)}$. Por el Teorema de Monodromia, los levantamientos $\widetilde{q \circ f}$ y $\widetilde{c_{q(e)}}$ son homotópicos. Ahora bien, $f$ es el levantamiento de $q \circ f$ y $c_e$ es el levantamiento de $c_{q(e)}$. Por lo anterior, $f \sim c_e$. Por tanto, el único elemento en el kernel de $q_\ast$ es $[c_e]$.  Esto implica que $q_\ast$ es inyectivo. $\blacksquare$

**Ejemplo 1**. Consideremos el mapeo cubriente $q_n: \mathbb S^1 \to \mathbb S^1$ definido como $q_n(z) = z^n$, con $n \in \mathbb N$. Por el Teorema 4, $q_{n \ \ast}(\pi_1(\mathbb S^1, z_0))$ es un subgrupo de $\pi_1(\mathbb S^1, x_0)$. Como veremos más adelante, el grupo fundamental de $\mathbb S^1$ es un grupo cíclico generado por un solo elemento. Luego, si $\omega$ es el generador de $\pi_1(\mathbb S^1, z_0)$,  $q_{n \ \ast} \pi_1(\mathbb S^1, z_0)$ es $\langle [\omega^n] \rangle $. 

**Teorema 5 (Criterio de levantamiento)**. Sea $q: E \rightarrow X$ un mapeo cubriente. Sea $Y$ un espacio conexo y localmente conexo por caminos y sea $\phi: Y \rightarrow X$ un mapeo continuo. Dados cualesquiera dos puntos $y_0\in Y$ y $e_0 \in E$ tales que $q(e_0) = \phi(y_0)$, el mapeo $\phi$ tiene un levantamiento $\widetilde{\phi}: Y \rightarrow E$ satisfaciendo que $\widetilde{\phi}(y_0) = e_0$ si y solo si el subgrupo $\phi_\ast \pi_1(Y, y_0)$ de $\pi_1(X, \phi(y_0))$ está contenido en $q_\ast \pi_1(E, e_0)$.

*Demostración:* Si $\widetilde \phi$ es un levantamiento de $\phi$ tal que $\widetilde \phi(y_0) = e_0$, entonces $\phi_\ast \pi_1(Y, y_0) = q_\ast \circ \widetilde \phi_\ast \pi_1(Y, y_0) \subset q_\ast \pi_1(E, e_0)$.

Definamos el mapeo $\widetilde \phi: Y \rightarrow E$  como $\widetilde \phi (y) = \widetilde{(\phi \circ f)}_{e_0}(1)$, donde $f$ es un camino entre $y_0$ y $y$. En primer lugar, es necesario demostrar que el valor de $\widetilde \phi(y)$ es independiente del camino $f$ seleccionado. Para esto, sean $f$ y $f^\prime$ dos caminos de $y_0$ en $y$. 



### El grupo fundamental de $\mathbb S^1$

En esta sección expondremos que los teoremas anteriores tienen la sufiente potencia para derivar un resultado no trivial: el grupo fundamental de $\mathbb S^1$. Para esto, sea $\epsilon: \mathbb R \to \mathbb S^1$ el mapeo definido como $\epsilon(t) = e^{2\pi i t}$. En [notas anteriores](https://www.luisgrivas.com/blog/posts/2021/03/04/espacios-cubrientes.html) se demostró que este es un mapeo cubriente. Sea $\alpha$ un lazo en $\mathbb S^1$ basado en $1$. Si $\widetilde \alpha$ es un levantamiento de $\alpha$, como $\alpha$ es un lazo, entonces $\widetilde \alpha(0), \widetilde \alpha(1) \in \epsilon^{-1}(1) = \mathbb Z$, por lo que $\widetilde \alpha(1) - \widetilde \alpha(0)$ siempre es un entero. A este entero le llamaremos *el* **número de enrollamiento** de $\alpha$. Este entero es independiente del levantamiento seleccionado. Sea $\widetilde \alpha^\prime$ otro levantamiento de $\alpha$. Como $\epsilon(\widetilde \alpha (t)) = \alpha(t) = \epsilon(\widetilde \alpha^\prime(t))$, entonces 


$$
\begin{eqnarray}
e^{2\pi i \widetilde \alpha(t)} - e^{2\pi i \widetilde \alpha^\prime(t)}=0 &\iff& e^{2\pi i \widetilde \alpha(t)}(1  - e^{2\pi i \ [ \widetilde \alpha^\prime(t) -\widetilde \alpha(t)]}) = 0 \\
&\iff& e^{2\pi i  \ [\widetilde \alpha^\prime(t) -\widetilde \alpha(t)]} = 1\\ &\iff& \widetilde \alpha^\prime(t) -\widetilde \alpha(t) \in \mathbb Z.
\end{eqnarray}
$$


Ya que $\widetilde \alpha^\prime(t) -\widetilde \alpha(t)$ es una función continua de $I$ en $\mathbb Z$, tenemos que $\widetilde \alpha(t) = \widetilde \alpha^\prime(t) + K$, para alguna $K\in \mathbb Z$. De aquí, vemos que $\widetilde \alpha(1) - \widetilde \alpha (0) = \widetilde \alpha^\prime(1) - \widetilde \alpha^\prime (0)$. Lo anterior muestra que el número de enrollamiento es el mismo para cualquier levantamiento de $\alpha$. Denotemos al número de enrollamiento de un lazo $\alpha$ en $\mathbb S^1$ como $E(\alpha)$.

Intuitivamente, el número de enrollamiento nos indica qué tantas veces le da la vuelta a $\mathbb S^1$ un determinado lazo. Cabe esperar que dos lazos son homotópicos si y solo si tienen el mismo número de enrollamiento. Esto lo demostraremos a continuación.

 Consideremos dos lazos $\alpha$ y $\beta$ en $\mathbb S^1$ basados en $1$. Por el Corolario 1, existen levantamientos únicos $\widetilde \alpha$ y $\widetilde \beta$ de $\alpha$ y $\beta$ respectivamente tales que $\widetilde \alpha(0) = 0 = \widetilde \beta(0).$ Por el Teorema 3, los lazos $\alpha$ y $\beta$ son homotópicos si y solo si  $\widetilde \alpha $ y $ \widetilde \beta$  son homotópicos y $\widetilde \alpha (1) = \widetilde \beta (1)$. Pero esto ocurre si y solo si $E(\alpha) = \widetilde \alpha(1) - \widetilde \alpha(0) = \widetilde \beta (1) - \widetilde \beta(0) = E(\beta)$. 

Con lo anterior, tenemos todo lo necesario para demostrar el siguiente teorema. 

**Teorema 6.** El grupo fundamental de $\mathbb S^1$ es un grupo cíclico infinito generado por $[\omega]$, donde $\omega: I \to \mathbb S^1$ es el lazo definido como $\omega(t) = e^{2\pi i t}.$ 

*Demostración:* Solo tenemos que probar que $E(\omega^n) = n,$ donde $\omega^n = e^{2 \pi i n t}$ y $n \in \mathbb Z$. Observe que $\widetilde \omega^n: I \to \mathbb R$ definido como $\widetilde \omega^n(t) = nt$, es un levantamiento de $\omega^n$: $\epsilon(\widetilde \omega^n(t)) = e^{2 \pi i \widetilde \omega^n(t)} = e^{2\pi i nt} = \omega^n$. Entonces $E(\omega^n) = \widetilde \omega^n (1) - \widetilde \omega^n(0) = n $. 

Si $f$ es un lazo en $\mathbb S^1$ basado en $1$ con $E(f) = n$, entonces $f \sim \omega^n$. Por lo que $[f] = [\omega^n] = [\omega]^n$. Esto muestra que $\pi_1(\mathbb S^1, 1) = \langle [\omega] \rangle$. $\blacksquare$

De este teorema tenemos algunos resultados indemdiatos. 

**Corolario 2.** Si $X = \mathbb S^1 \times \cdots \times \mathbb S^1$, entonces $\pi_1(T^n, x_0) \simeq \mathbb Z^n$. En particular, el toro tiene grupo fundamental isomorfo a $\mathbb Z^2$.

Estos resultados nos permiten demostrar algo que con las herramientas previas no era posible.

**Corolario 3.** $\mathbb S^n$ no es homeomorfo a $T^n$, para $n > 2$.

**Corolario 4.** El espacio punteado $\mathbb R^2 - \{\pmb{0} \}$ tiene grupo fundamental isomorfo a $\mathbb Z$.

*Demostración.* Observe que el mapeo $r: \mathbb R^2 - \{\pmb 0\} \to \mathbb S^1$ definido como $r(x) = \frac{x}{\mid x \mid}$ es un retracto fuerte por deformación. Entonces $\pi_1(\mathbb R^2 - \{\pmb 0\}, x_0) = \pi_1(\mathbb S^1, 1) \simeq \mathbb Z$.

...



---

**Draft:**

