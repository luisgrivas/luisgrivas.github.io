---
title: "Resultados del Tipo Turán-Ramsey en el Hipercubo"
date: "2025-11-14 19:03:00"
author: ["lfgr"]
draft: false
---
Dadas dos [gráficas](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)) $G$ y $H$, definimos al _número extremal_ $ex(G, H)$ como el 
máximo número de aristas en una subgráfica de $G$ que no contiene una copia de $H$.

El _hipercubo de dimensión $n$_ es la gráfica $Q_n$ cuyo conjunto de vértices es
$\{0, 1\}^n$ y en el que dos vértices son adyacentes si difieren exactamente en una 
coordenada. Esta gráfica tiene $2^n$ vértices y, dado que es $n$-regular, tiene 
$n 2^{n-1}$ aristas ([Lema del Saludo](https://en.wikipedia.org/wiki/Handshaking_lemma)).

## Los ciclos monocromáticos son inevitables en el hipercubo
**Teorema**. Para toda $k$ y $l \geq 6$ y $n \geq n_0(k, l)$ suficientemente grande, 
toda coloración de aristas de $Q_n$ con $k$ colores contiene un ciclo monocromático
de longitud $2l$.

**Teorema**. Sea $H$ una subgráfica de un hipercubo. Entonces $H$ es Ramsey si y solo si
existe un encaje (embedding) de $H$ entre dos niveles del hipercubo de manera que en este 
encaje todas las aristas $e\in E(H)$ con el mismo _flip-bit_ tienen la misma 
presuma $p(e)$.

## Teorema de Turán en el hipercuboSobre un conjunto de subgráficas con densidad de Turán cero en el hipercubo

## Un resultado extremal en el hipercubo
Decimos que una subgráfica $H$ del hipercubo tiene una **representación $k$-partita** si
existe $l$ tal que 
- $H$ es una subgráfica $Q_l$;
- Toda arista $e = [a_1 \ a_2 \cdots a_l]$ en $H$ tiene exactamente $k$ bits diferentes de
cero.
- Existe una función $\sigma: [l] \rightarrow [k]$ tal que, para toda arista $e$, la 
imagen $\{\sigma(i_1), \ldots, \sigma(i_k) \}$ del conjunto de bits diferentes de zero
$\{a_{i_1}, \ldots, a_{i_k}\}$ de $e$ bajo $\sigma$ es $[k]$.

**Teorema**. Sea $H$ una subgráfica del hipercubo. Si, para alguna $k$, $H$ admite 
una representación $k-$partita, entonces
$$ ex(Q_n, H) = o(e(Q_n)). $$

## Subgráficas de densidad de Turán cero pero sin representaciones k-partitas
Para una gráfica $H$, el _número extremal_ de $H$ en $Q_n$, denotado por $ex(Q_n, H$, es
el número más grande de aristas en una subgráfica $G$ de $Q_n$ que no contiene una subgráfica
isomorfa a $H$.

Decimos que una gráfica $H$ tiene _densidad de Turán cero en un hipercubo_ si 
$ex(Q_n, H) = o(e(Q_n))$. De otra manera, decimos que $H$ tiene una _densidad de Turán
positiva en un hipercubo_.

Considere una 1-subdivisión de $K_{q, 2}$ con $q \geq 3$. A este tipo de gráficas también
se les conoce como _gráficas teta_ con $q$ piernas de longitud 4. Por economía, escribiremos
$\Theta(q)$. A los vértices de grado $q$ se les conoce como _polos principales_.

Sea $H(q)$ la unión de dos copias de $\Theta(q)$ que comparten exactamente un vértice
que es un polo principal de una copia y un vértice de subdivisión en la otra copia.

**Teorema**. Sea $H$ una gráfica en la que cada bloque tiene una representación partita. 
Entonces $H$ tiene una densidad de Turán cero en el hipercubo.

**Teorema**. Para toda $q\geq 3$ la gráfica $H(q)$ es cúbica, no tiene representación
partita, pero tiene densidad de Turán cero en el hipercubo.

## Números extremales para ciclos en el hipercubo

**Teorema**. Sea $l$ un entero impar, $l \geq 7$. Entonces
$ex(Q_n, C_{2l}) = O(n^{\frac{5}{6} - \frac{1}{3(l-3})} 2^n)$

## Referencias
- 
- 
- 
