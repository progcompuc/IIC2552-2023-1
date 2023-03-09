---
title: KMP
description: Explicación del algoritmo de KMP y su implementación en C++.
---

# Algoritmo de Knuth-Morris-Pratt (KMP)

## Introducción

El algoritmo de KMP es un algoritmo que sirve para encontrar todas las ocurrencias de un patrón en un string. KMP es una mejora del algoritmo de fuerza bruta. El algoritmo de fuerza bruta revisa cada posición del string y va comparando el patrón con el substring del string que empieza en esa posición. El algoritmo de KMP es más eficiente porque cada vez que hay una comparación fallida, se salta a la siguiente posición del string donde es posible que el patrón aparezca. Se aprovecha de las comparaciones parciales. Cosa que no hace el algoritmo de fuerza bruta.

## Observación base

KMP se basa en la siguiente observación. Si tenemos un patrón el cual tiene una comparación parcial correcta de un prefijo suyo. Si este último posee un prefijo ($p$) y un sufijo ($s$) que son iguales ($p = s$). Entonces si se falla en el siguiente carácter, podemos saltar a cuando inicia el sufijo y asumir que el prefijo ya fue comparado correctamente. Esto se puede ver en la siguiente ejemplo:

Patrón a buscar `ABABAC`, string `ABABABAC`.

Se hace el siguiente proceso:

1. Se compara hasta `ABABA`, la cual es una comparación parcial correcta.

    $$
        \colorbox{yellowgreen}{ABABA} BAC
    $$

2. Falla en la comparación del carácter `C` con el carácter `B`.

    $$
        \colorbox{yellowgreen}{ABABA} \colorbox{red}{B} AC
    $$

3. Como el prefijo `ABABA` tiene un sufijo `ABA` y un prefijo `ABA` que son iguales, podemos saltar a la posición donde inicia el sufijo y asumir que el prefijo ya fue comparado correctamente.

    $$
        AB\colorbox{yellowgreen}{ABA}BAC
    $$

4. Continuamos comparando hasta que se encuentra una comparación total correcta.

    $$
        AB\colorbox{yellowgreen}{ABABAC}
    $$

!!! note
    `ABABA` también tenía el prefijo/sufijo `A` pero si hubiéramos saltado a esa posición no habríamos encontrado el patrón en el string. De todos modos no siempre va a convenir utilizar el prefijo/sufijo más largo.

## Implementación

La implementación de KMP es muy similar a la de fuerza bruta. La diferencia es que vamos a dar saltos en el string cuando hay una comparación parcial fallida. Pero primero debemos calcular los saltos que vamos a dar.

### Función de fallo

Vamos a ocupar la _observación_ y calcularemos el largo del prefijo/sufijo más largo para cada prefijo del patrón. Si no tiene, entonces su largo será de $0$.

Sigamos con el mismo ejemplo donde el patrón es `ABABAC`. Su arreglo de prefijos/sufijos más largos $f$ será:

<center>

| Prefijo | Prefijo más largo | Largo prefijo más largo ($f(i)$)|
|:-------:|:-----------------:|:-------------------------------:|
|  ""     | ""                | 0                               |
| `A`     | ""                | 0                               |
| `AB`    | ""                | 0                               |
| `ABA`   | `A`               | 1                               |
| `ABAB`  | `AB`              | 2                               |
| `ABABA` | `ABA`             | 3                               |
| `ABABAC`| ""                | 0                               |

</center>

Donde "" es el string vacío.

Llamaremos $f(i)$ al largo del prefijo/sufijo más largo del prefijo del patrón de largo $i$.

Notemos que $f(f(i))$ es la segunda mejor coincidencia de prefijo/sufijo más largo. Por ejemplo, si $f(5) = 3$, entonces $f(3) = 1$. Que coincide con que `ABABA` tiene tanto a `ABA` como a `A` como prefijo/sufijo's. Esto se puede iterar, y obtener el tercero mejor, cuarto mejor y así, hasta llegar a $f(f(\ldots)) = 0$.

