---
layout: post
title: "Temas relacionados con el conjunto de Cantor"
date:   2020-11-06 13:38:00 -600
last_modified_at: 2020-11-07 10:15:00
category: post
tags: análisis-real topología
---

## Conjunto de Cantor



<img src="https://upload.wikimedia.org/wikipedia/commons/5/56/Cantor_set_in_seven_iterations.svg" alt="conjunto de cantor" style="zoom:150%;" />



Hagamos $P_0 = [0, 1]$. Sea $P_1$ el conjunto resultante al remover el tercio central $(\frac{1}{3}, \frac{2}{3})$ de $P_0$, es decir, $P_1  = [0, \frac{1}{3}] \cup [\frac{2}{3}, 1]$. Sea $P_2$ el conjunto resultante al remover los tercios centrales de los intervalos de $P_1$. Obtenemos $P_2 = [0, \frac{1}{9}]\cup [\frac{2}{9}, \frac{3}{9}]\cup [\frac{6}{9}, \frac{7}{9}]\cup [\frac{8}{9}, 1]$. Continuando de está manera, sea $P_n$ el conjunto resultante al remover los tercios centrales de cada intervalo de $P_{n-1}$.  El conjunto de Cantor se define como 

$$C = \bigcap_{k=1}^\infty P_n.$$

Esta intersección es no vacía ya que $P_n \supset P_{n+1}$ y cada uno de estos es compacto[^1]. De la definición se observa que todo extremo de los intervalos de $P_n$ pertenecen al conjunto de Cantor.

Existe otra definición no obvia para el conjunto de Cantor. Definamos $T$ como el conjunto de números en $[0, 1]$   cuya expansión ternaria $(a_n)_3$ consiste únicamente de ceros y dos. Es decir



$$ T = \{(a_n)_3 \in [0, 1]: a_n \neq 1,  \forall n \in \mathbb{N}  \}$$



Demostremos por inducción que $T \subset P_n$ para toda $n \in \mathbb{N}$. 

Sea $x = (a_n)_3 \in T$. Si $a_n = 0$, para todo $n \in \mathbb{N}$, entonces $x = 0 $ y es un elemento de $C$. Suponga pues que $x > 0$.  Primero, si $a_1 = 0$, entonces $x < \frac{1}{3}$ y por tanto $x \in P_1$; y si $a_1 = 2$, entonces $x > \frac{2}{3}$ y por tanto $x \in P_1$. 

Suponga que $x \in P_k$ para algún natural $k$ y sea $I_{k, x}$ el intervalo de $P_k$ tal que $x \in I_{n, x}$. Si $a_n = 0$ para toda $n > k$, entonces $x$ es un extremo de $I_{k, x}$ y por tanto $x \in P_{k+1}$. Si lo anterior no ocurre, sea $k^\prime$ el natural mínimo tal que $a_{k^\prime} = 2$ y $k < k^\prime$.  Si $k^\prime > k + 1$, entonces $x < \frac{2}{3^k} + \frac{1}{3^{k+1}}$ y por tanto $x \in P_{k+1}$. Y si $k^\prime = k + 1$, entonces $x \geq \frac{2}{3^k} + \frac{2}{3^{k+1}}$ y por tanto $x \in P_{k+1}$. (??)

Concluimos por inducción que $x \in P_n$ para toda $n \in \mathbb{N}$. Por tanto $T \subset C$.

Ahora bien, sea $x \in T^c$ y sea $k$ el natural mínimo tal que $a_k = 1$. Entonces $x \in P_{k-1}$ [^2]. Sea $I_{x} = [c, d]$ el intervalo de $P_{k-1}$ que contiene a $x$. Observe que $c < c + \frac{1}{3^{k}}  \leq x < c + \frac{2}{3^k} < d$. Entonces $x$ pertenece al subintervalo $(c + \frac{1}{3^k}, c + \frac{2}{3^k})$ de $I_x$ que es removido al construir $P_k$. Por tanto, $x \notin C$. Se concluye que $T^c \subset C^c$ o dicho de otra manera, que $C \subset T$.

La discusión anterior nos permite concluir que $C$ se puede definir como el conjunto de todos los números reales en $[0, 1]$ cuya expansión ternaria $(a_n)_3$ satisface que $a_n = 0$ o $a_n = 2$ para toda $n \in \mathbb{N}$. 



## Propiedades topológicas

De la primera definición podemos constatar que $C$ es **cerrado**, pues es la interseccion de conjuntos cerrados. Pero no solo eso, también $C$ es **perfecto**, es decir, todos sus puntos son puntos límites. Si $x \in C$, entonces $x \in P_n$ para toda $n \in \mathbb{N}$. Denotemos por $I_{n, x}$ el intervalo de $P_n$ que contiene a $x$.  Observe que la longitud de $I_{n, x}$ es $l(I_{n, x}) = \frac{1}{3^n}$. Entonces, si $V$ es una vecindad de $x$, para $n$ suficientemente grande $I_{n, x} \subset V$. Luego, alguno de los puntos extremos de $I_{n, x}$ pertenece a $V \cap C\setminus \{ x\}$. Se sigue que $x$ es un punto límite de $C$.  Resumamos lo anterior con el siguiente teorema. 

