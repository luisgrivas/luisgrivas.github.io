---
layout: post
title:  "Longitud de Arco"
date:   2020-11-05 03:59:07 -0600
categories: posts
tags: [analisis-real, geometria-diferencial]
---

## Funciones de variación acotada 

**Definición**. Sea $f:[a, b] \rightarrow \mathbb{R}$ una función. Decimos que $f$ es una función de **variación acotada**, si existe $M > 0$ tal que  $$\sum_{k=1}^n \lvert f(x_k) - f(x_{k-1}) \lvert < M,$$
para toda partición $P = \\{ x_0, x_1, \ldots, x_n \\}$ de $[a, b]$.

**Ejemplo**. Consideremos la función $f(x) = x$ en $[0, 1]$. Para cualquier partición $P$ de $[0, 1]$, se tiene que 

$$\sum_{k=1}^n \lvert f(x_k) - f(x_{k-1}) \lvert = \sum_{k=1}^n (x_k - x_{k-1}) = 1.$$

Por tanto $f(x) = x$ es una función de variación acotada. 

**Nota**. Notése que en la suma anterior, solo hicimos uso de la monotonía de la función $f$, por tanto, se concluye inmediatamente que las funciones monónotonas en intervalos $[a, b]$ son de variación acotada. 

No toda función continua es función de variación acotada. Sin embargo, suponga que $f$ es continua y diferenciable en $[a, b]$. Sea $P$ es una partición de $[a, b]$, entonces, por el Teorema del Valor Medio, se tiene que 
$f(x_k) - f(x_{k-1}) = f^\prime(t_k) (x_k - x_{k-1})$, para algún $t_k \in (x_{k-1}, x_k)$. Luego,

$$\sum_{k=1}^n \lvert f(x_k) - f(x_{k-1}) \lvert = \sum_{k=1}^n \lvert f^\prime(t_k)(x_k - x_{k-1}) \lvert =  \sum_{k=1}^n \lvert f^\prime(t_k) \lvert (x_k - x_{k-1}). $$

De lo anterior, podemos ver que si $f^\prime$ está acotada en $[a, b]$, entonces $f$ es de variación acotada.

**Ejemplo.** Sea $f$ en $[0, 1]$ definida como $f(x) = 1$, si $x$ es racional; $f(x) = 0$, si $x$ es irracional. Sea $P$ una partición con un número impar de elementos y definida de la siguiente manera: $x_k$ racional si $k$ es impar, $x_k$ irracional si $k$ es par. Entonces 
$$ \sum_{k=1}^n \lvert f(x_k) - f(x_{k-1}) \lvert = n.$$
Esto muestra que $f$ no es de variación acotada. 

El anterior ejemplo muestra que no toda función acotada es de variación acotada. Sin embargo, toda función de variación acotada necesariamente es acotada. Esto se deduce inmediatamente si consideramos la partición $P = \{a, t, b\}$ y la desigualdad 
$$\lvert f(t) - f(a) \lvert + \lvert f(b) - f(t) \lvert \leq M. $$

## Curvas rectificables y longitud de arco

**Definición**. Sea $f: [a, b] \rightarrow \mathbb{R}^n$ una función. Sea $P = \\{x_0, x_1, \ldots, x_n\\}$ una partición de $[a, b]$. Definamos 
$$ \Lambda_f(P) = \sum_{k=1}^n \lvert \lvert f(x_k) - f(x_{k-1}) \lvert \lvert. $$
Si el conjunto $L = \\{\Lambda_f(P): P \text{ partición de } [a, b] \\}$ está acotado superiormente, se dice que $f$ es **rectificable**. Al número $ \Lambda_f(a, b) = \sup L$ se le conoce como longitud de arco de $f$. 

Si el conjunto $L$ no está acotado superiormente se dice que $f$ es no rectificable.

Note que si $f(t) = (f_1(t), \ldots, f_n(t))$, entonces 

$$\lvert f_i(x_k) - f_i(x_{k-1}) \lvert \leq \lvert \lvert f(x_k) - f(x_{k-1}) \lvert \lvert \leq \sum_{i=1}^{n} \lvert f_i(x_k) - f_i(x_{k-1}) \lvert, $$

para $i=1, \ldots, n$ y para toda partición $P$ de $[a, b]$. Luego, una condición necesaria y suficiente para que $f$ sea rectificable es que cada una de las funciones $f_i$ sean de variación acotada. Esto lo enunciamos en el siguiente teorema.

**Teorema.** Sea $f: [a, b] \rightarrow \mathbb{R}^n$ de componentes $f = (f_1, \ldots, f_n)$. Entonces $f$ es rectificable si y solo si cada componente $f_i$ es de variación acotada. 

Una objetivo interesante es determinar si existe una forma analítica de calcular la longitud de arco. Consideremos una función $f: [a, b] \rightarrow \mathbb{R}^m$ con  componentes $f = (f_1, \ldots, f_m)$ y una partición $P = \{a=x_0, x_1, \ldots, b=x_n \}$ de $[a, b]$. Si $f$ es diferenciable en $[a, b]$, podemos aplicar el Teorema del Valor Medio para obtener

