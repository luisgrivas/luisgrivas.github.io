---
layout: post
title: "Espacios cubrientes"
date: 2021-03-04 9:00:00
categories: posts
tags: [topologia, topologia-algebraica]
---

En lo siguiente, todos los espacios en cuestión son arco-conexos y [localmente arco-conexos](https://en.wikipedia.org/wiki/Locally_connected_space#Definitions_and_first_examples).

**Definición.** Sean $E$, $B$ espacios topológicos. Decimos que un mapeo $p: E \to B$ es un **mapeo cubriente**, si $p$ es continuo y sobreyectivo y si para todo $x \in B$ existe una vecindad $U$ tal que $p^{-1}(U)$ es la unión de abiertos disjuntos en $E$, cada uno mapeado homeomorfamente por $p$ sobre $U$. Es decir,
$$
p^{-1}(U) = \bigsqcup_\alpha V_\alpha
$$
con $V_\alpha \in E$ y $p\mid_{V_\alpha}: V_\alpha \to U$ homeomorfismo para toda $\alpha$. En este caso, decimos que $U$ es **regular**. Al espacio $E$ lo llamamos **espacio cubriente** y al espacio $B$ le llamamos **espacio base.** Los abiertos $V_\alpha$ que son mapeados por $p$ homeomorfamente les llamamos las **hojas** de $E$ sobre $U$.

Existe una relación estrecha entre los espacios cubrientes y un espacio base y sus grupos fundamentales. Esto los discutiremos en notas posteriores. 

**Ejemplo 1.** Sean $E = \mathbb R$ y $B = \mathbb S^1$, la círcunferencia en el plano complejo. El mapeo $\epsilon(s) = e^{2\pi i s}$ es un mapeo cubriente. Es claro que este mapeo es continuo y sobreyectivo. Para ver que es cubriente, considere los conjuntos $X_+ := \{z \in \mathbb S^1: Re(z) > 0 \}$, $X_{-} := \{z\in \mathbb S^1: Re(z) < 0 \}$, $Y_+ := \{z\in \mathbb S^1 : Im(z) > 0\}$ y $Y_{-}:= \{z \in \mathbb S^1: Im(z) < 0 \}$. Estos forman una cubierta abierta de $B$. Además, cada uno de estos es regular. Por ejemplo, 

$$
\epsilon^{-1}(X_+) = \bigcup_{n\in \mathbb Z} (n -1/4, n + 1/4 ).
$$
Podemos imaginar que el mapeo $\omega$ enrolla a la recta real en forma de hélice sobre la circunferencia. 

<img src="https://upload.wikimedia.org/wikipedia/commons/5/54/Covering_map.png" style="zoom:65%;" />



**Ejemplo 2.** Sean $E = B = \mathbb S^1$ y $p_n: \mathbb S^1 \to \mathbb S^1$ el mapeo definido como $p_n(z) = z^n$ para $n \in \mathbb N$. Este es un mapeo cubriente para toda $n$. 

**Ejemplo 3.** Sea $E = \mathbb S^n$ y $B = \mathbb{RP}^n$, el espacio proyectivo real de dimensión $n$. Sea $p: E \to B$  el mapeo que asigna a cada punto $x \in \mathbb S^n$ la recta que pasa por el origen y $x$.

**Teorema 1.** Todo mapeo cubriente es un [homeomorfismo local](https://en.wikipedia.org/wiki/Local_homeomorphism), un mapeo abierto y un [mapeo cociente](https://www.luisgrivas.com/blog/posts/2021/01/18/topologia-cociente.html). 

*Demostración:* Sea $p: E \to B$ un mapeo cubriente. El hecho que $p$ es un homeomorfismo local se deduce casi inmediatamente de la definición de mapeo cubriente. Si $x \in E$, entonces existe una vecindad regular de $f(x)$ en $B$, cuyas hojas podemos representar como $\{V_\alpha\}$. Sea $V_{\alpha^\prime}$ el elemento de $\{V_\alpha\}$ que contiene a $x$. Por definición,  $p(V_\alpha^\prime) =U$  es abierto en $B$ y $p\mid_{V_\alpha^\prime}$ es un homeomorfismo de $V_{\alpha^\prime}$ sobre $p(V_{\alpha^\prime})$. Por tanto $p$ es un homeomorfismo local.

Sea $V$ un abierto en $E$. Para cada $x \in V$, sea $U_{f(x)}$ el abierto regular en $B$ que contiene a $f(x)$. A su vez, para cada $x \in V$, sea $V_{x}$ la hoja correspondiente a $U_{f(x)}$ que contiene a $x$. Nótese para toda $x \in V$, $p(V \cap V_x) $ es un abierto en $U$, pues $p \mid_{V_x}$ es un homeomorfismo sobre $U$. Luego, $p(V) = p(V \cap (\bigcup_{x \in V} V_x)) = p(\bigcup_{x \in V} V \cap V_x) = \bigcup_{x \in V} p(V \cap V_x)$, que es abierto en $B$, pues es la unión de abiertos en $U$. Por tanto, $p$ es un mapeo abierto.

Finalmente, sea $U$ un subconjunto de $B$. Si $p^{-1}(U)$ es abierto en $E$, como $p$ es sobreyectivo y por el párrafo anterior, $p (p^{-1}(U))  = U$ es abierto en $B$. Concluimos que $p$ es un mapeo cociente. $\blacksquare$

Mediante el Teorema 1 podemos reinterpretar el mapeo $\omega$ del Ejemplo 1. Observe que $\omega$ induce la siguiente relación de equivalencia en $\mathbb R$: $x, y$ están relacionados si y solo si $x - y \in \mathbb Z$. Intuitivamente, $\omega$ enrolla a la recta real *pegando* a los enteros en un solo punto. Es claro que el resultado de esta identificación, $\mathbb R / \sim$, es el círculo $\mathbb S^1$.

El siguiente teorema nos indica cómo construir un mapeo cociente a partir de un número finito de mapeos cociente.

**Teorema 2.**  $p: E \rightarrow B$ y $p^\prime: E^\prime \rightarrow B^\prime$ son mapeos cubrientes, entonces $p \times p^\prime: E \times E^\prime \rightarrow B \times B,$ es un mapeo cubriente.

*Demostración:* Sea $(b, b^\prime) $ un elemento de $B \times B^\prime$. Sean $U \subset B$ y $U^\prime \subset B^\prime$ vecindades regulares de $b$ y $b^\prime$ respectivamente. Si $\{V_\alpha\}$ son las hojas de $U$ y $\{V^\prime_\beta\}$  son las hojas de $U^\prime$, entonces $(p\times p^\prime)^{-1} (U \times U^\prime)$ es igual a la unión de todos los $V_\alpha \times V^\prime_\beta$. Es claro que esta es una unión disjunta de abiertos en la topología producto y por tanto,  $U \times U^\prime$ es una vecindad regular de $(b, b^\prime)$. $\blacksquare$

**Ejemplo 4.** Por el Teorema 2, si $\omega$ es la función del Ejemplo 1, entonces $\epsilon \times \epsilon: \mathbb R^2 \to S^1 \times S^1 = T$ es un mapeo cubriente del toro. 

**Proposición 1.** Un mapeo cubriente inyectivo es un homemomorfismo.

*Demostración:* Sea $p: E \to B$ un mapeo cubriente e inyectivo (en particular es una biyección). Por el Teorema 1, $p$ es un mapeo abierto. Por tanto $p$ es un homeomorfismo [^1]. $\blacksquare$

**Teorema 3.** Para todo mapeo cubriente $p: E \to B$, la cardinalidad de las fibras $p^{-1}(x)$ es la misma para todas las fibras.

*Demostración:* Sea $\sim$ la relación de equivalencia en $B$ definido como $x \sim y$ si y solo si $p^{-1}(x)$ y $p^{-1}(y)$ tienen la misma cardinalidad. Sea $[x]$ una clase de equivalencia inducida por $\sim$. Como $p$ es un mapeo cubriente, existe una vecindad regular $U$ de $x$. Como la cardinalidad de la fibra $p^{-1}(x)$ es la misma que la cardinalidad de las hojas de $U$, entonces si $x^\prime \in U$ se tiene que $p^{-1}(x^\prime)$ tiene la misma cardinalidad que $p^{-1}(x)$. Esto implica que $U \subset [x]$, es decir, $[x]$ es un abierto en $B$. Como $B$ es conexo, esto solo es posible si $[x] = B$. Por tanto la cardinalidad de las fibras es la misma para todas las fibras. $\blacksquare$

El Teorema 3 nos permite hablar **del número de hojas** de un mapeo cubriente. El mapeo cubriente $p_n$ del Ejemplo 2 tiene $n$ hojas, pues todo número complejo tiene $n$ raíces complejas. En cambio, si $p$ es el mapeo cubriente del Ejemplo 3, este siempre tiene dos hojas: $p$ identifica puntos antipodales en $\mathbb S^n.$

---

[^1]: Esta es una equivalencia conocida. Véase por ejemplo el libro Topology, James Dugundji, Teorema 12.2.

**DRAFT:** falta terminar demostraciones.

