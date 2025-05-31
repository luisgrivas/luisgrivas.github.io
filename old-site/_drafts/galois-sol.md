---
layout: post
title: "Criterio de solubilidad por radicales"
date: 2021-06-02 18:17:00
categories: posts
tags: teoria-de-galois
---



En estas notas queremos probar el siguiente resultado debido a Galois:

**Teorema.** Sea $f(x) \in k[x]$, donde $k$ es un campo y sea $E$ el campo de descomposición de $f$ sobre $k$. Si $f$ es soluble por radicales, entonces su grupo de Galois $Gal(E/k)$ es un grupo soluble.

En lo siguiente definiremos los conceptos del teorema y demostraremos algunos lemas que utilizaremos en la prueba.

<img src="https://upload.wikimedia.org/wikipedia/commons/5/53/Evariste_galois.jpg" style="zoom:35%;" />

### Campo de descomposición

El primer concepto clave es el concepto de campo de descomposición de un polinomio $f(x)$ en $k[x]$. Este se define como el campo más pequeño que contiene a todas las raíces de un polinomio $f$ y al campo $k$. Más formalmente, 

**Definición.** Si $K/k$ es una extensión de campo y $f(x) \in k[x]$ es no constante, entonces decimos que $f$ se **descompone** en $K$ si $f(x) = a (x - z_1)\cdots (x-z_n)$, donde $z_1, \ldots, z_n$ son elementos de $K$ y $a \in k$. Una extensión de campo $E/k$ se dice que es **el campo de descomposición** de $f$ **sobre** $k$ si $f$ se descompone en $E$, pero $f$ no se descompone en ningun subcampo propio de $E$.

Para aclarar la definición consideremos el siguiente ejemplo. Sea $f(x) = x^2 +1 \in \mathbb{Q}[x]$. Como sabemos, este polinomio se descompone en $\mathbb{Q}$ como $f(x) = (x - i)(x + i)$. Sin embargo, $\mathbb{C}$ **no es el campo de descomposición** de $f$. Podemos comprobar que el campo de descomposición de $f$ es $\mathbb{Q}(i) = \{a + bi : a,b \in \mathbb{Q}\}$ que es subcampo de $\mathbb{C}$.

Consideremos ahora el polinomio $g(x) = x^2 - 2 \in \mathbb{Q}[x]$. Sabemos que $g(x) = (x -\sqrt 2)(x + \sqrt2)$. El campo de descomposición de $f$ es  $\mathbb{Q}(\sqrt 2) = \{a + b \sqrt 2: a, b \in  \mathbb{Q}\}$.

Cabe señalar que el campo de descomposición de un polinomio también depende del campo $k$. Por ejemplo, en el ejemplo anterior, si $g(x)$ lo consideramos como un polinomio en $\mathbb{R}$, su campo de descomposición sería el mismo $\mathbb{R}$.

Los ejemplos anteriores pueden indicarnos dos cosas: 1) qué el campo de descomposición de un polinomio siempre existen y además, 2) el cómo construirlos. Para ver esto, veamos los siguientes resultados. 

**Proposición 1.** Sea $k$ un campo y sea $p(x) \in k[x]$ un polinomio mónico e irreducible de grado $n$. Sea $K = k[x] / (p)$ y sea $\beta = x + I$. Entonces:

1. $K$ es un campo con $k^\prime = \{a + I: a \in k\}$ como subcampo isomorfo a $k$.
2. $\beta$ es una raíz del polinomio $p$ en $K$. 

*Demostración:* Como $p$ es irreducible, el ideal $(p)$ es maximal en $k[x]$. Por tanto $K $ es un campo. El mapeo $a \mapsto a + (p)$ claramente es un isomorfismo $k \rightarrow k^\prime$. Esto muestra 1. 

Para ver que $\beta$ es raíz de $p$, vea que si $p(x) = a_0 + a_1 x + \ldots + a_{n-1}x^{n-1} + x^n$, tenemos que

 

