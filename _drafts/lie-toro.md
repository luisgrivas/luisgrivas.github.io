---
layout: post
title "Lie"
date: 2021-10-21 17:21:00
categories: post
tags: grupos grupos-de-lie toro topología
---

Un resultado elemental de la teoría de grupos de Lie establece que todo grupo de Lie abeliano y conexo es igual al producto de un toro y el espacio euclídeo $\mathbb R^n$. Lo interesante de este resultado de clasificación es que su demostración utiliza herramientas sencillas.


Un **grupo de Lie** es un conjunto $G$ con las siguientes dos estructuras: (1) $G$ es una variedad suave; (2) $G$ es un grupo. Además, las operaciones de multiplicación e inversión son suaves:

$$ (g, h) \mapsto g \cdot h, $$   

$$ g \mapsto g^{-1}.$$

Como $G$ es una variedad suave, podemos asociar a $G$ el haz tangente $TG$, que consiste en la unión disjunta de espacios tangentes $T_p G$. Si $e$ es el elemento identidad de $G$, entonces al espacio tangente $T_eG$ se le conoce como álgebra de Lie de $G$. Este espacio es particularmente importante para los grupos de Lie. Un primer resultado que resalta su importancia es el siguiente. 

**Teorema**. Si $G$ es un grupo de Lie y $T_eG$ es el espacio tangente de $G$ en la identidad $e$, entonces 

$$ TG  \cong G \times T_e G.$$

Es decir, el haz tangente es trivial. Para ver esto, sea $g$ en $G$ y definamos el mapeo **de traslaciones por la izquierda**

$$ l_g: G \rightarrow G \ \ \ x \mapsto g \cdot x.$$

Un argumento directo muestra que $l_g$ es un difeomorfismo para toda $g \in G$  (es clave la existencia de inversos en $G$). A partir de estos mapeos, podemos definir un homomorfismo de haces $\varphi: G \times T_e G \rightarrow TG$ de la siguiente manera: 

$$ (g, X) \mapsto d_e l_g(X).$$

De ahora en adelante, denotemos por $LG$ a $T_eG$. 

Un **campo vectorial** en una variedad es una sección del haz $TM \rightarrow M$. Intuitivamente, un campo vectorial asigna, a cada punto $p$ en $M$, un vector tangente a $M$ en $p$. Decimos que un campo vectorial $S: M \rightarrow TM$ es invariante por la izquierda, si 

$$ S(l_g(p)) = d_p l_g(S(p)), \ \ \ \text{ para todo } p,g \in G. $$ 

En el caso de los grupos de Lie, su álgebra de Lie es *igual* al conjunto de campos vectoriales invariantes por la izquierda. Para ver esto, sea $X \in LG$, un vector tangente a $G$ en la identidad. Entonces, podemos definir un campo vectorial en $G$ a partir de $X$ de la siguiente manera:

$$ g \mapsto d_e l_g(X). $$

No es difícil ver que esta relación establece un isomorfismo entre los espacios vectoriales $LG$ y los campos vectoriales invariantes por la izquierda. Intuitivamente podemos pensar en lo siguiente. Cada vector en $LG$ podemos trasladarlo por toda la variedad $G$, sin alterar su "magnitud" y "dirección", formando así un espacio vectorial en $M$. Este espacio es invariante por la izquierda, por su misma construcción. Por ejemplo, si una particula que sigue una trayectoria descrita por $d(t) = (cos(t), sin(t))$, entonces su rapidez $\lvert d'(t) \rvert = 1$. Esta partícula induce un campo vectorial invariante por la izquierda:.... 

Este resultado aparentemente insípido ya nos permite establecer que las esferas $S^n$ cuando $n$ es par no son grupos de Lie. Es [teorema de la bola peluda]({% url_post %}) establece que todo campo vectorial en $S^n$ se anula en un punto de $S^n$ cuando $n$ es par. Por tanto, estas esferas no tienen campos vectoriales invariantes por la izquierda. 


Existe otra forma de describir al espacio $LG$. Una **curva integral**  Un **homomorfismo de un parámetro** de un grupo de Lie $G$, es un homomorfismo de grupos de Lie

$$ \alpha: \mathbb R \rightarrow G. $$

La correspondencia $\alpha \mapsto \alpha^\prime(0)$, establece una biyección  




**Teorema.** Un grupo de Lie abeliano y conexo es igual al producto de un toro y espacio vectorial: $G \cong T^k \times \mathbb R^m.$

