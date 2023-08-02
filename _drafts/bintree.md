---
layout: post
title:  "Nota Breve Sobre Árboles Binarios de Búsqueda"
date:   2023-08-04 12:00:00
category: post
tags: combinatoria
---

Una de las experiencias más satisfactorias en matemáticas es descubrir equivalencias entre estructuras aparentemente ajenas. Una de estas equivalencias
es el caso de "árboles binarios de búsqueda" y "strings de paréntesis bien formados". 

Recordemos que un árbol es una gráfica conexa sin ciclos. Un árbol binario, es un árbol tal que el grado de cada uno de sus vértices es a lo más dos (de tal manera que podemos hablar de vecinos izquierdo y derecho). Y finalmente, un árbol binario de búsqueda (en adelante, ABB), es aquel cuyos vértices están etiquedos y que satisfacen las siguientes tres propiedades:
1. El subárbol izquierdo de un vértice dado, contiene vértices cuyas etiquetas son menores que la etiqueta del vértice.
2. El subárbol derecho de un vértice dado, contiene vértices cuyas etiquetas son mayores que la etiqueta del vértice.
3. Los subárboles izquierdo y derecho son también ABB.

[EJEMPLO DE ÁRBOLES BINARIOS]()

Un string de paréntesis es simplemente un string que consiste únicamente de los caracteres ```(``` y ```)``` (paréntesis izquierdo y derecho, respectivamente). Por "bien formado" queremos decir un string de paréntesis que satisfacen dos propiedades: 
1. El número de paréntesis izquierdos y derechos es igual;
2. Todo substring tiene más o la misma cantidad de paréntesis izquierdos que derechos. 

Los siguientes son ejemplos de strings de paréntesis bien formados.

```
()()(), ((())), ()(()), (())(), (()())
```

Y los siguientes son ejemplos de strings de paréntesis que satisfacen la propiedad 1, pero no la prodiedad 2.
```
))(((), ()))((, (()))(, )))(((, )()()(
```

Estas estructuras aparecen recurrentemente en combinatoria y ciencias computacionales. Tan es así, que en LeetCode aparecen en (al menos) los siguientes problemas.

[IMAGEN de LEETCODE PARENTESIS]()

[IMAGEN De leetcode arboles]()

Definamos el conjunto $ABB(n)$ como el conjunto de ABB cuyos vértices están etiquetados por el conjunto $\{1,2, \ldots, n\}$ sin repeticiones. Y también definamos el conjunto $D(n)$ como el conjunto de strings de paréntesis bien formados de longitud $2n$.

Lo interesante de todo esto es que podemos encontrar una relación biyectiva (ver apéndice, para una presentación más formal) entre estas estructuras mediante las siguientes reglas:s

1. Por cada vértice en el árbol escribimos ```()```.
2. Si el vértice tiene un vecino derecho, anidamos lo escrito por el vértice derecho.
3. Si el vértice tiene un vecino izquierdo, adjuntamos (_append_) lo escrito por el vértice izquierdo.

[IMAGEN de equivalencia]()

Un solución para resolver el problema (TAL) es el siguiente (vea esta nota para más explicación):

```python
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        pref_list = [('', 0, 0)]
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

Por tanto, para resolver TAL, podemos usar la solución previa y luego utilizar la función biyectiva para solucionar TAL. Cosas bonitas de que uno se encuentra casualmente en matemáticas.

Como comentario extra, en una [nota previa]() demostramos que el número de strings de paréntesis bien formados de longitud $2n$ está dado por los números de Catalán
$$C_n = \frac{1}{n+1} {2n \choose n}.$$

En LeetCode aparece este [problema](LINK) 

[PROBLEMA DE LEETCODE]()

Dado que encontramos una biyección entre el conjunto de ABB en $n$ vértices y el número de strings de paréntesis bien formados, podemos utilizar el resultado anterior (y algo de recursión de los números de Catalan) para resolver este problema. Note que una solución estándar involucaría utilizar programación dinámica (o estrategias similares). Así pues, con saber un poco de matemáticas podemos evitar algo de trabajo. 

```python
class Solution:
    def numTrees(self, n: int) -> int:
        if n == 1:
            return 1    
        previous_catalan = self.numTrees(n-1)
        return int(previous_catalan * (4*n - 2) / (n + 1))
```

Esto es solo un caso del sinnúmero de cosas bonitas que uno se encuentra en matemáticas. 

## Apéndice

Para toda $n$ en $\mathbb{N}$, sea $\Sigma(n)$ el conjunto de todas las $2n$-eadas cuyas entradas toman únicamente los valores $\pm 1$. Definamos el conjunto $D(n)$, como el subcojunto de $\Sigma(n)$ tal que
1. si $s = (a_1, \ldots, a_{2n}) \in D(n)$, entonces $\sum_{i=1}^{2n} a_i = 0$;
2. si $s = (a_1, \ldots, a_{2n}) \in D(n)$, entonces $\sum_{i=1}^{k} a_i \leq 0$, para cualesquiera $1 \leq k \leq 2n$. 

Note que este conjunto es precisamente el conjunto de strings de paréntesis bien formados (sustituya el $-1$ por ```(``` y el $1$ por ```)```).