$$
\begin{eqnarray}
p(\beta) &=& (a_0 + (p)) + (a_1 + (p))(x + (p)) + \ldots + (1 +(p))(x + (p))^n\\
&=& (a_0 + (p)) + (a_1 x + (p)) + \ldots + (1 x^n + (p))\\
&=& a_0 + a_1x + \ldots + x^n + (p)\\
&=& p(x) + (p) = (p). 
\end{eqnarray}
$$


Como $(p)$ es el elemento cero en $K$, lo anterior muestra que $\beta$ es una raíz de $p$ en $K$. Esto muestra 2. $\blacksquare$

En realidad esta proposición es mucho más potente. La dimensión de $K$ sobre $k$ es justamente $n$ el grado de $p$. Además, si otro polinomio $g$ tiene a $\beta$ como raíz, este es divisible por $p$. No obstante esto no lo utilizaremos en estas notas.

A manera de ejemplo, consideremos de nuevo al polinomio $f(x) = x^2 + 1 \in \mathbb{Q}[x]$. Este polinomio es mónico e irreducible en $\mathbb{Q}$ (puede usárse el criterio de Eisenstein). La Proposición 1 nos indica que $K = \mathbb{Q}[x]/(f)$ es un campo cuyo elemento $\beta = x + (f)$ es raíz de $f$. Veamos que $K$ es isomorfo al campo de descomposición de $f$, $\mathbb{Q}(i)$. 

Consideremos el homomorfismo $\phi: \mathbb{Q}[x] \to  \mathbb{C}$ como $f(x) \mapsto f(i)$. Claramente el kernel de $\phi$ es el ideal $(p)$. Por el primer Teorema de Isomorfismo $K\simeq Im(\phi)$. Es claro que $Im(\phi) = \mathbb{Q}(i)$ ya que $i^2 = -1$. 

La Proposición 1 nos indica cómo encontrar extensiones de $k$ que contengan raíces de polinomios $f \in k[x]$. Es claro que si $\beta$ es raíz de $f$, entonces $f(x) = (x- \beta) g(x)$, con $grad(g) < grad(f)$. Por lo que si aplicamos este teorema repetidas veces podremos descomponer a $f$ linealmente. Esta es es precisamente la idea del siguiente teorema.

**Teorema 1.** Si $k$ es un campo y $f(x) \in k[x]$, entonces existe una extensión $K/k$ en la que podemos descomponer a $f$. 

*Demostración:* Utilizaremos inducción sobre el grado de $f$. Si $grad(f) = 1$, entonces $f$ es lineal y podemos escoger $K = k$. Suponga ahora que el teorema es cierto para todo polinomio $f \in k[x]$ de grado menor que $n$.  Si $grad(f) = n$, escribamos $f = p q$, con $p(x), q(x) \in k[x]$ y $p$ irreducible (esto siempre se puede hacer, ya que $k[x]$ es DFU). Por la Proposición 1, existe una extensión $K/k$ que contiene a una raíz $z$ de $p$. Luego, $p = h (x - z)$, de manera que $f = (x - z) hq$. Observe que $grad(hq) < grad(f)$. Entonces, por la hipótesis de inducción, existe una extensión $E/K$  $hq$ en la que podemos descomponer a $hq$. Pero esto implica que podemos descomponer a $f$. $\blacksquare$

Puede suceder que al aplicar la cadena de extensiones en un polinomio particular $f$ el campo resultante $K$ no sea el campo de descoposición del polinomio. Sin embargo, si $z_1, \ldots, z_n$ son las raíces de $f$, el campo de descomposición de $f$ es $k(z_1, \ldots, z_n)$.



### Solubilidad por radicales

Intuitivamente lo que queremos decir por *solubilidad por radicales* de un polinomio $f \in k[x]$, $k$ campo, es encontrar una fórmula que nos permita encontrar las raíces de $f$ en función de sus coeficientes. Por ejemplo la fórmula de segundo grado



$$
x_r = \frac{b \pm \sqrt{b^2 - 4ac} }{2a}
$$
es un ejemplo ... Para traducir este objetivo en el lenguaje de campos es necesario introducir los siguientes conceptos.

