---
layout: post
title: "Teorema de Baire en espacios métricos"
date: 2020-11-29 22:53:00
categories: posts
tags: análisis-real
---



**Definición.** Decimos que un conjunto $E$ en un espacio métrico $X$ es **denso en ninguna parte**, si $\bar{E}^c$ es denso en $X$.

Un ejemplo sencillo de este tipo de conjuntos son los enteros $\mathbb{Z}$. También [el conjunto de Cantor es denso en ninguna parte](https://luisgrivas.github.io/blog/post/2020/11/06/conjunto-cantor.html). 



**Teorema.** Sea $X$ un espacio métrico completo y $\\{O_n\\}$ una colección numerable de subconjuntos abiertos densos en $X$. Entonces $\bigcap_n O_n$ es no vacía. 

*Demostración.* Sea $x_1$ un elemento de $O_1$ y $B_1$ una bola centrada en $x_1$ con radio $r_1$ contenida en $O_1$.Como $O_2$ es denso, existe un $x_2 $ en $O_2 \cap B_1$. Como $O_2$ es abierto, existe una bola $B_2$ centrada en $x_2$ contenida en $O_2$ y radio $r_2$ menor que $\frac{r_1}{2}$ y menor que $r_1 - \rho(x_1, x_2)$. Luego $\overline{B_2} \subset B_1$. Inductivamente, obtenemos una sucesión $\langle B_n \rangle$ de bolas tales que $\overline{B_{n}} \subset B_{n-1} $ y $B_n \subset O_n$. Además, la sucesión de radios $\langle r_n \rangle$  de las bolas convergen a cero. Sea $\langle x_n \rangle$ la sucesión de centros de estas bolas. Observe que si $n, m \geq N$ con $N$ en $\mathbb{N}$, entonces $x_n, x_m$ son elementos de $B_N$. Luego, $\rho(x_n, x_m) \leq \rho(x_n, x_N) + \rho(x_N, x_m) = 2 r_N$. Como $r_n \to 0$, entonces $\rho(x_n, x_m) \to 0$. Por tanto, $\langle x_n \rangle $ es sucesión de Cauchy. Como $X$ es completo, $x_n \to x$ para algún $x \in X$.  Como $x_n \in B_{N+1}$ para toda $n > N$, se tiene que $x \in \overline{B_{N+1}} \subset B_N \subset O_N$. Por tanto $x \in \bigcap_n O_n$. $\blacksquare$



**Corolario (Teorema de Categoría de Baire).** Un espacio métrico completo no es la unión numerable de conjuntos densos en ninguna parte. 

*Demostración:* Sea $X$ un espacio métrico completo. Suponga que $X = \bigcup_n O_n$ donde $O_n$ son densos en ninguna parte. Entonces $\bar{O}_n^c$ es un conjunto abierto  y denso para toda $n\in \mathbb{N}$. Pero $\emptyset = \bigcap \bar{O}_n^c$, lo cual contradice al Teorema anterior. $\blacksquare$

Un conjunto $E$ se dice que es de **primera categoría** si es la unión numerable de conjuntos densos en ninguna parte. El corolario anterior puede reescribirse  como: *ningún espacio métrico completo es de primera categoría.* Un conjunto que no es de primera categoría se dice que es de **segunda categoría.**

Por ejemplo, $\mathbb{Q}$ es de primera categoría en $\mathbb{R}$. Sea $(x_n)$ una enumeración de $\mathbb{Q}$. Entonces $\mathbb{Q} = \bigcup_n\\{x_n\\}$ y también $\overline{\\{x_n\\}}^c = (-\infty, x_n]\cup[x_n, \infty)$ es denso para toda $n$ en $\mathbb{N}$. Esto tiene como consecuencia algo todavía más interesante: no existe una función real continua $\mathbb{Q}$ y discontinua en $\mathbb{R}\setminus \mathbb{Q}$. Si existiera, entonces $\mathbb{Q}$ sería un conjunto $\mathcal{G}_\delta$, es decir,  $\mathbb{Q} = \bigcap_n O_n$ con $O_n$ abierto en $\mathbb{R}$. Como $\mathbb{Q} \subset O_n$ y $\mathbb{Q}$ es denso en $\mathbb{R}$, entonces $O_n$ es denso en $\mathbb{R}$. Luego, $\mathbb{R}\setminus \mathbb{Q} = \bigcup_n O_n^c$. Observe que $\overline{O_n^c} = O_n^c$ ya que este es cerrado y por tanto $\overline{O_n^c}^c = O_n$ es denso para toda $n\in \mathbb{N}$. Se sigue que $\\{O_n^c\\}$ es una colección numerable de conjuntos densos en ninguna parte. Esto implica que $\mathbb{R}\setminus \mathbb{Q}$ es de primera categoría. Como $\mathbb{Q}$ es de primera categoría, se sigue que $\mathbb{R}$ también lo es. Pero esto es imposible, ya que que $\mathbb{R}$ es un espacio métrico completo. Para una demostración más elemental véase el siguiente artículo sobre el [teorema de Volterra](https://luisgrivas.github.io/blog/posts/2020/11/17/volterra.html).



### Aplicaciones

**Proposición.**  Un conjunto cerrado $F$ es denso en ninguna parte si y solo si no contiene a ningún conjunto abierto.

*Demostración.* $(\Rightarrow)$ Si $F$ es cerrado y denso en ninguna parte, entonces $\overline{F}^c = F^c$ es un abierto denso en $X$. Esto implica que si $A$ es abierto, entonces $F^c \cap A \neq \emptyset$. Por tanto, ningún abierto está contenido en $F$.

$(\Leftarrow)$ Suponga que $F$ no contiene a ningún abierto. Sea $A$ un abierto en $X$. Entonces $A \cap F^c \neq \emptyset $. Como $F$ es cerrado, $\overline{F}^c = F^c$. Luego $F^c$ es denso en $X$. Por tanto $F$ es denso en ninguna parte. $\blacksquare$

En otras palabras, *un conjunto cerrado es denso en ninguna parte si y solo si su interior es vacío.*

**Teorema.** Sea $\mathcal{F}$ una familia de funciones de valores reales continuas en un espacio métrico completo $X$. Suponga que para toda $x \in X$ existe un número real $M_x$ tal que $\lvert f(x) \lvert \leq M_x$ para toda $f \in \mathcal{F}$. Entonces existe un abierto no vacío $O \subset X$ y una constante $M$ tal que $\lvert f(x) \lvert \leq M$ para toda $f \in \mathcal{F}$ y para toda $x \in O$.

*Demostración.* Para toda $f \in \mathcal{F}$ y $n \in \mathbb{N}$ sea $E_{n, f} = \{x \in X: \lvert f(x) \lvert < n \}$. Como $f$ es continua, $E_{n, f}$ es cerrado para toda $f$ y para toda $n$. Sea $E_n = \bigcap_{f \in \mathcal{F}} E_{n, f}$. Es claro que $E_n$ es cerrado para toda $n$. Además, si $x \in X$, existe $M_x$ tal que $\lvert f(x) \lvert < M_x$. Si $n < M_x$, entonces $x \in E_n$. Luego $X = \bigcup_n E_n$. Como $X$ es completo, existe $k$ en $\mathbb{N}$ tal que $E_k$ no es denso en ninguna parte.  Como $E_k$ es cerrado, existe un abierto $O$ contenido en $E_k$. Se comple que si $x \in O$, entonces $\lvert f(x) \lvert < k$ para toda $f \in \mathcal{F}$.

 

**Proposición** Existe un conjunto en $[0, 1]$ que es cerrado y denso en niguna parte cuya medida de Lebsgue es $1 - \frac{1}{n}$. 

*Demostración.* Sea $C_\frac{1}{n}$  [el conjunto de Cantor generalizado](https://luisgrivas.github.io/blog/post/2020/11/06/conjunto-cantor.html) con $\alpha = \frac{1}{n}$ . Este conjunto es cerrado y es de medida $1 - \frac{1}{n}$.

Sea $A$ un abierto en $[0, 1]$ tal que $A \cap C_{\frac{1}{n}} \neq \emptyset. $ Entonces $A \cap P_{k , \frac{1}{n}} \neq \emptyset$ para toda $k \in \mathbb{N}$.  