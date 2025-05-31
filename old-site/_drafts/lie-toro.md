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

El ejemplo que discutiremos en estas notas es el siguiente. Sea $S^1 = \{z \in \mathbb C: \lvert z \rvert = 1\}$. Las proyecciones estereográficas establecen un atlas diferenciable en $S^1$, por lo que $S^1$ es una $1-$variedad suave. Dado que en $\mathbb C$, $\lvert z_1 \rvert \cdot \lvert z_2 \rvert = \lvert z_1 \cdot z_2$, se observa que $S^1$ es un subgrupo multiplicativo de los complejos. Además, es claro que las operaciones de multiplicación e inversión son suaves. Por tanto, $S^1$ es un grupo de Lie. 

Como en particular, un grupo de Lie $G$ es una variedad suave, podemos asociar a $G$ el haz tangente $TG$,que consiste en la unión disjunta de espacios tangentes $T_p G$. Si $e$ es el elemento identidad de $G$, entonces al espacio tangente $T_eG$ se le conoce como álgebra de Lie de $G$. Este espacio es particularmente importante para los grupos de Lie. Un primer resultado que resalta su importancia es el siguiente. 

**Teorema**. Si $G$ es un grupo de Lie y $T_eG$ es el espacio tangente de $G$ en la identidad $e$, entonces 

$$ TG  \cong G \times T_e G.$$

Es decir, el haz tangente es trivial. Para ver esto, sea $g$ en $G$ y definamos el mapeo **de traslaciones por la izquierda**

$$ l_g: G \rightarrow G \ \ \ x \mapsto g \cdot x.$$

Un argumento directo muestra que $l_g$ es un difeomorfismo para toda $g \in G$  (es clave la existencia de inversos en $G$). A partir de estos mapeos, podemos definir un homomorfismo de haces $\varphi: G \times T_e G \rightarrow TG$ de la siguiente manera: 

$$ (g, X) \mapsto d_e l_g(X).$$

De ahora en adelante, denotemos por $LG$ a $T_eG$. 

Consideremos de nuevo el grupo de Lie $S^1$. Geométricamemte, su álgebra de Lie $LS^1$ es isomorfa a $R^1$: esta consiste en todos los vectores tangentes a $S^1$ en $1$, es decir, es una recta. De aquí, su haz tangente es un cilindro $S^1 \times \mathbb R$. 

Un **campo vectorial** en una variedad es una sección del haz $TM \rightarrow M$. Intuitivamente, un campo vectorial asigna, a cada punto $p$ en $M$, un vector tangente a $M$ en $p$. Decimos que un campo vectorial $S: M \rightarrow TM$ es invariante por la izquierda, si 

$$ S(l_g(p)) = d_p l_g(S(p)), \ \ \ \text{ para todo } p,g \in G. $$ 

En el caso de los grupos de Lie, su álgebra de Lie es *igual* al conjunto de campos vectoriales invariantes por la izquierda. Para ver esto, sea $X \in LG$, un vector tangente a $G$ en la identidad. Entonces, podemos definir un campo vectorial en $G$ a partir de $X$ de la siguiente manera:

$$ g \mapsto d_e l_g(X). $$

No es difícil ver que esta relación establece un isomorfismo entre los espacios vectoriales $LG$ y los campos vectoriales invariantes por la izquierda. Intuitivamente podemos pensar en lo siguiente. Cada vector en $LG$ podemos trasladarlo por toda la variedad $G$, sin alterar su "magnitud" y "dirección", formando así un espacio vectorial en $M$. Este espacio es invariante por la izquierda, por su misma construcción.

Este resultado aparentemente insípido ya nos permite establecer que las esferas $S^n$ cuando $n$ es par no son grupos de Lie. Es [teorema de la bola peluda]({% url_post %}) establece que todo campo vectorial en $S^n$ se anula en un punto de $S^n$ cuando $n$ es par. Por tanto, estas esferas no tienen campos vectoriales invariantes por la izquierda [^1].


