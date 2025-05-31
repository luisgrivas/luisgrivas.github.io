---
layout: post
title: "Teorema de Sard"
date: 2021-09-17 23:58:00
categories: posts
tags: topología-diferencial
---

En estas notas demostraremos el siguiente teorema

**Teorema de Sard.** Los valores críticos de un mapeo diferencial en variedades tiene medida de Lebesgue cero. 

Recordemos que la medida de Lebesgue en $\mathbb R^n$ se define como 
$$
\lambda(C) =  \inf \left\{\sum_{i=1}^\infty \lvert W_i \rvert : C \subset \bigcup_{i=1}^\infty W_i \ \text{ con } W_i \text{ cubos en } \mathbb R^n \right\}
$$
En particular, un subconjunto $C$ de $\mathbb R^n$ tiene **medida cero** si, para toda $\epsilon > 0$, existe una sucesión de cubos $W_i \subset \mathbb R^n$ con $W_i \subset \mathbb R^n$ , $C \subset \cup_{i=1}^\infty W_i$ y $\sum_{i=1}^\infty \lvert W_i \rvert < \epsilon$. 

**Lema.** Sea $U\subset \mathbb R^n$ un abierto y $C \subset U$ un conjunto de medida cero. Si $f: U \rightarrow \mathbb R^n$ es diferenciable, entonces $f(C)$ tiene medida cero. 

*Demostración:*



Decimos que un conjunto $C$ de una variedad diferenciable $M$ tiene medida cero si para toda carta $h: U \rightarrow U^\prime \subset \mathbb R^m$, el conjunto $h(C \cap U)$ tiene medida cero en $\mathbb R^m$.



**Teorema de Fubini**. Sea $\mathbb R^{n-1}_t = \{x \in \mathbb R^n: x_n = t\}$; sea $C \subset \mathbb R^n$ Compacto y $C_t = C \cap \mathbb R^{n-1}_t$ con medida cero en $\mathbb R^{n-1}_t \simeq \mathbb R^{n-1}$ para toda $t \in \mathbb R$. Entonces $C$ tiene medida cero en $\mathbb R^n$. 

*Demostración:*





**Draft**