Esta observación nos sirve para calcular $f(i)$ sabiendo todos los $f(j)$ con $j < i$. $f(i)$ va a ser igual al largo del prefijo/sufijo más largo del prefijo de largo $i - 1$ que se pueda extender con el carácter $i$-ésimo, o sea que siga siendo prefijo/sufijo del prefijo $i$. Por lo que hay que comprobar con todos los prefijo/sufijo's del prefijo de largo $i - 1$. Acá ocupamos la observación iterando $f(i-1)$ sobre si misma.

#### Código

A esto se le llama _función de fallo_ y su implementación en C++ es la siguiente:

!!! code-cpp " "

    ```cpp
    vector<int> failure_function(string pattern) {
        int n = pattern.size();
        vector<int> f(n + 1);
        f[0] = f[1] = 0;    // (1)!
        for (int i = 2; i <= n; i++) {
            int j = f[i - 1];    // (2)!
            
            while (j > 0 && pattern[j] != pattern[i - 1]){    // (3)!
                j = f[j];
            }
            
            if (pattern[j] == pattern[i - 1]){    // (4)!
                j++;
            }
            
            f[i] = j;    // (5)!
        }
        return f;
    }
    ```

    1. :man_raising_hand: Inicializamos los casos base.
    2. :man_raising_hand: Inicializamos j con el prefijo/sufijo más largo del prefijo de largo i - 1.
    3. :man_raising_hand: Iteramos siempre y cuando no podamos extender el prefijo/sufijo del prefijo de largo i - 1 con el carácter j-ésimo.
    4. :man_raising_hand: Si podemos extender el prefijo/sufijo del prefijo de largo i - 1 con el carácter j-ésimo, entonces lo extendemos.
    5. :man_raising_hand: Guardamos el prefijo/sufijo más largo del prefijo de largo i.

### Implementación KMP

Ahora que tenemos la función de fallo podemos implementar el algoritmo KMP.

Como ya se mencionó en un inicio, la idea va a ser que cada que una comparación parcial falle, vamos a saltar a la posición donde inicia el prefijo/sufijo más largo del prefijo que ya fue comparado. Y continuamos con el siguiente carácter. Si este siguiente carácter no coincide, intentamos con el segundo mejor prefijo/sufijo. Y así sucesivamente hasta llegar a que no hayan más prefijos/sufijos o que alguno calce, y continuamos con la comparación parcial normal.

#### Código

El código de KMP en C++ es el siguiente:

!!! code-cpp " "

    ```cpp
    vector<int> kmp(string text, string pattern) {
        vector<int> f = failure_function(pattern);
        vector<int> matches;
        int n = text.size();
        int m = pattern.size();
        int i = 0, j = 0;    // (1)!
        while (i < n) {
            if (text[i] == pattern[j]) {    // (2)!
                i++;
                j++;
                if (j == m) {   // (3)!
                    matches.push_back(i - m);
                    j = f[j];
                }
            } else if (j > 0) {    // (4)!
                j = f[j];
            } else {    // (5)!
                i++;
            }
        }
        return matches;
    }
    ```

    1. :man_raising_hand: i es el índice del texto y j es el índice del patrón.
    2. :man_raising_hand: Si el carácter i-ésimo del texto coincide con el carácter j-ésimo del patrón, entonces avanzamos ambos índices. 
    3. :man_raising_hand: Si j llega a ser igual al largo del patrón, entonces encontramos una coincidencia y guardamos la posición donde inicia el patrón en el texto. Luego, asignamos j al prefijo/sufijo más largo del prefijo de largo j.
    4. :man_raising_hand: Si j es mayor a 0, significa que estamos buscar el prefijo/sufijo más largo del prefijo de largo j que coincida con la expansión del carácter i-ésimo del texto. Por lo que vamos por el siguiente candidato, f(j). 
    5. :man_raising_hand: Si no, entonces avanzamos i. Este es el caso de la búsqueda normal.

## Material consultado

- [Introduction to String Searching Algorithms — topcoder](https://www.topcoder.com/thrive/articles/Introduction%20to%20String%20Searching%20Algorithms){:target="_blank"}
