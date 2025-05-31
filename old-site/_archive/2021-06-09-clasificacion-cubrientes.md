---
layout: post
title: "Clasificación de espacios cubrientes"
date: 2021-06-09 18:25:00
categories: posts
tags: topología-algebraica topología
---

Consideremos un espacio topológico $X$ y sea $E$ un espacio cubriente. Si $H = \pi_1(E, e)$ y $G = \pi_1(X, x)$ son los grupos fundamentales de $E$ y $X$ respectivamente, sabemos que el homomorfismo inducido por el mapeo cubriente $q_\ast: H \to G$ es inyectivo. Esto implica que $H$ es isomorfo a un subgrupo de $G$. Así pues, la siguiente pregunta surge de manera natural,

> ¿Existe una correspondencia entre los subgrupos del grupo fundamental de $X$ y espacios cubrientes de $X$?

En estas notas veremos que si $X$ es un espacio lo suficientemente *bonito*, esta correspondencia existe. Más aún, veremos cómo encontrar todos los espacios cubrientes (salvo isomorfismo) a partir del cubriente universal de $X$.

### Automorfismos cubrientes

Suponga que $q: E \to X$ es un mapeo cobriente. Un **automorfismo cubriente** de $q$ es un homeomorfismo $\phi: E \to E$ tal que $q \circ \phi = q$.

El conjunto de todos los automorfismos cubrientes lo denotamos por $Aut_q(E)$. Este conjunto forma un grupo bajo la composición llamado **el grupo cubriente**. 

El resultado principal de esta sección es que $Aut_q(E)$ se puede expresar en términos del grupo fundamental del espacio $X$.

**Definición.** Si $H$ es un subgrupo de $G$, el **normalizador** de $H$ en $G$, denotado por $N_G(H)$, es el conjunto de todos los $g\in G$ tales que $g H g^{-1} = H$.

Es directo ver que $N_G(H)$ es un subgrupo normal de $G$.

**Teorema.** Sean $q: E \to X$  un mapeo cubriente, $e \in E$ y $x = q(e)$. Sean $G = \pi_1(X, x)$ y $H = q_\ast \pi_1(E, e)$. Para cada clase $\gamma \in N_G(H)$, existe un único automorfismo cubriente $\phi_\gamma \in Aut_q(E)$ tal que $\phi_\gamma(e) = e \cdot \gamma$. El mapeo $ \gamma \mapsto \phi_\gamma$ es un homomorfismo sobreyectivo de grupos de $N_G(H)$ en $Aut_q(E)$ cuyo kernel es $H$.

*Demostración:*



Por el Primer Teorema de Isomorfismo tenemos que
$$
Aut_q(E) \simeq N_{\pi_1(X, x)}(q_\ast \pi_1(E, e)) / q_\ast \pi_1(E, e)
$$

###  Teorma de Clasificación

**Teorema.** Sea $X$ un espacio topológico que tiene un cubriente universal y sea $x_0 \in X$ un punto base. Existe una correspondencia uno a uno entre clases de isomorfas de cubrientes de $X$ y clases de conjugación de subgrupos de $\pi_1(X, x_0)$. Esta correspondencia asocia a cada cubriente $q: E \rightarrow X$ con la clase de conjugación del subgrupo inducido.