Existe otra forma de describir al espacio $LG$. Una **curva integral** $\alpha: (-\epsilon, \epsilon) \rightarrow M$ de un campo vectorial $S: M \rightarrow TM$ es una curva suave tal que $\alpha^\prime(t) = S(\alpha(t))$ para toda $t \in (-\epsilon, \epsilon)$. Un resultado conocido establece que, dado un campo vectorial, existe una única curva integral que pasa por un punto $p$. Para el caso de grupos de Lie, si $S \in LG$ es un campo vectorial invariante por la izquierda (aquí usamos la anterior descripción de $LG$), entonces $\alpha^S$ denota la curva integral del campo $S$ tal que $\alpha^\prime(0) = e$.  

 Un **grupo de un parámetro** de un grupo de Lie $G$, es un homomorfismo de grupos de Lie

$$ \alpha: \mathbb R \rightarrow G. $$

La correspondencia $\alpha \mapsto \alpha^\prime(0)$, establece una biyección entre grupos de un parámetro y el álgebra de Lie de $G$.

¿Qué significa lo anterior para $S^1$? Observe que el mapeo exponencial $\omega: \mathbb R \rightarrow S^1$ definido como $t \mapsto e^{it}$ es un homomorfismo de un parámetro. Vea que $\omega^\prime(0) = i$ y este es tangente a $S^1$ en $1$. Así pues, $\omega^\prime(0) \in LS^1$. Podemos utilizar este mapeo como plantilla para definir otros grupos de un parámetro. Para toda $\lambda \in \mathbb R \cong LG$, definamos definamos  $\alpha_\lambda: \mathbb R \rightarrow S^1$ como $\alpha_lambda = \omega(\lambda t)$. Es claro que este es un grupo de un parámetro para toda $\lamdba \in \mathbb R.$


La construcción anterior que acabamos de realizar sirve como base para definir el **mapeo exponencial** de un grupo de Lie arbitrario. Este lo definimos como 

$$ \exp: LG \rightarrow G \ \ \ \ X \mapsto \alpha^X(1),$$

donde $\alpha^X(1)$ es un grupo de un parámetro con $\alpha^{X \ \prime} (0) = X$. Este mapeo nos permite estudiar $G$ mediante su álgebra de Lie. 

**Teorema**. El mapeo exponencial es suave y su diferencial en el origen es la identidad. 

*Demostración*. Consideremos el mapeo 

$$\mathbb R \times G \times LG \rightarrow G \times LG \ \ \ (\lambda, g, X) \mapsto (g \cdot \alpha^{X}(\lambda), X). $$

Este mapeo es el flujo en $G \times LG$ correspondiente al campo vectorial $(g, X) \mapsto (X(g), 0)$ y por tanto es un mapeo diferenciable. Por tanto, la restricción $1 \times \{e\} \times LG \rightarrow G$, $(1, e, X) \mapsto  \alpha^X (1)$ es diferenciable.  

Sean $\lambda \in \mathbb R$ y $X \in LG$. Vea que los grupos de un parámetro $t \mapsto \alpha^{X}(\lambda t)$ y $ t \mapsto \alpha^{\lambda X}(t)$ correspoden al mismo vector $\lambda X$, por lo que son iguales. Entonces

$$ \exp(\lambda X) = \alpha^{\lambda X}(1) = \alpha^{X}(\lambda).$$

Luego, $\frac{ \partial \exp(\lambda X) }{\partial \lambda}$ en $\lambda = 0$, es igual  $X$. Por tanto, $d_0 \exp = Id_{LG}.$ :metal:

Si $f: G \rightarrow H$ es un homomorfismo de grupos de Lie, entonces este induce un mapeo conmutativo:






Con todo lo anterior, estamos listos para demostrar el siguiente teorema.

**Teorema.** Si $G$ es grupo de Lie abeliano y conexo, entonces $G \cong T^k \times \mathbb R^m.$ Aquí, $T^k \cong \mathbb R^n / \mathbb Z^n$.

*Demostración*. Como la imagen de $\exp$ contiene un conjunto de generadores de $G$, $\exp$ es un homomorfismo sobreyectivo. Observe que $K = \ker \exp$ es un subgrupo discreto de $LG$, ya que $\exp$ es una biyección en una vecindad de $0\in LG$. Entonces $K$ tiene una base $\{g_1, \ldots, g_k \}$. Podemos completar la base con vectores $g_{k+1}, \ldots, g_n$ en $LG$ tal es que estos formen una base para $LG$. Esta base determina un isomorfismo entre $LG$ y $\mathbb R^n$ tales que 

$$K \cong \mathbb Z^n \times \{0\} $$

