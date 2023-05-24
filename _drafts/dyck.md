---
layout: post
title: "LeetCode y Números de Catalan"
date: 2023-05-23 18:30:00
categories: posts
tags: leetcode
---

Últimamente me he estado divirtiendo [resolviendo](https://github.com/luisgrivas/leetcode) problemas de LeetCode. Aunque en su mayoría los problemas son interesantes, una vez que los resuelvo no suelo pensar más en ellos. Sin embargo, el siguiente [problema](https://leetcode.com/problems/generate-parentheses/description/) captó particularmente mi atención:

> Dados $n$ pares de paréntesis, escribe una función que genere todas las posibles combinaciones de paréntesis balanceados.

Aunque este problema está considerado como nivel medio en LeetCode, tuve dificultad para contrar una solución _elegante_. Claro, una solución ingenua (e ineficiente) consiste en calcular todos los strings posibles de longitud $2n$ con los caracteres ```(``` y ```)``` y conservar solo los que estén balanceados. Pero, ¿que quiere decir balanceados?, dado un string ¿cómo sabemos que este está balanceado?

## Paréntesis Balanceados

Para poder dar con una definición, demos unos pasos atrás y veamos cómo obtenemos paréntesis balanceados. Por ejemplo, considere la siguiente expresión: 

$$(3 \cdot (1 + 2)) \cdot ((3 - 1) / (2 + 2)) / (4 + 3).$$

Para calcular el resultado de esta expresión el uso de los paréntesis es fundamental. Si en esta expresión borramos todos los caracteres menos los paréntesis obtenemos el string ```(())(()())()```. Entonces, podemos decir que que un string de paréntesis está balanceado si se obtuvo de una expresión aritmética como la anterior conservando solo los paréntesis. 

¿Cuáles son las reglas para utilizar paréntesis? Sabemos que siempre que abramos un paréntesis debemos cerrarlo. Ejemplos de esto serían los strings  ```(())``` y ```()()```. Además, debemos exigir que el número de paréntesis izquierdos sea el mismo que el número de paréntesis derechos, pues de lo contrario tendríamos ejemplos como ```)()()```. Así pues, podemos valernos de la siguiente definición.

Un string de paréntesis está balanceado si:
1. A cada paréntesis izquierdo ```(``` le corresponde uno y solo un paréntesis derecho ```)``` _posterior_;
2. el número de paréntesis izquierdos y derechos en el string es igual.

Con esto, el algoritmo para verificar _buen balanceo_ de paréntesis es sencillo: 

```python3
def isValid(self, s: str) -> bool:
	parentheses = {"(": ")"}
	tmp  = []
    for ch in s:
    	if ch in parentheses:
    		tmp.append(ch)
        elif tmp and parentheses[tmp[-1]] == ch:
            tmp.pop()
        else:
            return False
    return not tmp
```

Recorriendo el string de izquierda a derecha: si el caracter es ```(``` lo guardo en una lista (abro paréntesis); si el caracter es ```)```, verifico que exista un correspondiente ```(``` en la lista (verifico que se cumpla 1.): si no existe, el string no es balanceado; si sí existe, borro el caracter ```(``` y continúo con el siguiente caracter. Si al terminar este recorrido, la lista es vacía (se verifica 2.), entonces el string es balanceado; de lo contrario el string no es balanceado.

 ## Lenguaje de Dyck

 ![Palabras de Dyck con 4 pares de paréntesis. Autor: Timan Piesk](https://upload.wikimedia.org/wikipedia/commons/0/01/Dyck_lattice_D4.svg)

La definición anterior nos permite dar una solución por [fuerza bruta](https://en.wikipedia.org/wiki/Brute-force_search) mencionada al inicio de estas notas. Pero si observamos detalladamente lo hecho hasta ahora, veremos que ya tenemos lo necesario para encontrar una solución más inteligente.

Sea $\Sigma $ el conjunto de cuyos únicos elementos son los caracteres ```(``` y ```)```. Para nosotros, la [cerradura de Kleene](https://en.wikipedia.org/wiki/Kleene_star) $\Sigma^\ast$  de $\Sigma$ será el conjunto de todas los strings _finitos_ con caracteres en $\Sigma$. Para todo elemento $s\in \Sigma^\ast$ denote por $lp(s)$ y $rp(s)$ al número de paréntesis izquierdos y derechos contenidos en $s$ respectivamente.

Sea $s\in \Sigma^\ast$ un string de paréntesis balanceado. Si $s^\prime$ es un [prefijo](https://en.wikipedia.org/wiki/Substring#Prefix) de $s$, entonces por 1. y 2., se tiene que $rp(s^\prime) \leq lp(s^\prime)$. Más aún, un razonamiento directo muestra que el converso es cierto. Es decir, si $s\in \Sigma^\ast$ es un string tal que todo prefijo $s^\prime$ de $s$ satisface que $rp(s^\prime) \leq lp(s^\prime)$, entonces $s$ es un string de paréntesis balanceados. Así pues, podemos definir al conjunto de todos los strings de paréntesis balanceados como 

$$B = \{s \in \Sigma^\ast: \text{ todo prefijo } s^\prime \text{ de } s \text{ satisface que } rp(s^\prime) \leq lp(s^\prime)  \}. $$

En matemáticas, al conjunto anterior se le conococe como [lenguaje de Dyck](https://en.wikipedia.org/wiki/Dyck_language) y a sus elementos se les conoce como *palabras de Dyck*. Este conjunto tiene diversas propiedades interesantes que discutiremos más adelante. 

Es natural preguntarse, ¿para qué tanta teoría? Bueno, la definición anterior nos ayuda a pensar de major manera sobre el problema. Precisamente, la definición de $B$ nos permite pensar a los strings de paréntesis balanceados en término de sus prefijos. 

Así pues, para un natural $n$ dado, la complejidad del problema se reduce a calcular iterativamente los strings $t\in \Sigma^\ast$ que satisfagan $rp(t) \leq lp(t) \leq n$. Observe que este es un procedimiento relativamente sencillo. Si $rp(t) = lp(t) = n$, entonces $t$ es un string de paréntesis balanceados de tamaño $2n$. Si $rp(t) < lp(t)$, entonces podemos definir el string ```t_0 = t + )```; si $lp(t) < n$, entonces podemos definir el string ```t_1 = t + (```. Sustituimos al string $t$ por los strings $t_0$ y $t_1$ (en caso de existir) y procedemos iterativamente. Por ejemplo, para el caso $n = 2$ el procedimiento lo podemos ver en el siguiente diagrama:

```mermaid
flowchart LR
   B["("] --> C["()"];
   B --> D["(("];
   D --> E["(()"];
   E --> F["(())"];
   C --> G["()("];
   G --> H["()()"]
````

Con todo ya mencionado, una solución es la siguiente:

```python3
def generateParenthesis(self, n: int) -> List[str]:
    pref_list = [('(', 1, 0)]
    dyck = []
    while pref_list:
        pref, lp, rp = pref_list.pop()
        if lp == rp == n:
            dyck.append(pref)
        else:
            if rp < lp:
                pref_list.append((pref + ')', lp, rp + 1))      
            if lp < n:
                pref_list.append((pref + '(', lp + 1, rp))       
    return dyck
```

## Números de Narayana y Números de Catalan

Definamos para $n \in \mathbb{N}$, el resultado del algoritmo ```generateParenthesis``` para el input $n$. En términos precisos

$$ B_n = \{ s \in B: \lvert s \rvert = 2n \}.$$

Es natural preguntarse, ¿existirá alguna fórmula que nos permita calcular $\lvert B_n \rvert$? En otras palabras, ¿podemos determinar una fórmula para el número de strings de paréntesis balanceados de longitud $2n$? En esta sección daremos una respuesta a esta pregunta. 

En primer lugar, pensemos en una pregunta relacionada. Para $n, k \in \mathbb{N}$, denotemos por $N(n, k)$ al número de elementos de $B_n$ en los que el string ```()``` aparezca exactamente $k$ veces como [substring](https://en.wikipedia.org/wiki/Substring). Por ejemplo, $N(3,2) = 3$ ya que

```
(()())   (())()   ()(())    
```

son los únicos strings en $B_3$ en los que ```()``` aparece dos veces como substring. A los números $N(n, k)$ se les conoce como [números de Nayarana](https://en.wikipedia.org/wiki/Narayana_number). Estos satisfacen los siguientes teoremas.

**Teorema.** Se tiene que 
$$N(n, k) = \frac{1}{n} {n \choose k } \cdot { n \choose k-1}$$

**Teorema**. Los números de Nayarana satisfacen la siguiente relación
$$N(n, k) = N(n, n - k + 1).$$

**Teorema**. Se tiene que 

$$C_n = \sum_{k=1}^n N(n, k),$$
donde $C_n$ es el n-ésimo número de Catalan.