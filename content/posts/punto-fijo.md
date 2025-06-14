---
title:  "Un problema de punto fijo"
date:   2020-11-05 10:42:07 -0600
lastmod: 2025-06-13 18:55:00
draft: false
tags: ["analisis"]
---

> Sea $f: \mathbb{R} \rightarrow \mathbb{R} $ una función continua tal que $1$ aparece en
> $f(x), f(f(x)), f(f(f(x))), \ldots $ para toda $x$ en $\mathbb{R}$. Demuestre que $ f(1) = 1$.


Este problema podemos resolverlo con dos ideas clave: 
- Como es habitual en temas de continuidad, utilizaremos alguna consecuencia
del [Teorema del Valor Intermedio](https://es.wikipedia.org/wiki/Teorema_del_valor_intermedio).
- El único punto fijo de $f$ es $1$, pues de lo contrario, si $p \neq 1$ satisface
que $f(p) = p$, entonces $f^{(n)}(p) = p$ para toda $n \in \mathbb N$, y por tanto
$1$ jamás aparece en la sucesión $f(p), f(f(p)), \ldots$.

En lo siguiente, denotemos por $ f^{(k)}$ la composición de la función $f$ 
en sí misma $k$ veces, con la convención de que $f^{(0)}(x) = x$ y
$f^{(n + 1)}(x) = f(f^{(n)}(x))$.

**Demostración**. Suponga que $ f(1) \neq 1$ y considere el caso $ f(1) > 1$
(el caso $f(1) < 1 $ se resuelve de manera similar). Afirmamos que la
sucesión $\\{ f^{(n)}(1) \\}_{n \in \mathbb N}$ es **estrictamente creciente.**

Para esto, defina la función **continua** $g: \mathbb R \rightarrow \mathbb R$
como $g(x) = f(x) - x$.
Si $f^{(2)}(1) \le f^{(1)}(1)$, entonces $g(f(1)) = f(f(1)) - f(1) \leq 0$.
En caso de que $g(f(1)) = 0$, se tiene que $f(1) \neq 1$ es punto fijo de $f$,
lo cual implica que $1$ nunca aparece en la sucesión $\\{f^{(n)}(1)\\}$. Si
$g(f(1)) < 0$, dado que $g(1) = f(1) - 1 > 0$ y $g$ es una función continua,
por el Teorema del Valor Intermedio garantiza que existe un punto $p \in (1, f(1))$ tal que
$g(p) = 0$. Es decir, existe un punto $p \neq 1$ que es punto fijo de $f$, que de nuevo,
implica que la sucesión $\\{f^{(n)}(1)\\}$ no contiene a $1$ como uno de sus términos.
Por tanto, la hipótesis de que $f^{(2)}(1) \leq f^{(1)}(1)$ debe ser falsa.

Suponga que la sucesión $\\{f^{(n)}(1)\\}$ es estrictamente creciente hasta un entero
$k$. Por contradicción, suponga que $f^{(k+1)}(1) \leq f^{(k)}(1)$. Si
$f^{(k+1)}(1) = f^{(k)}(1)$, entonces $f^{(k)}(1) > 1$ es un punto fijo de $f$. Y si 
$f^{(k+1)}(1) < f^{(k)}(1)$, como $g$ es continua, por el Teorema del Valor Intermedio podemos
encontrar un $p \in (f^{(k-1)}(1), f^{(k)}(1))$ tal que $g(p) = 0$; es decir,
$p > 1$ es punto fijo de $f$. Ambos casos contradicen el hecho de que $1$ aparece 
en la sucesión $\\{f^{(n)}\\}$. Por tanto $f^{(k)}(1) < f^{(k+1)}(1)$ y por inducción
concluimos que la sucesión $\\{f^{(n)}\\}$ es estrictamente creciente.

No obstante, si $\\{f^{(n)}\\}$ es una sucesión estrictamente creciente, $1$ 
no aparece en la sucesión, pues $f(1) > 1$. Por tanto, la hipótesis de que $f(1) > 1$
debe ser falsa. Concluimos que $f(1) \leq 1$.

De manera análoga, si $f(1) < 1$, se demuestra que la sucesión $\\{ f^{n}(1) \\}$
es estrictamente decreciente y, por tanto $1$ tampoco puede aparecer en ella, 
contradiciendo la hipótesis. 

En conclusión, la única posibilidad restante es que $f(1) = 1$. 🤙🏻

> *Este texto fue reescrito, pues la "solución" original estaba mal. Última modificación: 13 de junio de 2025*