$$f_i(x_k) - f_i(x_{k-1}) =  f_i^\prime(t_k^{(i)}) (x_k - x_{k-1}), $$

con $t_k^{(i)} \in (x_{k-1}, x_k)$ y para $i=1, \ldots, m$. De aquí se sigue que, 

$$ \Lambda_f(P) = \sum_{k=1}^n \lvert \lvert f(x_k) - f(x_{k-1}) \lvert \lvert = \sum_{k=1}^n (x_k - x_{k-1}) \sqrt{f^\prime_1(t_k^{(1)})^2 + \ldots + f^\prime_m(t_k^{(m)})^2 }. $$

Ahora, si además suponemos que $f^\prime$ es continua en $[a, b]$, esto implica que cada $f^\prime_i$ es continua en $[a, b]$. Luego, $f_i^\prime$ es uniformemente continua en $[a, b]$. Sea $\epsilon > 0$. Entonces, para cada $f_i$ existe un $\delta_i > 0$ tal que si $\lvert x - y \lvert < \delta_i$, entonces $\lvert f^\prime_i(x) - f^\prime_i(y) \lvert < \frac{\epsilon}{(b - a)\sqrt{m }}$. Si hacemos $\delta = \min\{\delta_1, \ldots, \delta_m \}$ y consideramos una partición $P$ cuya norma sea menor que $\delta$, entonces 
$$\begin{eqnarray*} 
\Delta_f(P) - S(P, \lvert \lvert f^\prime\lvert \lvert) &=& \sum_{k=1}^n (x_k - x_{k-1}) \sqrt{f^\prime_1(t_k^{(1)})^2 + \ldots + f^\prime_m(t_k^{(m)})^2 }\\
&-& \sum_{k=1}^n (x_k - x_{k-1}) \sqrt{f^\prime_1(t_k)^2 + \ldots + f^\prime_m(t_k)^2 } \\
&\leq& \sum_{k=1}^n (x_k - x_{k-1}) \sqrt{ (f^\prime_1(t_k^{1}) - f^\prime_1(t_k))^2 + \ldots + (f^\prime_m(t_k^{m}) - f^\prime_m(t_k))^2 }\\
&<& \sum_{k=1}^n (x_k - x_{k-1}) \frac{\epsilon}{b-a} \\
&= & \epsilon. 
\end{eqnarray*} $$

Por otro lado, como $f$ es rectificable, existe una partición $P^\prime_\epsilon$ tal que 

$$ \Lambda_f(a, b) - \Lambda_f(P) < \epsilon, $$ 

para cualquier partición $P$ más fina que $P^\prime_\epsilon.$

Finalmente, observe que la continuidad de $f^\prime$ implica que $\parallel f^\prime \parallel $ es Riemann integrable. Luego, existe una partición $P^{\prime\prime}_\epsilon$ tal que

$$\left\lvert S(P, \lvert \lvert  f^\prime \lvert \lvert) - \int_{a}^b \lvert \lvert f^\prime \lvert \lvert dt  \right\lvert < \epsilon, $$
para toda partición $P$ más fina que $P^{\prime\prime}_\epsilon$.

Se sigue que si $P_\epsilon \supset P^\prime_\epsilon \cup P^{\prime\prime}_\epsilon$ es una partición de $[a, b]$ cuya norma es menor que $\delta$, se tiene que

$$\begin{eqnarray*}
\left\lvert \Lambda_f(a, b) - \int_{a}^b \lvert \lvert f^\prime \lvert \lvert dt \right\lvert  &\leq& \left\lvert \Lambda_f(a, b) - \Lambda_f(P) \right\lvert + \left\lvert \Lambda_f(P) - \int_{a}^b \lvert \lvert f^\prime \lvert \lvert dt \right\lvert \\
&<&  \epsilon + \left\lvert \Lambda_f(P) - S(P, \lvert \lvert f^\prime \lvert \lvert) \right\lvert + \left\lvert S(P, \lvert \lvert f^\prime\lvert \lvert) - \int_{a}^b \lvert \lvert f^\prime \lvert \lvert dt \right\lvert\\
&<& 3 \epsilon
\end{eqnarray*}$$

para toda partición $P$ más fina que $P_\epsilon$. Esto demuestra que $$\Lambda_f(a, b) = \int_{a}^b \lvert \lvert f^\prime \lvert \lvert dt.$$

Resumamos lo anterior en el siguiente teorema.


**Teorema.** Si $f: [a, b] \rightarrow \mathbb{R}^n$ tiene derivada $f^\prime$ continua en $[a, b]$, entonces la longitud de arco $\Lambda_f(a, b)$ está dada por
$$ \Lambda_f(a, b) = \int_{a}^b \lvert \lvert f^\prime(t) \lvert \lvert dt.$$

## Reparametrizaciones

## Camino más corto

**DRAFT** 