**Definición.** Una **extensión pura** de **tipo** $m$ es una extensión $k(u)/k$ en la que $u^m \in k$ para algún entero positivo $m$. Una extensión $K/k$ es una **extensión radical** si existe una torre de campos 



$$
k = K_0 \subset K_1 \subset \cdots \subset K_t = K,
$$
tal que $K_{i+1} / K_i$ es una extensión pura.

**Definición.** Sea $f(x) \in k[x]$ con campo de descomposición $E$. Decimos que $f$ es **soluble por radicales** si exste una extensión radical 



$$
k = K_0 \subset K_1 \subset \cdots \subset K_t
$$


con $E \subset K_t$.

Por ejemplo,  todo polinomio cuadrático $f(x) \in \mathbb Q[x]$ es soluble por radicales.  Si $f(x) = a x^2 + bx + c $,  $u = \sqrt{b^2 - 4ac}$  y $K_1 = \mathbb Q(u)$, entonces $K_1$ es una extensión pura de $k$ de tipo 2. Más aún, la fórmula cuadrática establece que $K_1$ es el campo de descomposición de $f$, lo que muestra que $f$ es soluble por radicales. 



###  Grupo de Galois y grupos solubles

**Definición.** Sea $E/k$ una extensión de campos. Un **automorfismo** de $E$ es un isomorfismo $\sigma: E \to E$; decimos que un automorfismo $\sigma$ de $E$ **fija** a $k$ si $\sigma(a) = a$ para toda $a\in k$.

**Definición.** El **grupo de Galois** de una extensión de campos $E/k$, denotado como $Gal(E/k)$, es el conjunto de todos los automorfismo de $E$ que fijan a $k$. Si $f(x) \in k[x]$ y $E$ es el campo de descomposición de $f$ sobre $k$, entonces el **grupo de Galois** de $f$ sobre $k$ es $Gal(E/k)$.

Es interesante determinar cómo actua el grupo de Galois de un polinomio $f$ sobre sus raíces .

**Propisición 2.**  Sea $E/k$ el campo de descomposición de un polinomio $f \in k[x]$. Si $\sigma \in Gal(E/k)$, entonces $\sigma$ permuta las raíces de $f$.

*Demostración:* Si z es una raíz de $f$, entonces $0 = \sigma(0) = \sigma(f(z)) = f (\sigma(z))$. Esto implica que $\sigma(z)$ es también una raíz del polinomio $f$. Por lo que, si $R$ es el conjunto de raíces de $f$ el mapeo $\sigma\mid_R: R \to R$. Además, como $\sigma$ es inyectiva, $\sigma \mid_R$ también es inyectiva. Por tanto $Gal(E/k)$ permuta las raíces de $f$.

...

Consideremos de nuevo el polinomio $f(x) = x^2 +1 \in \mathbb Q[x]$. Sabemos que el campo de descomposición de $f$ es $\mathbb Q(i)$. ¿Cuál es el grupo de Galois de $f$ ? Si $\sigma \in Gal(\mathbb Q(i)/\mathbb Q)$, como $i^2 = -1$, se tiene que $\sigma(i)^2 = \sigma(i^2) = \sigma(-1) = -1$. Por lo que $\sigma(i) = \pm i$. Ahora bien, si $a + bi \in \mathbb{Q}(i)$, entonces, $\sigma(a+bi) = \sigma(a) + \sigma(bi) = a \pm bi$. Por tanto, solo existen dos elementos en $Gal(\mathbb Q(i)/\mathbb Q)$: la identidad y la conjugación compleja. Es decir, $Gal(\mathbb Q(i)/\mathbb Q)$ es isomorfo a $\mathbb Z_2$. 

**Definición.** Una extensión de campos $E/k$ es **normal** si es el campo de descomposición de un polinomio en $k[x]$.

Por ejemplo, $\mathbb Q(i)/ \mathbb Q$ es una extensión normal, ya que es el campo de descomposición del polinomio $x^2 + 1 \in \mathbb Q[x]$. Otro

**Teorema 3.**  Sea $k \subset E \subset F$ una torre de campos. Si $E/k$ y $F/k$ son extensiones normales, entonces $\sigma(E) = E$ para toda $\sigma \in Gal(F/k)$. Además, $Gal(F/E) \vartriangleleft Gal(F/k)$ y 


