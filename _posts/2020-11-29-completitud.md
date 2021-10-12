---
layout: post
title: "Todo espacio métrico se puede completar"
date: 2020-11-29 15:24:00
categories: posts
tags: analisis
---



### Sucesiones y convergencia

La noción de convergencia en un espacio métrico se puede definir de manera equivalente al caso de convergencia en los reales con la métrica euclidiana. 

Sea $\langle x_n\rangle$ una sucesión en un espacio métrico $(X, \rho)$. Decimos que que $\langle x_n \rangle$ **converge** a un elemento $x$ en $X$, si dado $\epsilon > 0$, existe un $N$ en $\mathbb{N}$ tal que $\rho(x_n, x) < \epsilon$ si $n \geq N$. En términos de abiertos, decimos que $\langle x_n \rangle$ converge a $x$ si toda vecindad de $x$ contiene a todos salvo un número finito de términos de $\langle x_n \rangle$. Si $\langle x_n \rangle$ converge a $x$, escribimos $x_n \to x$ o $\lim x_n = x$. 

 **EJEMPLOS**



### Sucesiones y continuidad

Las funciones continuas y las sucesiones convergentes se *llevan bien.* Sea $f: X \rightarrow Y$ una función de un espacio métrico $X$ en un espacio métrico $Y$. Suponga que $f $ es continua en $p$. Sea $\langle x_n \rangle$ una sucesión en $X$ que converge a $p$ y sea $\epsilon > 0$. Como $f$ es contninua en $p$, existe un $\delta > 0$ tal que $\sigma(f(x) , f(p)) < \epsilon$ si $\rho(x, p) < \delta$. Como $x_n \to p$, existe $N$ en $\mathbb{N}$ tal que $\rho(x_n, p) < \delta$ si $n \geq N$. Luego, $\sigma(f(x_n), f(p)) < \epsilon$ si $n \geq N$. Esto implica que  $f(x_n) \to f(p)$. 

Lo anterior puede resumirse como "*las funciones continuas preservan la convergencia*". El converso también es cierto. Suponga que $f$ es discontinua en $p$. Entonces existe $\epsilon > 0$ tal que para toda $n$ en $\mathbb{N}$, existe $x_n$ tal que $\rho(p, x_n) < \frac{1}{n}$ y  $\sigma(f(x), f(p) ) \geq \epsilon$. Se sigue que $x_n \to p$ pero $f(x_n)$ no converge a $f(p)$. Por contraposición se obtiene lo deseado.



### Sucesiones de Cauchy

