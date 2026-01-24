---
title: El Problema de Zarankiewicz
date: 2025-07-06 17:30:00
draft: true
---

<!---->NOTE: agregar link wikipedia
En 1951  Zarankiewicz propuso el siguiente problema:  

> Sea $A_n = (a_{ij})$ una matriz de $n$ filas y $n$ columnas tal 
> que $a_{ij} \in \\{0, 1\\}$. Sea $t$ un entero con $2 \le t \le n - 1$.  
> Si $A_n$ contiene un número **suficientemente grande** de $1s$, entonces
> $A_n$ contiene un "menor" de orden $t$ cuyas entradas son únicamente de 
> $1s$.

Este problema tiene una traducción natural al lenguaje de teoría de gráficas.
Sea $H = (X, Y)$ una gráfica bipartita cuyas partes son de orden $n$, es decir,
$\vert X \vert = \vert Y \vert = n$. Etiquetemos los vértices de $X$ y $Y$ como 
$x_1, \ldots, x_n$ y $y_1, \ldots, y_n$ respectivamente. De esta manera, poddemos
definir a la matriz $A_n = (a_{ij})$ como

$$a_{ij} = 1 \quad  \text{ si } \quad (x_i, y_j) \in E(H),$$
o $a_{ij} = 0$ de otro modo. Entonces el problema de Zarankiewicz pregunta por
el número de aristas que $H$ debe tener para asegurar que $H$ contiene
una gráfica bipartita completa $K_{t,t}$.

Por supuesto, el problema original puede ser generalizado al considerar a las partes
de $H$ de tamaños distintos, digamos $m$ y $n$. Y también al considerar subgráficas
bipartitas completas con partes de tamaño distinto, es decir, subgráficas $K_{s,t}$.

Con esta traducción, podemos enmarcar a este problema dentro de lo que se conoce 
como Teoría Extremal. En estas notas, daremos una breve introducción a este problema
presentando resultados relacionados bla bla bla.

## Introducción: Teorema de Turán
En Teoría Extremal nos interesan problemas de la siguiente forma:

> Dada una gráfica $G$ de orden $n$ que tiene asociada una gráfica **prohibida** H, es
> decir, $H$ **no es subgráfica de $G$, ¿qué tantas aristas puede tener $G$?

Denotemos por $ex(n, H)$ al máximo número de aristas una gráfica de orden $n$ cuya
gráfica prohibida es $H$. A este número se le conoce como **número extremal** o 
**número de Turán**.

El Teorema de Turán describe precisamente el comportamiento del número extremal, cuando $H$
es una gráfica completa. Para esto, definamos a la gráfica de Turán $T_{n, r}$, la 
gráfica $r-$partita completa de orden $n$ cuyas partes difieren en tamaño a lo más
en un vértice (cada parte es de tamaño $\lfloor n / r \rfloor$ o $\lceil n / r \rceil $).

**Teorema**. La gráfica de Turán $T_{n, r}$ es la gráfica con el número máximo de aristas
de entre todas las gráficas de orden $n$ que son libres de gráficas completas de orden
$r + 1$. Más aún, la gráfica de Turán es el único maximizador.

Este resultado es particularmente fuerte, pues no solo establece que $ex(n, K_{r+1}) = e(T_{n, r})$,
sino que además nos muestra la estructura de la "(única) gráfica extremal", la gráfica de Turán. 

**Lema**. Entre todas las gráficas $r-$partitas, la gráfica de Turán es la única gráfica
con el máximo número de aristas.

_Demostración_. Considere una gráfica $r-$partita con el máximo número de aristas. Esta 
debe ser completa. Si dos de sus partes, digamos $A$ y $B$, satisfacen 
$\vert A \vert + 2 \le \vert B\vert$, entonces "mover" un vértice de $B$ a
$A$ incrementaría el número de aristas por

$$(\vert A \vert + 1) (\vert B \vert - 1) - \vert A \vert \vert B \vert = \vert B \vert - \vert A \vert - 1, $$

lo cual contradice la maximalidad de la gráfica. Por tanto, todas las partes difieren en tamaño
a lo más en un vértice. La gráfica de Turán es esta gráfica. ✅

_Demostración del Teorema de Turán_. Procederemos mediante inducción sobre $r$. El caso $r=1$
es trivial, pues una gráfica libre de $K_2$ no contiene aristas. Asuma pues que $r > 1$ y 
que $ex(n, K_{r}) = e(T_{n, r-1})$ para toda $n$. 
Sea $G$ una gráfica libre de $K_{r+1}$. Sea $v$ un vértice de $G$ de grado máximo. Como $G$ 
es libre de $K_{r+1}$, la vecindad $A = N(v)$ de $v$ es libre de $K_{r}$.

## Referencias
- K. Zarankiewicz, Problem 101, Colloq. Math. 2 (1951), 301.