$$
Gal(F/k) / Gal(F/E) \simeq Gal(E/k).
$$
*Demostración:*  Sea $\sigma \in Gal(F/k)$. Como $E/k$ es normal, entonces $E = k(z_1, \ldots, z_n)$, donde $z_1, \ldots, z_n$ son raíces de un polinomio en $k[x]$. Todo elemento de $E$ es de la forma $\sum a_{i_1,\ldots,i_n} z_1^{i_1}\cdots z_{n}^{i_n}$, por lo que

 $\sigma(\sum a_{i_1,\ldots,i_n} z_1^{i_1}\cdots z_{n}^{i_n}) = \sum a_{i_1,\ldots,i_n} \sigma(z_1)^{i_1}\cdots \sigma(z_{n})^{i_n} \ \ \ (1).$

 Como $\sigma \mid_E$ es un automorfismo de $E$ sobre $E$,  $\sigma$ permuta las raíces $z_1, \ldots, z_n$. Por lo que la expresión (1) es un elemento de $E$. Como claramente $E \subset \sigma(E)$, se concluye que $E = \sigma(E)$.

Definamos el mapeo $\phi: Gal(F/k) \to Gal(E/k)$ definido como $\phi(\sigma) = \sigma \mid_E$. Un simple cómputo muestra que $\phi$ es un homomorfismo de grupos. El kernel de $\phi$ es el conjunto de todos los automorfismo $\sigma \in Gal(F/k)$ tales que $\sigma \mid_E$ son la identidad en $E$, es decir, los automorfismos de $F$ sobre $F$ que dejan fijo a $E$. Por tanto, $\sigma \in Gal(F/E)$. Esto muestra que $Gal(F/E)$ es normal en $Gal(F/k)$. Finalmente, si $\gamma \in Gal(E/k)$, este se puede extender a un automorfismo $\sigma$ de $F$ sobre $F$. Como $\gamma$ deja fijo a $k$, $\sigma \in Gal(F/k)$ y $\phi(\sigma) = \gamma$. Esto muestra que $\phi$ es sobreyectiva. El resultado se sigue por el Primer Teorema de Isomorfismo. $\blacksquare$



**Lema.** Si $B = k(u_1, \ldots, u_t)/k$ es una extensión finita de campos, entonces existe una extensión normal $E/k$ que contiene a $B$; esto es, $E$ es el campo de descomposición de algún polinomio $f(x) \in k[x]$. Si $u_i$ es separable sobre $k$, entonces $f$ es un polinomio separable y si $G = Gal(E/k)$, entonces $E = k(\sigma(u_1), \ldots, \sigma(u_t): \sigma \in G)$. Por otro lado, si $B/k$ es una extensión radical, entonces la extensión normal $E/k$ es una extensión radical. 



**Teorema.** Sea $k = K_0 \subset K_1 \subset \ldots \subset K_t$ una torre de campos tales que $K_{i} / K_{i-1}$ es una extensión pura de tipo primo $p_i$. Si $K_t /k$ es una extensión normal y $k$ contiene a todas las $p_i$-ésimas raíces de la unidad para $i=1,  \ldots, t$, entonces existe una sucesión de subgrupos 


$$
Gal(K_t/k) = G_0 \supseteq G_1 \supseteq \ldots \supseteq G_t = \{1\},
$$
 con $G_{i+1}\lhd G_i$ y $G_i / G_{i+1}$ un grupo cíclico de orden $p_{i+1}$ o $\{1\}$.

**Definición.** Una **serie normal** de un grupo $G$ es una sucesión de subgrupos


$$
G = G_0 \supseteq G_1 \supseteq \ldots \supseteq G_t = \{1\}
$$
con cada $G_{i+1}$ subgrupo normal de $G_i$; los **grupos factores** de esta serie son los grupos cocientes $G_i / G_{i+1}$. La longitud de la serie es el número de grupos factores no triviales.

**Definición.** Un grupo es **soluble** si existe una serie normal cuyos grupos factores son abelianos.

