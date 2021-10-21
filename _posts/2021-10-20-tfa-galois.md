---
layout: post
title: "Teorema Fundamental del Álgebra"
date: 2021-10-20 17:09:00
categories: posts
tags: teoria-de-galois
---

El Teorema Fundamental del Álgebra (en adelante TFA) afirma que todo polinomio con coeficientes en los complejos tiene una raíz compleja. Este importante resultado normalmente se demuestra en un primer curso de análisis complejo utilizando el [teorema de Liouville](https://en.wikipedia.org/wiki/Liouville%27s_theorem_(complex_analysis)). No obstante, aunque esta demostración es sastisfactoria desde el punto de vista analítico, se debería poder demostrar el TFA utilizando únicamente herramientas algebraicas.

En estas notas presentamos una demostración del TFA utilizando Teoría de Galois. 

### Conceptos clave de la Teoría de Galois

En esta sección se presentan resultados y definiciones de la Teoría de Galois fundamentales para la demostración del TFA. Algunos teoremas se presentan sin demostración. Para una explicación más detallada consultar [1]. 

Sea $f(x) \in k[x]$ un polinomio no constante con coeficientes en un campo $k$. Si $K/k$ es una extensión de $k$ tal que $f(x) = a(x-z_1) \cdots (x-z_n)$,  con $z_i \in K$ y $a \in k$, decimos que $f$ se **descompone o factoriza** en $K$.  Una extensión $E/k$ es un **campo de descomposición** de $f$ sobre $k$ si $f$ se descompone en $E$ y no se descompone en ningún subcampo propio de $E$. Un resultado elemental es que cualesquiera dos campos de descomposición son **isomorfos.**

Si $K/k$ es una extensión, entonces $K$ es un espacio vectorial sobre $k$. Su dimensión la denotamos por $[K:k]$. Una extensión $K/k$ es **finita**, si $[K:k]$ es finita. Si se tiene una torre de campos, es decir, campos que satisfacen $k \subset E \subset K$ con $K/k$ extensión finita, entonces se cumple 

$$[K: k] = [K: E][E:k]. $$

El **grupo de Galois** de una extensión $E/k$, denotado por $Gal(E/k)$ es el conjunto de todos los automorfismos de $E$ que fijan a $k$. Es claro que el grupo de Galois es un grupo bajo composición de funciones.  

Si $E$ es un campo y $H$ es un subconjunto de $Aut(E)$, entonces el **campo fijo** de $H$ se define como

$$E^H = \{a \in E: \sigma(a) = a \text{ para todo } \sigma \in H \}.$$

Una extensión $E/k$ es una **extensión finita de Galois** si $E/k$ es una extensión finita y $k = E^{Gal(E/k)}$. 

**Teorema Fundamental de la Teoría de Galois.** Sea $E/k$ una extensión finita de Galois con grupo de Galois $G = Gal(E/k)$. Entonces

1. La función $\gamma: Sub(Gal/E/k) \rightarrow Int(E/k)$ definida como 

   $$ \gamma : H \mapsto E^H$$, 

   es una biyección que invierte el orden. Su inversa,

   $$ \delta: Int(E/k) \rightarrow Sub(Gal(E/k)),$$

   es también una biyección que invierte el orden y se define como

   $$ \sigma: B \mapsto Gal(E/B).$$

2. Para todo $B\in Int(E/k)$ y $H\in Sub(Gal(E/k))$, se tiene 

   $$E^{Gal(E/B)} = B \ \ \text{ y } Gal(E/E^H) = H.$$

3. Para todo $B \in Int(E/k)$ y $H\in Sub(Gal(E/k))$, se tiene que 

   $$ [B:k] = [G: Gal(E/B)] \ \ \text{ y } [G:H] = [E^H:k].$$

4. Si $B\in Int(E/k)$, entonces $B/k$ es una extensión de Galois si y solo si $Gal(E/B)$ es un subgrupo normal de $G$

Hablando informalmente, existe una correspondencia biyectiva entre campos intermedios de $E$ y subgrupos de del grupo de Galois $Gal(E/k)$. Esta correspondencia invierte el *orden* de contención. Por ejemplo, si $E = \mathbb Q(\sqrt 2, \sqrt 3)$, se obtiene el siguiente diagrama:



![](https://upload.wikimedia.org/wikipedia/commons/a/ad/Lattice_diagram_of_Q_adjoin_the_positive_square_roots_of_2_and_3%2C_its_subfields%2C_and_Galois_groups.svg)

**Lema 1.**  El campo $\mathbb C$ no tiene extensiones de grado $2$.

*Demotración.* Aplíquese la fórmula general.

**Lema 2.** Todo polinomio $f(x) \in \mathbb R[x]$ de grado impar tiene una raíz real.

La demostración de este lema se basa en el Teoerma del Valor Intermedio.

**Lema 3.** No existe extensión $E/\mathbb R$ de grado impar mayor que $1$. 

*Demostración.* Si $u \in E$, entonces, por el Lema 1,  su polinomio minimal e irreducible sobre $\mathbb R$ tiene grado par. Luego, $[\mathbb R(u): \mathbb R]$ es par. Ya que $[E: \mathbb R] = [E: \mathbb R(u)] [\mathbb R(u): \mathbb R]$, se tiene que la extensión $E/\mathbb R$ es de grado par.

## Resultado principal

Formalmente, el TFA es el siguiente.

**Teorema Fundamental del Álgebra.** Todo polinomio no constante $f(x) \in \mathbb C[x]$ tiene una raíz compleja.

 Antes de presentar la demostración, veamos lo siguiente. Sea $f(x) = \sum_i^n a_i x^i \in \mathbb C[x]$. Denotemos el *polinomio conjugado* de $f$ por $\bar f(x) = \sum_i^n \bar{a_i}x^i$, donde $\bar a_i$ es el conjugado de $a_i$. Observe que el producto $f \cdot \bar f $ es un polinomio en $\mathbb R[x]$, ya que si $f \cdot \bar f (x) = \sum_{i}^k c_i x^i$, con $c_i = \sum_{r + s = i} a_r \bar a_s$, entonces $\bar c_i = \sum_{r+s = i}^n \bar a_r a_s = \sum_{s+r=i} a_s \bar a_r = c_i$. Como $c_i = \bar c_i$, se tiene que $c_i \in \mathbb R$. 

Afirmamos que si $z_0$ es una raíz de $f \cdot \bar f$, entonces $z_0$ o $\bar z_0$ es una raíz de $f$.  Para esto, si $z_0$ es una raíz del polinomio $f \cdot \bar f$, entonces $f(z_0) = 0$ o $\bar f(z_0) = 0$. Si $z_0$ es raíz de $\bar f$, entonces $\bar z_0$ es raíz del polinomio $f$. 

Hemos reducido el problema original (demostrar TFA) en  el problema de demostrar que todo polinomio en $\mathbb R[x]$ tiene una raíz compleja. Sea pues $f(x) \in \mathbb R [x]$ y sea $E/\mathbb R$ el campo de descomposición del polinomio $(x^2 + 1)f(x)$. Dado que $\mathbb R[x] / (x^2+1) \cong \mathbb C$, se tiene que $\mathbb C$ es un campo intermedio de la extensión $E/\mathbb R.$ Como $\mathbb R$ es de característica $0$, $E/ \mathbb R$ es una extensión de Galois. Si $G = Gal(E/\mathbb R)$, entonces $\lvert G \rvert = 2^m l$, con $m \geq 0$ y $l$ impar. Por el [teorema de Cauchy](% post_url  2021-07-02-teorema-cauchy-grupos}), $G$ tiene un subgrupo $H$ de orden $2$. Sea $B = E^H$ su campo intermedio correspondiente. Por el Teorema Fundamental de la Teoría de Galois, el grado $[B: \mathbb R]$ es igual al índice $[G: H] = l$.  Por el lema 3, $\mathbb R$ no tiene extensiones impares mayores a $1$. Luego, $l = 1$ y $G$ es un $2-$grupo.

Por otro lado, $E/\mathbb C$ también es una extensión de Galois, y $Gal(E/ \mathbb C) \subset G$ es también un $2-$ grupo. Si $Gal(E/\mathbb C)$ es no trivial, este grupo tiene un subgrupo $K$ de índice $2$. De nuevo, por el Teorema Fundamental de la Teoría de Galois, el campo intermedio $E^K$ es una extensión de $\mathbb C$ de grado $2$, lo cual contradice el lema 1. Por tanto, $[E: \mathbb C] = 1$, es decir, $E = \mathbb C$. El resultado se sigue inmediatamente. :metal:

### Referencias

[1] Rotman, J. (2015). *Advanced Modern Algebra*. American Mathematical Society.

---

