---
layout: post
title:  "Problema de Punto fijo 1"
date:   2020-11-05 10:42:07 -0600
categories: análisis-real punto-fijo
---

**Problema**. Sea $f: \mathbb{R} \rightarrow \mathbb{R} $ una función continua tal que $1$ aparece en  $f(x), f(f(x)), f(f(f(x))), \ldots $ para toda $x$ en $\mathbb{R}$. Demuestre que $ f(1) = 1$.

Cuando tratamos temas de continuidad comúnmente utilizamos alguna consecuencia del [Teorema del Valor Intermedio](https://es.wikipedia.org/wiki/Teorema_del_valor_intermedio) . En este caso utilizaremos la siguiente proposición.

**Proposición**. Sean $ f, g: [a, b] \rightarrow \mathbb{R}$ funciones continuas tales que $f(a) \leq g(a)$ y  $f(b) \geq g(b)$. Entonces existe $x \in [a, b]$ tal que $ f(c) = g(c)$.

El argumento central de la demostración se basa en la siguiente observación. Si existe un $ p \in \mathbb{R}$ diferente de $1$ que es punto fijo de la función $ f$, entonces $1$ no puede aparecer en la sucesión $ f(p), f(f(p)), f(f(f(p))), \ldots$; esto contradiría la hipótesis del problema. Con esto en mente y con la proposición anterior a la mano, veamos la solución.

**Solución**: Procedamos por contradicción. Suponga que $ f(1) \neq 1$ y consideremos el caso $ f(1) > 1$ (el caso $f(1) < 1 $ se resuelve de manera similar). Sea $e: \mathbb{R} \rightarrow \mathbb{R}$ la función identidad en los reales y sea $ n$ el natural más pequeño que satisface $ f^{(n)}(1) \leq 1$. Observe que $ f(1) > 1 = e(1) $ y $f(f^{(n-1)}(1)) \leq 1 < f^{(n-1)}(1) =  e(f^{(n-1)}(1))$. Entonces existe un $p \in (1, f^{(n-1)}(1))$ tal que $ f(p) = e(p) = p$. Esto contradice la hipótesis del problema. Por tanto, la suposición $f(1) \neq 1$ debe ser falsa. $\blacksquare$

Nota: En la demostración $ f^{(k)}$ denota la composición de la función $f$ en sí misma $k$ veces.

**DRAFT**