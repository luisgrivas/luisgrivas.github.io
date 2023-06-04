---
layout: post
title: "Topología cociente"
date: 2021-01-18 12:00:00
categories: posts
tags: topología
---

**Definición**. Sean $X$ y $Y$ espacios topológicos; sea $p: X \rightarrow Y$ un mapeo sobreyectivo. El mapeo $p$ es un **mapeo cociente** si  $U \subset Y$ es abierto si y solo si $p^{-1}(U)$ es abierto en $X$. 

Obsérvese que la definición anterior es más fuerte que continuidad. Otra forma de llamar a los mapeos cociente es **continuidad fuerte.**

Otra forma de describir un mapeo cociente es la siguiente: decimos que un subconjunto $C \subset X$ es **saturado** si $C$ contiene cada conjunto $p^{-1}(\{y\})$ que intersecta. Con esto, decimos que $p$ es un mapeo cociente si $p$ es continua y mapea conjuntos abiertos y saturados de $X$ en abiertos de $Y$.

**Definición.** Si $X$ es un espacio topológico y $A$ es un conjunto y si $p: X \rightarrow A$ es un mapeo sobreyectivo, entonces existe exactamente una topología $\tau$ en $A$ tal que $p$ es un mapeo cociente. A esta topología se le conoce como **topología cociente** inducida por $p$.

¿Cómo se construye esta topología? Definamos 
$$
\tau_p:= \{B \subset A: p^{-1}(B) \text{ es abierto en } X \}.
$$
Es fácil comprobar que $\tau_A$ satisface los axiomas de topología. 

**Definición.** Sea $X$ un espacio topológico, y sea $X^*$ una partición disjunta de $X$. Sea $p: X \rightarrow X^\ast$ el mapeo sobreyectivo que mapea cada punto de $X$ al elemento de $X^\ast$ que contiene a ese punto. En la topología cociente inducida por $p$, el espacio $X^\ast$ se le conoce como **espacio cociente** de $X$.

Dada una partición, sabemos que esta induce una relación de equivalencia en $X$ (el converso también es cierto). Entonecs podemos pensar en $X^\ast$ como el espacio resultante después de *identificar* puntos equivalentes en $X$. Al espacio cociente también se le llama **espacio de identificación** de $X$.

**Teorema.** Sea $p: X \rightarrow Y$ un mapeo cociente. Sea $A$ un subespacio de $X$ que es saturado respecto a $p$. Sea $q: A \rightarrow p(A)$ el mapeo obtenido cuando se restringe a $p$. Entonces

1. Si $A$ es abierto o cerrrado en $X$, entonces $q$ es un mapeo cociente.
2. Si $p$ es un mapeo abierto o cerrado, entonces $q$ es un mapeo cociente.



**Teorema.** Sean $X, Y$ espacios topológicos y sea $q: X \rightarrow Y$ un mapeo cociente. Para cualquier espacio $Z$, el mapeo $f: Y \rightarrow Z$ es continua si y solo si la composición $f \circ q$ es continua.



**Teorema (Passing to the Quotient).** Sea $p: X \rightarrow Y$ un mapeo cociente. Sea $Z$ un espacio y sea $g: X \rightarrow Z$ un mapeo que es constante en todo conjunto de la forma $p^{-1}(\{y\})$, para $y\in Y$. Entonces $g$ induce un mapeo $f: Y \rightarrow Z$ tal que $f \circ p = g$. El mapeo inducido $f$ es continuo si y solo si $g$ es continuo; $f$ es un mapeo cociente si y solo si $g$ es un mapeo cociente. 

### ![mapeo-cociente](/assets/images/mapeo-cociente.png)



**Corolario.** Sea $g. X \rightarrow Z$ un mapeo continuo y sobreyectivo. Sea $X^\ast$ la siguiente familia de subconjuntos de $X$:
$$
X^\ast := \{g^{-1}(\{z\}: z \in Z\}.
$$
Asignemos a $X^\ast$ la topología cociente. Entonces

a. El mapeo $g$ induce un mapeo continuo y biyectivo $f: X^\ast \rightarrow Z$, en el que es homeomorfismo si y solo si $g$ es un mapeo cociente.

b. Si $Z$ es Hausdorff, entonces $X^\ast$ es Hausdorff. 

**Proposición.** Sean $X$ y $Y$ espacios topológicos, y sea $f: X \rightarrow Y$ un mapeo continuo tal que  es abierto o cerrado. Entonces

1. Si $f$ es inyectiva, entonces es un *topological embedding*
2. Si $f$ es sobreyectiva, entonces es un mapeo cociente.
3. Si $f$ es biyectiva, entonces es un homeomorfismo.

**Proposición**. Supóngase que $F$ es un mapeo continuo y sobreyectivo de un espacio compacto en un espacio Hausdorff. Entonces $F$ es un mapeo cociente.



### Referencias

- Munkres, ...
- Dugundji...

---