Una sucesión $\langle x_n \rangle$ decimos que es **sucesión de Cauchy** si dado $\epsilon > 0$ existe $N$ en $\mathbb{N}$ tal que $\rho(x_n, x_m) < \epsilon$ si $n, n \geq N$. Las sucesiones de Cauchy se *ven* como en la figura de abajo. Esta gráfica pudiera inducir la idea de que toda sucesión de Cauchy converge. A fin de cuentas, la distancia entre los términos de la sucesión se hace cada vez más pequeña. Sin embargo, existen espacios métricos con **sucesiones de Cauchy que no convergen**. 



  ![cauchy](https://upload.wikimedia.org/wikipedia/commons/6/62/Cauchy_sequence_illustration.svg)



Consideremos el espacio métrico $(\mathbb{Q}, \rho)$, donde $\rho$ es la métrica euclidiana. Para toda $n  $ en $ \mathbb{N}$, sea $x_n$ un racional tal que $2 - \frac{1}{n} < (x_n)^2 < 2$.  De esta desigualdad se sigue que, para $n, m$ en $\mathbb{N}$,
$$
-\frac{1}{n} < (x_n + x_m)(x_n - x_m) < \frac{1}{m}.
$$
Así que, si $n, m \to \infty$, entonces $(x_n + x_m)(x_n - x_m) \to 0$. Ahora bien, también se tiene que $x_k > 1$ para toda $k $ en $\mathbb{N}$, entonces $x_n + x_m > 1$. Esto implica que $(x_n - x_m) \to 0$, si $n, m \to \infty$. Por tanto $\langle x_n \rangle$ es una sucesión de Cauchy. 

Si $\langle x_n \rangle$  converge a $x$ en $\mathbb{Q}$, entonces $\langle (x_n)^2 \rangle$ converge a $x^2$. A su vez, por definición $\langle(x_n)^2\rangle$ converge a $2$, entonces se satisface que $x^2 = 2$. Pero esta ecuación no tiene soluciones en $\mathbb{Q}$. Por tanto $\langle x_n \rangle$ no converge. Con este ejemplo podemos constatar que $\mathbb{Q}$ tiene *agujeros*. 

Por otro lado, la desigualdad del tríangulo implica que toda sucesión convergente es sucesión de Cauchy. Sea $x_n \to x$ y sea $\epsilon > 0$. Entonces existe $N$ en $\mathbb{N}$, tal que $\rho(x_n, x) < \epsilon/2$. Luego, si $n, m \geq N$, se tiene que 
$$
\rho(x_n, x_n) \leq \rho(x_n, x) + \rho(x, x_m) < \epsilon.
$$
Cabe preguntarse si la condición de Cauchy (esto es, ser suceción de Cauchy) se preserva bajo  funciones continuas.  Sea $f: (0, 1] \rightarrow \mathbb{R}$ definida como $f(x) = \frac{1}{x}$ para toda $x \in (0, 1]$. Esta función es continua en $(0, 1]$. Consideremos la sucesión $\langle \frac{1}{n} \rangle$ en $(0, 1]$. Claramente esta es una sucesión de Cauchy. Sin embargo $\langle f(\frac{1}{n}) \rangle = \langle n \rangle $ no es sucesión de Cauchy en $\mathbb{R}$. 

El anterior ejemplo muestra que la condición de Cauchy no se preserva bajo funciones continuas. No obstante, podemos encontrar condiciones con las que esto si se cumple.  Sea $f: X \rightarrow Y$ una función **uniformemente continua** en un espacio métrico $X$ en un espacio métrico $Y$. Sea $\langle x_n \rangle$ una sucesión de Cauchy y sea $\epsilon > 0$. Como $f$ es uniformemente continua, existe un $\delta > 0$ tal que $ \sigma(f(x), f(y)) < \epsilon$ si $\rho(x, y) < \delta$. Como $\langle x_n \rangle$ es sucesión de Cauchy, existe $N $ en $\mathbb{N}$ tal que $\rho(x_n, x_m) < \delta$ si $m, n \geq N$. Se sigue que $\sigma(f(x_n), f(x_m)) < \epsilon$ si $n, m \geq N$. Por tanto $\langle f(x_n) \rangle$ es de Cauchy en  $Y$.



### Completitud

El ejemplo anterior nos hace ver que los espacio métricos cuyas sucesiones de Cauchy convergen son especiales. Cuando esto ocurre diremos que el espacio métrico en cuestión es **completo.** Por ejemplo, en cursos básicos de análisis se demuestra que los reales son un espacio métrico completo. 

Si tenemos un espacio métrico incompleto, cabe preguntarse ¿existe alguna forma de *completarlo*? El siguiente teorema contesta esta pregunta.

**Teorema.** Si $(X, \rho)$ es un espacio métrico incompleto, entonces es posible encontrar un espacio métrico completo $X^\ast$ en el cual $X$ es sumergido isométricamente como conjunto denso. Si $X$ está contenido en un espacio métrico completo $Y$, entonces $X^\ast$ es isométrico con la cerradura de $X$ en $Y$. 

Empezaremos demostrando los siguientes lemas. 

**Lema 1.** Si $\langle x_n \rangle$ y $\langle y_n \rangle$ son sucesiones de Cauchy en un espacio métrico $X$, entonces $\rho(x_n, y_n)$ converge. 

*Demostración.* Por la desigualdad del triangulo se tiene que 


$$
\rho(x_n, y_n) \leq \rho(x_n, x_m) + \rho(x_m, y_n) \leq \rho(x_n, x_m) + \rho(x_m, y_m) + \rho(y_m, y_n).
$$


Entonces $\rho(x_n, y_n) - \rho(x_m, y_m) \leq \rho(x_n, x_m) + \rho(y_n, y_m)$. De manera análoga se llega a que $\rho(x_m, y_m) - \rho(x_n, y_n) \leq \rho(x_n, x_m) + \rho(y_n, y_m)$. Por tanto $\lvert \rho(x_n, y_n) - \rho(x_m, y_m) \lvert \leq \rho(x_n, x_m) + \rho(y_n, y_m)$ Por hipótesis, $\rho(x_n, x_m) \to 0$  y $\rho(y_n, y_m) \to 0$, cuando $n, m \to \infty$. Entonces $\lvert \rho(x_n, y_n) - \rho(x_m, y_m)\lvert \to 0$ cuando $n, m \to \infty$. Entonces la sucesión $\rho(x_n, y_n)$ es sucesión de Cauchy en $\mathbb{R}$ y por tanto converge. $\blacksquare$

**Lema 2.** El conjunto de todas las sucesiones de Cauchy de un espacio métrico $X$ forma un espacio pseudométrico, si $\rho^\ast(\langle x_n \rangle, \langle y_n \rangle) = \lim \rho(x_n, y_n)$.

*Demostración.* Sean $\langle x_n \rangle, \langle y_n \rangle$ y $\langle z_n \rangle$ sucesiones de Cauchy en $X$. Demostraremos que $\rho^\ast$ es una pseudométrica. 

Se cumple que $\rho^\ast(\langle x_n \rangle, \langle x_n \rangle ) = \lim \rho(x_n, x_n) = 0$ y $\rho^\ast(\langle x_n \rangle, \langle y_n \rangle) = \lim \rho(x_n, y_n) = \lim \rho(y_n, x_n) = \rho^\ast(\langle y_n \rangle, \langle x_n \rangle) $, ya que $\rho$ es una métrica en $X$.  Además, 


$$
\begin{eqnarray}
\rho^\ast(\langle x_n \rangle, \langle y_n \rangle) &=& \lim \rho(x_n, y_n) \\
&\leq& \lim [\rho(x_n, z_n) + \rho(z_n, y_n)]\\
&=& \lim \rho(x_n, z_n) + \lim \rho(z_n, y_n)\\
&=& \rho^\ast(\langle x_n\rangle, \langle z_n \rangle) + \rho^\ast(\langle z_n \rangle, \langle y_n\rangle).
\end{eqnarray}
$$


Decimos que $\rho^\ast$ es una pseudométrica, ya que las sucesiones $\langle x_n \rangle $ y $\langle x_{n+k}\rangle$, $k$ en $\mathbb{N}$ son distintas pero satisfacen  $\rho^\ast(\langle x_n \rangle, \langle x_{n+k}\rangle) = 0$. $\blacksquare$

**Lema 3.** La relación $\langle x_n \rangle \sim \langle y_n \rangle$ si y solo si $\rho^\ast(\langle x_n \rangle , \langle y_n \rangle) = 0$ es una relación de equivalencia en el conjunto de todas las sucesiones de Cauchy de $X$. El conjunto $X^\ast$ de todas las clases de equivalencia generadas forma un espacio métrico. Además, $X$ está isométricamente sumergido en $X^\ast$ como conjunto denso.

*Demostración.* Por el Lema 2, $\sim$ es reflexiva y simétrica.  Sean $\langle x_n \rangle, \langle y_n \rangle$ y $\langle z_n \rangle$ sucesiones de Cauchy en $X$ tales que $\langle x_n \rangle \sim \langle y_n \rangle$ y $\langle y_n \rangle \sim \langle z_n \rangle$. Por la desigualdad del tríangulo se sigue que $0 \leq \rho^\ast(\langle x_n \rangle, \langle z_n \rangle) \leq \rho^\ast(\langle x_n \rangle, \langle y_n \rangle)+ \rho^\ast(\langle y_n \rangle, \langle z_n \rangle) = 0. $ Por tanto $\rho^\ast(\langle x_n \rangle, \langle z_n \rangle) = 0$. Se sigue que $\sim$ es una relación de equivalencia en el conjunto de todas las sucesiones de Cauchy en $X$.

Llamemos $X^\ast$ al conjunto de todas las clases de equivalencia generadas por $\sim$. Sean $x^\ast , y^\ast$ en $X^\ast$. Sean $\langle x_n \rangle $, $\langle x_n^\prime \rangle$  y $\langle y_n \rangle $, $\langle y_n^\prime \rangle$ dos representantes de las clases $x^\ast$ y $y^\ast$ respectivamente. Entonces 


$$
\begin{eqnarray}
\rho^\ast(\langle x_n \rangle, \langle y_n \rangle) &\leq& \rho^\ast(\langle x_n \rangle, \langle x_n^\prime \rangle) + \rho^\ast(\langle x_n^\prime \rangle, \langle y_n \rangle)\\
&=& \rho^\ast(\langle x_n^\prime \rangle, \langle y_n \rangle)\\
&\leq& \rho^\ast(\langle x_n^\prime \rangle, \langle y_n^\prime \rangle) + \rho^\ast(\langle y_n^\prime \rangle, \langle y_n \rangle)\\
&=& \rho^\ast(\langle x_n^\prime \rangle, \langle y_n^\prime \rangle).
\end{eqnarray}
$$


Por tanto $\rho^\ast(\langle x_n \rangle, \langle y_n \rangle) \leq \rho^\ast(\langle x_n^\prime \rangle, \langle y^\prime_n \rangle)$. De manera similar se deduce que $\rho^\ast(\langle x_n^\prime \rangle, \langle y_n^\prime \rangle) \leq \rho^\ast(\langle x_n \rangle, \langle y_n \rangle)$.  Con lo anterior, hemos demostrado que el valor de $\rho^\ast$ es independiente de los representantes de las clases de equivalencia involucradas. En resumen, la función $\sigma(x^\ast, y^\ast) = \rho^\ast(\langle x_n \rangle, \langle y_n \rangle)$, donde $\langle x_n \rangle $ y $ \langle y_n \rangle$ son representantes de las clases de equivalencia $x^\ast$ y $y^\ast$ respectivamente, está bien definida. Y por todo lo anterior, se deduce que $(X^\ast, \sigma)$ es un espacio métrico. 

Finalmente, identifiquemos a todo elemento $x $ en $ X$ con la sucesión de Cauchy $\langle x  \rangle$. Sea $\phi: X \rightarrow X^\ast$ dado por $\phi(x) = x^\ast$, si $\langle x \rangle \in x^\ast$. Observe que si $x \neq y$ , claramente $\langle x  \rangle \neq \langle y  \rangle $. Más aún, $\rho^\ast(\langle x  \rangle, \langle y  \rangle ) = \lim \rho(x , y ) = \rho(x, y) > 0$. De manera que $\langle x_n \rangle $ y $\langle y_n \rangle$ están en distintas clases de equivalencia. Hemos mostrado que el mapeo $\phi$ es inyectivo. Además, este mapeo es una isométrico, ya que $\rho(x, y) = \lim \rho(x, y)  = \rho^\ast(\langle x \rangle, \langle y \rangle) = \sigma(x^\ast, y^\ast) = \sigma(\phi(x), \phi(y))$. 

Por último, para ver que $\phi(X)$ es denso en $X^\ast$, sea $x^\ast $ en $X^\ast$ y sea $\epsilon > 0$. Sea $\langle x_n \rangle $ una sucesión de Cauchy en $X$ tal que $\langle x_n \rangle \in x^\ast$. Entonces existe un $N > 0$ tal que $\rho(x_m, x_N) < \epsilon/2$ si $m \geq N$. Consideremos la sucesión $\langle x_N \rangle$ es decir, la sucesión en la que todos sus términos son $x_N$ y sea  $y^\ast \in X^\ast$ la  clase de equivalencia tal que $\langle x_N \rangle \in y^\ast$. Más aún, esta clase de equivalencia es un elemento de $\phi(X)$  y satisface que $\sigma(x^\ast, y^\ast) = \rho^\ast(\langle x_n \rangle, \langle x_N \rangle) = \lim \rho(x_n, x_N) < \epsilon/2 < \epsilon$. Por tanto, $\phi(X)$ es denso en $X^\ast$. $\blacksquare$

**Lema 4**. El espacio métrico $(X^\ast, \sigma)$ es completo. 

*Demostración.* Sea $\langle x_k^\ast \rangle$ una sucesión de Cauchy en $X^\ast$. Sea $\langle x_{k,  n} \rangle$ una sucesión en $X$ tal que $\langle x_{k, n} \rangle \in x_k^\ast$, para toda $k \in \mathbb{N}$. Para toda $k$, $\langle x_{k, n} \rangle$ es sucesión de Cauchy en $X$. Entonces, existe $N_k \in \mathbb{N}$ tal que $\rho(x_{k, N_k}, x_{k, n}) < 2^{-k}$ si $n \geq N_k$. Consideremos la sucesión $\langle x_{k} \rangle $ con $x_k = x_{k, N_k}$ para toda $k \in \mathbb{N}$. Observe que

$$
\begin{eqnarray}
\rho(x_k, x_m) &=& \rho(x_{k, N_k}, x_{m, N_m}) \\
&\leq& \rho(x_{k, N_k}, x_{k, j}) + \rho(x_{k, j}, x_{m, N_m})\\
&\leq& \rho(x_{k, N_k}, x_{k, j}) + \rho(x_{k, j}, x_{m, j}) + \rho(x_{m,j}, x_{m, N_m})\\
&<& 2^{-k} + \rho(x_{k, j}, x_{m, j}) + 2^{-m},
\end{eqnarray}
$$


si $j \geq \max\{N_k, N_m\}$. Y como $\rho^\ast(x_k^\ast, x_m^\ast) \to 0$ cuando $k, m \to \infty$, se tiene que $\rho(x_{k, j}, x_{m, j}) \to 0$ cuando $k, m \to \infty$. Hemos demostrado que la sucesión $\langle x_k \rangle $ es sucesión de Cauchy. 

Sea $x^\ast $ la clase de equivalencia de $\langle x_k \rangle$. Tenemos entonces que 


$$
\begin{eqnarray}
\rho^\ast(x_k^\ast, x^\ast) &=& \lim_{n\to\infty} \rho(x_{k, n}, x_n)\\
&=& \lim_{n \to \infty} \rho(x_{k, n}, x_{n, N_n}) \\
&\leq& \lim_{n \to \infty} (\rho(x_{k, n}, x_{k, N_k}) + \rho(x_{k, N_k}, x_{n, N_n}))\\
& < & 2^{-k} + \rho(x_{k, N_k}, x_{n, N_n})).
\end{eqnarray}
$$


Bajo el mismo argumento anterior, $\rho(x_{k, N_k}, x_{n, N_n})) \to 0$ , cuando $n, k \to \infty$. Por tanto $x_k^\ast \to x^\ast$ y  la demostración está completa. :metal:

[  ]: Falta demostrar cerradura. 