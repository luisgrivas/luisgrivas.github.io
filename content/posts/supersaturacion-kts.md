---
title: "Supersaturación de gráficas bipartitas completas"
date: 2025-06-09 13:00:00
draft: true
---

En su libro, [Graph Theory and Additive Combinatorics](https://yufeizhao.com/gtacbook/),
Yufei Zhao presenta el siguiente problema:

> Ejercicio 1.4.12. Demuestre que para cada par de enteros positivos $s \leq t$,
> existen constantes $C, c > 0$ tales que toda gráfica en $n$ vértices y con
> $p \binom{n}{2}$ aristas contienen al menos $c p^{st}n^{s + t}$ copias de $K_{s,t}$,
> si $p \geq C n^{-1/s}$.

<!-- Este es un resultado de los denóminados de supersaturación: ... -->

Encontré una [solución](https://math.stackexchange.com/questions/4524216/supersaturation-of-k-s-t-in-graphs-with-many-edges)
que aquí presentaré para fines de documentación. En lo siguiente, si $v$ es un vértice de $G$ y $A = N(v)$,
escribiremos $v \sim A$. 

## Cota para el número de s-estrellas en $G$

Suponga que $G$ es una gráfica tal que $V(G) = n \ge s + t$ y $e(G) = p \binom{n}{2}$.
Sea $M$ el conjunto de $s$-estrellas en $G$. Esto es,

$$M = \\{ (A, v) \in \binom{V}{s} \times V: v \sim A \\}.$$

Note que 
$$\vert M \vert = \sum_{v \in V} \left\vert \left\\{A \in \binom{V}{s}: v \sim A \right\\} \right\vert = \sum_{v \in V} \left\vert \left\\{A : A \in \binom{N(v)}{s} \right\\} \right\vert = \sum_{v \in V} \binom{d(v)}{s}.$$

Por otra parte, considere la función $f_s: \mathbb R \rightarrow \mathbb R$ definida como
$x \mapsto \binom{x}{s}$  para $x \geq s - 1$ y $0$ de otro modo. Esta función es convexa
en todo $\mathbb R$, por lo que la desigualdad de Jensen implica que 
$$
\begin{align}
\vert M \vert &=\sum_{v \in V} f_s(d(v)) \\\\
&= n \sum_{v \in V} \frac{1}{n} f_s(d(v)) \\\\ 
&\ge n f_s\left( \sum_{v \in V} \frac{d(v)}{n} \right) \\\\
&= n f_s\left( \frac{2 e(G)}{n} \right) \\\\
&= n f_s(p (n - 1 )).
\end{align}
$$

## Cota para $f_s(p(n-1))$

Si $C = 2 st^{1/2}$, esto es, $p \ge 2s t^{1/s}n^{-1/s}$, entonces se comprueba que $p(n - 1) > s - 1$. 
Por lo que 
$$
\begin{align}
\vert M \vert &\ge n f_s(p (n - 1)) \\\\
&= n \frac{(pn - p)(pn - p - 1)\cdots (pn - p - (s - 1)}{s!} \\\\
&= p^s n^{s + 1}(s!)^{-1} \left( 1 - \frac{1}{n} \right) \left(1 - \frac{1}{n} - \frac{1}{pn} \right) \cdots \left( 1 -  \frac{1}{n}  - \frac{s - 1}{pn} \right) \\\\
&\ge p^s n^{s + 1}(s!)^{-1} \left( 1 - \frac{1}{n} - \frac{s-1}{pn} \right)^{s},
\end{align}
$$

donde la desigualdad se debe a que $p(n - 1) > s - 1$.

Por otro lado, si $n \ge 2$, entonces $1 - \frac{1}{n} \ge \frac{1}{2}$. Además, dado que $p \ge 2 st^{1/s}n^{-1/s}$,
entonces $pn \ge 2s$. Por tanto

$$1 - \frac{1}{n} - \frac{s-1}{pn} \ge \frac{1}{2} - \frac{s-1}{2s} = \frac{1}{2s}.$$ 

En resumen,
$$\vert M \vert \ge \frac{1}{(2s)^s s!}p^s n^{s + 1}.$$

## Cota para el número de copias de $K_{s,t}$ en $G$
Ahora bien, para cada $A \in \binom{V}{s}$ considere la función 
$g(A) = \vert \\{ v \in V: v \sim A \\} \vert$. El **número de copias de $K_{s, t}$** en $G$ está dado por

$$
\begin{align}
\sum_{A \in \binom{V}{s}} \binom{f(A)}{t} &= \sum_{A \in \binom{V}{s}} f_t(g(A)) \\\\
&= \binom{n}{s} \sum_{A \in \binom{V}{s}} \binom{n}{s}^{-1} f_t(g(A)) \\\\
&\ge \binom{n}{s} f_t\left( \sum_{A \in \binom{V}{s}} \binom{n}{s}^{-1} g(A) \right) \\\\
&= \binom{n}{s} f_t\left( \frac{\vert M \vert}{\binom{n}{s}} \right),
\end{align}
$$
donde la desigualdad se debe a la desigualdad de Jensen y la última igualdad se debe a 
que 
$$\vert M \vert = \sum_{A \in \binom{V}{s}} = g(A).$$


## Cota para ... 
Dado que $f_t$ es una función **no decreciente**, se obtiene que 
$$\binom{n}{s}f_t \left(\vert M \vert \binom{n}{s}^{-1} \right) \ge  \binom{n}{s}f_t \left(\binom{n}{s}^{-1}\frac{p^s n^{s +1}}{(2s)^s s!}  \right).$$

Se puede comprobar que, si $p \geq 2s t^{1/s} n^{-1/s}$, entonces
$\alpha = \binom{n}{s}^{-1}\frac{p^s n^{s +1}}{(2s)^s s!} \ge t$. Luego,

$$f_t(\alpha) = \frac{\alpha (\alpha - 1) \cdots (\alpha - (t - 1) )}{t!} \ge \frac{\alpha (\alpha - 1) \cdots (\alpha - (t - 1) )}{\alpha !}. $$

De manera que 
$$\binom{n}{s} f_t(\alpha) \ge \frac{n^s \alpha^t}{s! t!} \left(1 - \frac{s-1}{n} \right)^s \left( 1 - \frac{t-1}{\alpha} \right)^t $$

Puesto que $n \ge s + 1$, $s \le t$ y $\alpha \ge t$, se obtiene

$$\frac{n^s \alpha^t}{s! t!} \left(1 - \frac{s-1}{n} \right)^s \left( 1 - \frac{t-1}{\alpha} \right)^t \ge \frac{n^s \alpha^t}{s! t! t^t} \left(\frac{2}{s + 1} \right)^s $$

Finalmente, note que

$$
\begin{align}
 \alpha^t &= \frac{p^{st} n^{st + t}}{(2s)^{st}(s!)^t} \cdot \frac{(s!)^t}{\left[n (n - 1) \cdots (n - (s - 1))\right]^t} \\\\
&\ge \frac{p^st n^{st + t}}{(2s)^{st} n^{st}} \\\\
&= \frac{p^{st} n^t}{(2s)^{st}}.
\end{align}
$$

Con esto, concluimos que el número de copias de $K_{s, t}$ en $G$ es al menos
$$ \left( \frac{2^s}{s! t! t^t (2s)^{st} (s + 1)^s} \right) p^{st}n^{s + t} $$

si $p \ge (2 s t^{1/s}) n^{-1/s}$. 😅
