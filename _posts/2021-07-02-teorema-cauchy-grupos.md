---
 layout: post
title: "Teorema de Cauchy para grupos"
date: 2021-07-02 15:25:00
categories: posts
tags: teoria de grupos
---

En estas notas se muestran tres demostraciones del teorema de Cauchy. En lo siguiente $\mid A \mid$ denotará al número de elementos de $A$.

**Teorema de Cauchy.** Si $p$ es un primo que divide al orden de un grupo finito $G$, entonces $G$ tiene un elemento de orden $p$.

![Cauchy](https://upload.wikimedia.org/wikipedia/commons/e/e3/Augustin-Louis_Cauchy.jpg "Cauchy")

Para la primera demostración necesitamos el siguiente resultado.

**Lema.** Si $G$ es un grupo abeliano finito y $p$ es un primo que divide al orden de $G$, entonces existe un elemento de orden $p$. 

*Demostración:* La demostración se realiza por inducción en el orden de $G$. El teorema es cierto por vacuidad para $\mid G \mid = 1$. Suponga que el teorema es cierto para todo grupo abeliano de orden menor que $G$. Sea $a \in G$ distinto a la identidad y denotemos por $n$ al orden de $a$. Si $p \mid n$, entonces el elemento $a^{n/p} \in G$ tiene orden $p$. Suponga que $p \nmid n$. El subgrupo $K = \langle a \rangle$ es normal, pues $G$ es abeliano, por lo que $G/ K$ es un grupo. Se satisface que $\mid G/K \mid = \frac{\mid G \mid}{\mid K \mid} = \frac{\mid G \mid}{n}$, de manera que $p$ divide a $\mid G/K \mid$. Como $\mid G/K \mid < \mid G \mid $, por la hipótesis de inducción, $G/K$ tiene un elemento de orden $p$, digamos $ b K$, $b$ $\notin K$. Lo anterior implica que $b^p \in K$. Por uno de los corolarios del [Teorema de Lagrange](https://en.wikipedia.org/wiki/Lagrange%27s_theorem_(group_theory)), $b^{\mid K \mid p} = b^{np} =  1$. Sea  $c = b^{n}$ y supóngase que $c = 1$. Como $p \nmid n$, estos son primos relativos, por lo que existen enteros $\lambda, \mu$ tales que $b = b^{\ \lambda p + \mu n} = b^{\lambda p} b^{\mu n} = b^{\lambda p}$. Pero entonces $b \in K$, lo cual es una contradicción. Así pues, $c \neq 1$ y este es un elemento de orden $p$. $\blacksquare$

*Demostración 1 del Teorema de Cauchy.* La demostración se realiza por inducción en $m$, donde $\mid G \mid = p m$. Si $m = 1$, $\mid G \mid = p$, y el Teorema de Lagrange establece que todo elemento de $G$ diferente a la identidad tiene orden $p$.

Suponga entonces que el teorema es cierto para todo grupo de orden menor que $p m$. Si $x \in G$, denotemos por $C_G(x)$ el centralizador de $x$ en $G$ y por $N_G(x)$ al normalizador de $x$ en $G$. El [Teorema de Órbita-Estabilizador](https://en.wikipedia.org/wiki/Group_action#Orbit-stabilizer_theorem) establece que $\mid N_G(x) \mid = [G: C_G(x)]$. Si $x$ no es un elemento del centro de $G$, entonces  $\mid N_G(x)\mid > 1$ por lo que $\mid C_G(x) \mid < \mid G \mid.$ Si $p $ divide al orden de $C_G(x)$, entonces la hipótesis de inducción asegura que $C_G(x)$ (y por tanto $G$) tiene un elemento de orden $p$. Así pues, suponga que $p$ no divide al orden de $C_G(x)$ para $x \in G \setminus Z(G)$. La [ecuación de clase](https://groupprops.subwiki.org/wiki/Class_equation_of_a_group) establece que


$$
\mid G \mid = \mid Z(G) \mid + \sum_{x \notin Z(G)} [G: C_G(x)].
$$


Como $\mid G \mid = \mid C_G(x)\mid \cdot \ [G: C_G(x)]$ y $p$ no divide a $\mid C_G(x)\mid$, entonces $p \mid [G: C_G(x)]$ para toda $x \notin Z(G)$. Pero entonces $p$ divide al orden de $Z(G)$, pues $p$ divide al orden de $G$ y $p$ divide a todos los términos de la sumatoria anterior. Como $Z(G)$ es un grupo abeliano, el Lema anterior asegura que $Z(G)$ (y por tanto $G$) tiene un elemento de orden $p$. $\blacksquare$



La segunda demostración se obtiene como corolario del [Teorema de Sylow](https://en.wikipedia.org/wiki/Sylow_theorems). 

*Demostración 2 del Teorema de Cauchy.* Si $\mid G \mid = p^{\alpha} m$ con $p^\alpha \nmid m$, entonces por Sylow existe un subgrupo $H$ de $G$ de orden $p^\alpha$. Sea $x \in H$ distinto a la identidad. Entonces el orden de $\langle x \rangle $ es $p^\beta$ para algún $\beta \in \mathbb Z$, pues $\langle x \rangle $ es subgrupo de $H$. Entonces el elemento $y = x^{p^{\beta-1}}$ es distinto a la identidad y su orden es $p$. $\blacksquare$



La siguiente demostración elemental se debe a John McKay [^1]. 

*Demostración 3 del Teorema de Cauchy.* Denotemos al elemento neutro de $G$ como $1$ y $\mid G \mid = n$. Consideremos el siguiente conjunto.


$$
S = \{(a_1, \ldots, a_p): a_i \in G, a_1 \cdots a_p = 1\}.
$$


Observe que $\mid S \mid = n^{p-1}$, ya que tenemos $n$ opciones en las $p-1$ primeras entradas, pero en la última solo una opción, pues debe ser el inverso de $a_1 \cdots a_{p-1}$. Establezcamos una relación de equivalencia en $S$ diciendo que dos $p-$tuplas son equivalentes si una es una permutación cíclica de la otra. Observe que si $a_1 = \cdots = a_{p}$, entonces la clase $[(a_1, \ldots, a_p)]$ consiste de un solo elemento. Por otro lado, si al menos dos componentes de $(a_1, \ldots, a_p)$ son distintas, entonces la clase $[(a_1, \dots, a_p)]$ tiene $p$ elementos. Sea $r$ el número de clases de equivalencia con un solo elemento y sea $s$ el número de clases de equivalencia con $p$ elementos. Como toda relación de equivalencia induce una partición en clases de equivalencia, tenemos que


$$
n^{p-1} = r + s p.
$$


Como $p \mid n^{p-1} - sp $, entonces $p \mid r$. Luego, existe un $x\neq 1 \in G$ tal que $x^{p} = 1$; es decir, $x$ es un elemento de orden $p$.

---

[^1]: Véase American Mathematical Monthly, Vol. 66, John McKay, *Another proof of Cauchy's group theorem.*

