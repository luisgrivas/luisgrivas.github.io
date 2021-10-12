---
layout: post
title: "Una función continua en todo R y diferenciable en ninguna parte"
date: 2020-12-14 11:45:00
categories: posts
tags: analisis-real
---

*La siguiente construcción aparece en el libro "Principles of Mathematical Analysis" de Walter Rudin.*

**Observación:** Las siguientes funciones están definidas en un espacio métrico $E$ con imagen en $\mathbb{C}$.

**Teorema 1.** La sucesión de funciones $\langle f_n\rangle$, definidas en $E$, converge uniformemente en $E$, si y solo si, para todo $\epsilon > 0$ existe un entero $N$ tal que si $m, n \geq N$ y $x\in E$, entonces $\lvert f_n(x) - f_m(x)\lvert \leq \epsilon$.

*Demostración.* $(\Rightarrow)$ Suponga que $\langle f_n \rangle$ converge uniiformemente a $f$ en $E$. Sea $\epsilon > 0$. Entonces existe un entero $N $ tal que para toda $x \in E$,  $\lvert f_n(x) - f(x) \lvert < \epsilon/2$ si $n \geq N$. Luego, si $n, m \geq N$, se tiene que 
$$
\lvert f_m(x) - f_n(x) \lvert \leq \lvert f_n(x) - f(x)\lvert + \lvert f(x) - f_m(x)\lvert < \epsilon,
$$
para toda $x \in E$.

$(\Leftarrow)$ Como $\langle f_n(x) \rangle$ es una sucesión de Cauchy en $\mathbb{C}$, esta converge para todo $x \in E$. Sea $f$ tal que $f_n \rightarrow f$ en $E$ y sea $\epsilon > 0$. Sea $N$ un entero tal que $\lvert f_n(x) - f_m(x) \lvert < \epsilon$ para $n, m \geq N$ y para toda $x \in E$. Como $f_m \to f$ cuando $m \to \infty$ y por la desigualdad del triángulo se tiene que $\lvert f_n(x) - f(x) \lvert < \epsilon$ para toda $n \geq N$ y para toda $x \in E$. *QED*



**Teorema 2.** Suponga que $\{f_n\}$ es una sucesión de funciones definidas en $E$, y suponga que $\lvert f_n(x) \lvert \leq M_n$ para toda $x\in E$ y para toda $n\in \mathbb{N}$. Entonces $\sum f_n $ converge uniformemente en $E$ si $\sum M_n$ converge en $E$. 

*Demostración.* Definamos $s_n(x) := \sum_{i=1}^nf_i(x)$. Sea $\epsilon > 0$. Como $\sum M_n$ converge, existe $N$ entero tal que 


$$
\lvert s_m(x) - s_n(x) \lvert \leq \sum_{i=n}^m \lvert f_i(x)\lvert \leq \sum_{i=n}^m M_i \leq \epsilon,
$$


si $m > n \geq N$ para toda $x \in E$. La sucesión $\langle s_n\rangle$ satisface de las condiciones del **Teorema 1** y por tanto $\langle s_n \rangle$ converge uniformemente en $E$. *QED*

 **Teorema 3.** Suponga que $f_n \to f$ uniformemente en $E$. Sea $x$ un punto límite de $E$ y suponga que 


$$
\lim_{t \to x} f_n(t) = A_n.
$$


Entonces $\langle A_n \rangle$ converge y 


$$
\lim_{t \to x}f(t) = \lim_{n \to \infty} A_n.
$$


*Demostración.* 





**Corolario**. Si $f_n$ es continua para toda $n$ y $f_n \to f$ uniformemente, entonces $f$ es continua.



## Construcción

Definamos $\phi(x) = \lvert x \lvert$, para $-1 \leq x \leq 1$. Extendamos la definición de $\phi(x)$ a todos los reales requiriendo que $\phi(x + 2) = \phi(x)$. Así, por ejemplo, $\phi(2) = \phi(0 + 2) = \phi(0) = 0$; o también $\phi(3) = \phi(1 + 2) = \phi(1) = 1$.

Para toda $s, t$ se tiene que 
$$
\lvert \phi(s) - \phi(t) \lvert \leq \lvert s - t\lvert. 
$$
En particular, $\phi$ es continua en $\mathbb{R}$. Definamos 
$$
f(x):= \sum_{n=0}^\infty \left( \frac{3}{4} \right)^n \phi(4^n x).
$$
Observe que $\lvert \left( \frac{3}{4} \right)^n \phi(4^n x) \lvert  \leq \left(\frac{3}{4} \right)^n$ para toda $x \in \mathbb{R}$ y para toda $n \in \mathbb{N}$. Además, $\sum \left( \frac{3}{4} \right)^n$ converge. Aplicando el **Teorema 2**, se sigue que $ \sum \left( \frac{3}{4} \right)^n \phi(4^n x)$ converge uniformemente a $f$.



![](/blog/assets/images/wr-connodif.gif)

