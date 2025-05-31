---
layout: post
title: "Aplicaciones de Selección Dependiente Aleatoria"
date: 2025-02-07 23:16:00
categories: posts
tags: grafos
draft: true
---
> Lo presentado en este texto son notas de estudio del artículo [Dependent Random Choice](https://arxiv.org/abs/0909.3271) de 
Jacob Fox y Benny Sudakov. 

El método de Selección Dependiente Aleatoria (SDA) pertenece al conjunto de técnicas denominadas como "Método Probabilístico".
Esta técnica es utilizada cuando deseamos encajar una subgráfica $H$ con ciertas características (bipartitas, ciclos, etcétera)
dentro de una gráfica $G$. Si la gráfica $G$ es lo suficientemente densa, frecuentemente es útil encontrar un subconjunto
de vértices $U$ que tenga una estructura rica en el sentido de que todo subconjunto pequeño en $G$
tiene muchos vecinos en común. Consecuentemente, podemos utilizar algún método _greedy_ para encajar la gráfica 
$H$ utilizando esta propiedad del conjunto $U$. SDA establece la existencia de este conjunto, aunque sin mostrar claramente
cómo podríamos encontrarlo (en este sentido, no es una técnica constructiva).

Para un vértice $v$ en una gráfica $G$, sea $N(v)$ el conjunto de vecinos de $v$ en $G$.
Dado un conjunto $U$ de $V(G)$, definimos _la vecindad común_ $N(U)$ de $U$ como  el
conjunto de todos lo vértices en $G$ que son adyacentes a $U$.

**Lema Básico de SDA**. Sea $G = (V, E)$ una gráfica con $\vert V \vert = n$ vértices
y grado promedio $d = 2 \vert E \vert / n$. Si existen enteros positivos
$a, m, r$ y $t$ tales que
$$\frac{d^t}{n^{t-1}} - \binom{n}{r} \left(\frac{m}{n}\right)^t \geq a$$
entonces $G$ contiene un subconjunto de vértices $U$ en al menos $a$ vértices tal que
cada subconjunto de $r$ vértices en $U$ tiene al menos $m$ vécinos en común; es decir,
si $S \subset U$ y $\vert S \vert = r$, entonces $N(S) \geq m$.

El siguiente ejemplo (debido al Profesor Yufei Zhao) nos puede ayudar a entender de manera intuitiva el Lema Básico:

> Suponga que se desea modelar la red de conocidos entre estudiantes de una universidad. Suponga que cada estudiante
> en la universidad conoce un conjunto suficientemente grande de estudiantes, digamos $d$. SDA establece que podemos encontrar un 
> conjunto $U$ de estudiantes, tales que todo subconjunto de tamaño $r$ de $U$ tiene al menos un número mínimo de
> conocidos en común (digamos $m$). Podemos pensar en $U$ como una facultad dentro de la universidad (por ejemplo, la facultad 
> de matemáticas), y cada subconjunto de tamaño $r$ como grupos de estudiantes matriculados a una materia en específico.
> Es de esperarse que estos estudiantes tengan un número de conocidos en común grande.

_Demostración_: Sea $T$ un conjunto de $t$ vértices en $G$ seleccionados de manera uniformemente
aleateoria sin repetición. ¿Cuál es la probabilidad de que dado un vértice $v \in V(G)$, este pertenezca
a $N(T)$? Notemos que $v \in N(T)$ si y solo si $(v, w)$ es una arista en $G$
para toda $w \in T$. Es decir, $v \in N(T)$ si y solo si $T \subset N(v)$. Dado que $T$ tiene 
$t$ vértices, el evento $T \subset N(v)$ ocurre con probabilidad $\left(\frac{N(v)}{n}\right)^t$.
<!--TODO: verificar esto-->

Dado lo anterior, podemos estimar la siguiente cota inferior para el valor esperado
del número de vértices en $N(T)$ como sigue:

$$\begin{eqnarray}E[\vert N(T)\vert] &=& \sum_{v \in V(G)}P(v \in N(T))\\
&=& \sum_{v \in V(G)} \left(\frac{\vert N(v)\vert }{n}\right)^t \\
&=& n^{1-t} \frac{\sum_{v \in V(G)} (\vert N(v) \vert)^t}{n}\\
&\geq&n^{1-t} \left( \frac{\sum_{v \in V(G)}\vert N(v) \vert}{n} \right)^t &&  (\text{ por convexidad de la función } z \mapsto z^t) \\
&=& \frac{d^t}{n^{t-1}} && (\text{Handshake Lemma)}
\end{eqnarray}
$$

Ahora bien, diremos que un subconjunto de $r$ vértices $S$ en $N(T)$ es _malo_ si este tiene menos de $m$ vértices en común;
es decir, $S$ es malo si $S \subset N(T)$, $\vert S \vert = r$ y $N(S) < m$. La pregunta que nos interesa 
contestar es ¿podemos estimar alguna cota superior al valor esperado de la cantidad de subconjuntos malos en $N(T)$?
En primer lugar, note que $S \subset N(T)$ ocurre con probabilidad $\left(\frac{\vert N(S) \vert}{n}\right)^t$. En segundo,
existen a lo más $\binom{n}{r}$ conjuntos de tamaño $r$ tales que $\vert N(S) \vert < m$. Luego,

$$E[\text{# de conjuntos malos en }N(T)] < \binom{n}{r} \left(\frac{m}{n}\right)^t.$$ 

Por linealidad del valor esperado,

$$E[\vert N(T) \vert - \text{# de subconjuntos malos en } N(T)] \geq \frac{d^t}{n^{t-1}} - \binom{n}{r} \left(\frac{m}{n}\right)^t \geq a.$$

Esto asegura que existe una elección de vértices $T$ en $G$ en el que la _cardinalidad de $N(T)$ menos el número de subconjuntos
malos en $N(T)$ es mayor a $a$._ Borre un vértice para cada conjunto malo $S$ en $N(T)$ y sea
$U$ el conjunto restante. Entonces $U$ tiene al menos $a$ vértices y todos sus subconjuntos
de tamaño $r$ tienen al menos $m$ vecinos en común. $\blacksquare$

## Números de Turán para gráficas bipartitas 

Para una gráfica $H$ y un entero positivo $n$, el número de Turán $ex(n, H)$ denota el 
máximo número de aristas en una gráfica de $n$ vértices que _no contiene_ a $H$ como 
subgráfica. 

**Teorema**. Si $H = (A \cup B, F)$ es una gráfica bipartita cuyos vértices en $B$ tienen al menos
grado $r$ , entonces $ex(n, H) \leq c n^{2 - \frac{1}{r}}$, donde $c = c(H)$ depende 
únicamente de $H$.

_Demostración_. La idea de la demostración consiste en utilizar SDA para encontrar un encaje de $H$ 
en toda gráfica $G$ con más de $c n^{2 - \frac{1}{r}}$ vértices.

Sean $a = \vert A \vert$, $b =\vert B\vert$, $m = a + b$, $t = r$ y $c = \max\left(a^{1/r}, \frac{3(a + b)}{r}\right)$ 
y suponga que $G$ es una gráfica en $n$ vértices con _al menos_ $cn^{2-\frac{1}{r}}$ aristas.
Entonces, el grado promedio $d$ de $G$ satisface que $d \geq 2 cn^{1 - \frac{1}{r}}$ (`Handshake Lemma`).

$$
\begin{eqnarray}
\frac{d^t}{n^{t-1}} - \binom{n}{r} \left(\frac{m}{n}\right)^t
&\geq& \frac{(2c)^r n^{r-1}}{n^{r-1}} - \frac{n^r}{r!}\left(\frac{a + b}{n}\right)^r && ( \text{utilizando que }  \binom{n}{r} < \frac{n^r}{r!} )\\
&\geq& (2c)^r - \left(\frac{e(a + b)}{r}\right)^r && (\text{ aquí } r! \geq (r / e)^r)\\
&\geq& c^r && (\text{ utilizando que } c \geq 3(a + b) / r )\\
&\geq& a && (\text{ y aquí } c \geq a^{1/r}).
\end{eqnarray}
$$

Utilizando el **Lema Básico** encontramos un conjunto $U$ de vértices en $G$ con $\vert U \vert = a$ y tal que
todos sus subconjuntos de tamaño $r$ tienen al menos $a + b$ vecinos en común.


Ahora bien, para encontrar un encaje de $H$ en $G$, podemos proceder como sigue. Sea $f: A \rightarrow V(G)$ una función
inyectiva. Etiquetemos los vértices de $B$ como $v_1, \ldots, v_b$. Encaramos a los vértices de $B$ siguiendo este orden.
Suponga que el vértice a encajar es $v_i \in B$. Sea $N_i \subset A$ aquellos vértices en $H$ que son adyacentes a $v_i$,
por lo que $\vert N_i \vert \leq r$. Dado que $f(N_i)$ es un subconjunto de $U$ de cardinalidad a lo más $r$, existen al menos $a + b$
vértices adyacentes a todos los vértices de $f(N_i)$. Dado que el número de vérties encajados hasta el momento es menor a $a + b$, existe
un vértices $w \in V(G)$ que es adyacente a todos los vértices $f(N_i)$ y está disponible para ser utilizado en el encaje. Haga
$f(v_i) = w$. Siguiendo inductivamente, podemos proceder de esta manera para encajar todos los vértices de $B$ en $G$.

# Encaje de una 1-subdivisión en una Gráfica Completa
Una **copia topológica** de una gráfica $H$ es una gráfica formada mediante reemplazos de las aristas de $H$ por
trayectorias internamente disjuntas. En el caso especial en el que todas estas trayectorias son de longitud $k$,
decimos que esta es una t-subdivisión de $H$.


**Teorema**. Sea $G$ una gráfica en $n$ vértices con $\epsilon n^2$ aristas. Entonces $G$ contiene una 1-subdivisión de la gráfica completa con $a = \epsilon^{3/2}n^{1/2}$ vértices.

_Demostración_. Note que aquí el término $\epsilon n^2$ representa qué tan densa es la gráfica $G$. De manera similar al Teorema anterior, utilizaremos SDA para
encajar a la gráfica completa deseada en $G$.

Note que el grado promedio $d$ de la gráfica $G$ es $2 \epsilon n$. Sean $r = 2$, $t = \frac{\log n}{\log 1/\epsilon}$ y $m$ el número de vértices de una 1-subdivisión de la gráfica completa
en $a$ vértices. ¿A qué es igual este valor $m$? Dado que tengo $\binom{a}{2}$ aristas, una 1-subdivisión tendría en total $m = \binom{a}{2} + a$ vértices.
Claramente, $m < a^2$ y $\epsilon \leq 1/2$ (cualquier gráfica tiene a lo más $\frac{n(n-1)}{2}$ aristas ), entonces

$$
\begin{eqnarray}
\frac{d^t}{n^{t-1}} - \binom{n}{r} \left(\frac{m}{n}\right)^t &=& \frac{(2\epsilon n)^t}{n^{t-1}} - \binom{n}{2} \left(\frac{m}{n} \right)^t && \text{ (sustitución) } \\
&\geq& (2 \epsilon)^t n  - \binom{n}{2} \left( \frac{a^2}{2} \right)^t && \text{()} \\
&=&  (2 \epsilon)^t n  - \binom{n}{2} \left( \frac{(\epsilon^{3/2} n^{1/2})^2}{2} \right)^t && \\
\end{eqnarray}
$$
