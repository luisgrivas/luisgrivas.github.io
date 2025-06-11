---
title: "Una desigualdad L2 para funciones impares"
date: "2025-06-10 20:32:00"
tags: ["analisis"]
author: ["lfgr"]
---

Mientras me preparaba para el examen general de análisis de la UNAM, me topé con
el siguiente problema. Su solución me pareció especialmente bonita por la forma
en que combina distintas herramientas del análisis

> Sea $f: \mathbb R \rightarrow \mathbb R$ continuamente diferenciable
en $\mathbb R$ e impar. Demuestre que
$$\int_{-1}^1 f^2 \ d\lambda \le \int_{-1}^1 (f^\prime)^2 \ d \lambda.$$

**Solución.**  Si $a \in (0, 1]$, entonces

$$
\begin{align}
\left(\int_{-a}^af^\prime \ d\lambda\right)^2 &\le \left(\int_{-a}^a 1 \ d\lambda\right) \cdot
\left(\int_{-a}^a (f^\prime)^2 \ d\lambda\right)\\\\
&= 2a \int_{-a}^a (f^\prime)^2 \ d \lambda\\ \le 2a \int_{-1}^1 (f^\prime)^2 \ d\lambda,
\end{align}
$$
donde la primera desigualdad se debe a [Cauchy-Schwarz](https://en.wikipedia.org/wiki/Cauchy%E2%80%93Schwarz_inequality#L2)
en $L^2([-a, a])$ y la segunda se debe a que $(f^\prime)^2$ es no negativa.

El [Teorema Fundamental del Cálculo](https://en.wikipedia.org/wiki/Fundamental_theorem_of_calculus#Second_part)
establece que $\int_{-a}^{a} f^\prime \ d \lambda=f(a) - f(-a)$. Como $f$ es impar,
$f(a) - f(-a) = 2f(a)$. Luego,
$$2f(a)^2 \leq a \int_{-1}^{1}(f^\prime)^2 \ d\lambda,$$
para toda $a \in (0, 1]$. 

Como $f$ es impar, $f^2$ es par, así que
$$\int_{-1}^1f^2\ d\lambda = 2\int_0^1f^2 \ d\lambda.$$
Entonces,
$$\begin{align}
\int_{-1}^1 f^2 \ d\lambda &= 2\int_0^1f^2 \ d\lambda\\ \le
\left(\int_0^1 x \ d\lambda\right) \cdot  \left(\int_{-1}^1 (f^\prime)^2 \ d\lambda\right) \\\\
&= \frac{1}{2}\int_{-1}^1 (f^\prime)^2 \ d\lambda \\ \le \int_{-1}^1 ( f^\prime)^2 \ d\lambda,
\end{align}
$$
y la desigualdad requerida se sigue inmediatamente. 🤙🏻
