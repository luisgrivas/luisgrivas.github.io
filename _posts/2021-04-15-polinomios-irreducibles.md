---
layout: post
title: "Polinomios irreducibles sobre GF(p)"
date: 2021-04-15 14:30:00
categories: posts
tags: álgebra 
---

En este post demostraremos el siguiente teorema:

**Teorema 1.** El número de polinomios mónicos irreducibles de grado $n$ sobre $GF(p)$ es

$$ N_n = \frac{1}{n}\sum_{d \mid n} \mu(d) p^{n/d}, $$


donde la sumatoria recorre todos los divisores $d$ de $n$.

## Campos finitos

**Teorema 2.** Sea $p$ un número primo y $n$ un entero positivo. El polinomio $x^{p^n}-x$ es el producto de todos los polinomios mónicos irreducibles sobre $GF(p)$ cuyo grado $d$ divide a $n$.

*Demostración:* Sea $q(x) \in GF(p)[x]$ un polinomio mónico e irreducible de grado $d$. Sea $K = GF(p)[x] / (q)$ el campo cuya dimensión como espacio vectorial sobre $GF(p)$ es $d$. Si $q(x) \mid x^{p^n} - x$, entonces $K$ es (isomorfo a) un subcampo del campo de descomposición  $GF(p^n)$ de $x^{p^n}-x$. Luego, $n = [GF(p^n): GF(p)] = [GF(p^n):K] [K:GF(p)] = [GF(p^n):K] \cdot d$, es decir, $d \mid n$.



## Producto de Dirichlet y fórmula de inversión de Möbius 

<img src="https://upload.wikimedia.org/wikipedia/commons/4/4f/August_Ferdinand_M%C3%B6bius.png" style="zoom:35%;" />

**Definición.** Definimos a la función de Möbius $\mu$ como sigue:

$$
\mu(1) = 1;
$$
Si $n > 1$, descomonemos a $n$ en potencias de primos $n = p_1^{\alpha_1} \cdots p_k^{\alpha_k}$. Entonces


$$
\mu(n) = \cases{(-1)^k \ \ \text{si } \alpha_1 = \cdots = \alpha_k = 1, \\ 0 \ \ \ \ \ \ \ \ \ \ \text{en otro caso.}}
$$

 

**Definición.** Si $f$  $g$ son dos funciones aritméticas definimos su producto de Dirichlet como la función aritmética $h$ definida por
$$
h(n) = \sum_{d \mid n} f(d) g\left(\frac{n}{d}\right).
$$
Escribiremos $f \ast g$ en lugar de $h$. 

El plan de esta sección es mostrar que las funciones aritméticas $f$ tales que $f(1) \neq 0$ forman un grupo abeliano bajo el producto de Dirichlet. De esta manera, la fórmula de inversión de Möbius se deduce directamente bajo operaciones básicas de grupos. 

**Lema.** La multiplicación de Dirichlet es asociativa y conmutativa. 

*Demostración:* Sean $f, g$ y $k$ funciones aritméticas. Observe que, si $d$ es divisor de $n$, entonces $\frac{n}{d}$ también es divisor de $n$. Se sigue directamente de este hecho que $(f \ast g)(n) = \sum_{d \mid n} f(d) g\left(\frac{n}{d}\right) =  \sum_{d \mid n} g(d) f\left(\frac{n}{d}\right) = (g \ast f)(n).$

Para demostrar que el producto es asociativo, vease que 


$$
\begin{eqnarray}
(f \ast g) \ast k &=& \left( \sum_{d \mid n} f(d) g\left(\frac{n}{d}\right) \right) \ast k \\
&=& \sum_{d^\prime \mid n} \left( \sum_{d \mid d^\prime} f(d) g\left(\frac{d^\prime}{d}\right) \right) k\left(\frac{n}{d^\prime}\right) \\
&=& \sum_{abc = n} f(a)g(b)k(c).
\end{eqnarray}
$$


De manera similar, encontramos que 


$$
f \ast (g \ast k ) = \sum_{abc = n} f(a)g(b)k(c).
$$


El elemento identidad bajo el producto de Dirichlet es el siguiente.

**Definición.** La función aritmética $I$ definida como


$$
I(n) = \cases{1 \ \ \ \text{si } n = 1,\\ 0 \ \ \ \text{si } n > 1.}
$$


se le conoce como función identidad.  

**Lema.**  Para toda función aritmética $f$ se satisface que $f \ast I = I \ast f = f$.

*Demostración:* simple cálculo.

**Lema.** Si $f$ es una función aritmética tal que $f(1) \neq 0$, entonces existe una función aritmética $f^{-1}$ llamada inversa de Dirichlet tal que $f \ast f^{-1} = f^{-1}\ast f = I$. Además, podemos encontrar una expresión para $f^{-1}$ dada por la siguiente relación de recurrencia:



$$
f^{-1}(1) = \frac{1}{f(1)}, \ \ \ \ f^{-1}(n) = \frac{-1}{f(1)} \sum_{d \mid n \\ d < n} f\left(\frac{n}{d}\right)f^{-1}(d) \ \ \text{ para } n > 1.
$$
*Demostración:* 



Del lema anterior se deduce  que la función aritmética $u$ definida como $u(n) = 1$ para toda $n$ es la inversa de Dirichlet de la función de Möbius $\mu$.



**Teorema 3.** El conjunto de todas las funciones aritméticas $f$ tales que $f(1) \neq 0$ forman un grupo abeliano bajo el producto de Dirichlet. 

**Teorema (Fórmula de inversión de Möbius)**  La ecuación 


$$
f(n) = \sum_{d \mid n} g(d),
$$


implica


$$
g(n) = \sum_{d \mid n} f(d) \mu\left(\frac{n}{d} \right).
$$


*Demostración:* Si $f(n) = \sum_{d \mid n} g(d)$, entonces $f = g \ast u$. Multiplicando por $\mu$ obtenemos $f \ast \mu = (g \ast u) \ast \mu = g \ast (u \ast \mu) = g \ast I = g.$



### Resultado principal

Observe que 


$$
p^n = \sum_{d \mid n} d N_n.
$$


Luego, por la fórmula de inversión de Möbius, obtenemos la expresión


$$
N_n = \frac{1}{n} \sum_{d\mid n}\mu(d)p^{n/d}.
$$

**Referencias**

* Simmons, G. J., The Number of Irreducible Polynomials of Degree n over GF(p), Amer. Math. Monthly 77 (1970), pp. 743-745.
* Apostol, T.M., Introducción a la Teoría Analítica de Números, Editorial Reverté

---