**Teorema**. El conjunto de Cantor $C$ es perfecto. 

Cabe preguntarse, ¿cómo es el interior de este conjunto? Observe que al definir cada $P_n$, removemos un intervalo de la forma $(\frac{3m + 1}{3^n}, \frac{3m +2}{3^n})$ donde $m$ es un entero no negativo. Si $V$ es una vecindad de $x \in C$, siempre podemos encontrar un intervalo  de la anterior forma que esté contenido en $V$. Esto muestra que ninguna vecindad de $x$ está contenida en $C$. Se duduce que el interior de $C$ es vacío. Como $C = [C]$ y $Int([C]) = \emptyset$ , este es **denso en ninguna parte** de $[0, 1]$. 



## No numerabilidad 

Supongamos $C$ fuera numerable. Sea $\{x_n\}$ una enumeración de $C$. 

**Teorema**. Todo conjunto perfecto es no numerable.

Una segunda forma de demostrar que este conjunto es no numerable es establecer una correspondencia biyectiva entre $C$ y un conjunto no numerable. Por ejemplo, definamos el mapeo  $(a_n)_3 \mapsto (\frac{a_n}{2})_2$. Es claro que esta función es $1-1$ y sobre en el conjunto de todas las sucesiones con rango $\\{0, 1\\}$. 

**Corolario**. El conjunto de cantor es no numerable.



## Función Ternaria de Cantor



<img src="https://upload.wikimedia.org/wikipedia/commons/7/7f/Cantor_function.gif" alt="Función ternaria de Cantor" style="zoom:35%;" />

Sea $x \in [0, 1]$ y sea $(a_n)_3$ su expansión ternaria. Sea $N = \infty$ si $x \in C$ y sea $N$ el natural mínimo tal que $a_N = 1$. Sea $b_n = \frac{a_n}{2}$ para $n < N$ y $b_N = 1$. Definamos 
$$
f(x) = \sum_{n=1}^N \frac{b_n}{2^n}.
$$
Lo primero que tenemos que ver es que esta función está bien definida. Esto es, tenemos que demostrar que $f(x)$ es independiente de la representación ternaria de $x$. 



## Medida

En teoría de la medida se conoce el siguiente teorema.

**Teorema**. Si $A$ es numerable, entonces $m A = 0$.

El conjunto de Cantor muestra que el converso no es cierto. Este conjunto es no numerable y sin embargo



$$
m C = \lim_{n \to \infty} m P_n = \lim_{n \to \infty} \left(\frac{2}{3}\right)^n = 0.
$$


Podemos construir conjuntos de parecidos al conjunto de Cantor de la siguiente manera. Sea $0 < \alpha < 1$. Generemos los conjuntos $P_{n, \alpha}$ de la misma manera como con el conjunto de Cantor pero removiendo los intervalos centrales con longitud $\frac{\alpha}{3^n}$.  Definamos al conjunto 


$$
C_\alpha = \bigcap_{n}^\infty P_{n, \alpha}.
$$



Como $C_\alpha$ es la intersección de conjuntos cerrados, $C_\alpha$ es cerrado. Además, la medida de $P_{n, \alpha}$ es $ 1 - \frac{\alpha}{3}\sum_{k=0}^n (\frac{2}{3})^k$. Entonces


$$
\begin{eqnarray}
m C_\alpha &=& \lim_{n \to \infty} m P_{n, \alpha} \\
&=& \lim_{n \to \infty} \left( 1 - \frac{\alpha}{3}\sum_{k=0}^n \left(\frac{2}{3}\right)^k \right)\\
&=& 1 - \frac{\alpha}{3} \cdot \frac{1}{1 - \frac{2}{3}}\\
&=& 1 - \alpha.
\end{eqnarray}
$$


A los conjuntos $C_\alpha$ se les conoce como **conjuntos de Cantor generalizados.**

**TO DO** 

- [ ] Demostrar cosas de funcion ternaria.
- [ ] Correccion de demostracion ternaria

---

*Notas:*

[^1]: Vea el siguiente [teorema](https://en.wikipedia.org/wiki/Cantor%27s_intersection_theorem).
[^2]: Definamos $(y_n)_3$ como $y_n = a_n$ para toda $n < k$ y $y_n = 0$ para toda $n \geq k$. También definamos $(z_n)_3$ como $z_n = a_n$ para $n < k$ y $z_n = 2$ para toda $n \geq k$. Entonces $(y_n)_3 < (a_n)_3 < (z_n)_3$. Luego, $(a_n)_3$ es un número entre dos elementos del conjunto de Cantor que están a una distancia igual a $\frac{1}{3^{k-1}}$.

---

