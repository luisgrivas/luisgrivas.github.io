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

La definición anterior nos permite dar una solución por [fuerza bruta](https://en.wikipedia.org/wiki/Brute-force_search) mencionada al inicio de estas notas. Pero si observamos detalladamente lo hecho hasta ahora, veremos que ya tenemos lo necesario para encontrar una solución más inteligente.

Sea $s$ es un string de paréntesis balanceado. Sea $s^\prime$ un [prefijo](https://en.wikipedia.org/wiki/Substring#Prefix) de $s$. Por 1. y 2., se tiene que el número de paréntesis izquierdos de $s^\prime$ es menor o igual que el número de paréntesis derechos de $s^\prime$. 


```mermaid
flowchart LR
   A["' '"] --> B["("];
   B --> C["()"];
   B --> D["(("];
   D --> E["(()"];
   E --> F["(())"];
   C --> G["()("];
   G --> H["()()"]
````


```python3
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

## Números de Catalan
