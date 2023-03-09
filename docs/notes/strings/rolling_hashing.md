---
title: Rolling Hashing
description: Explicación del algoritmo de Rolling Hashing y su implementación en C++.
---

## Introducción

Supongamos que quieres saber si el dígito $0$ esta o no dentro de un numero muy grande. Este es un clásico algoritmo de búsqueda secuencial donde ves dígito por dígito si es igual o no a $0$. Si el largo del numero es de $n$ entonces la complejidad es $\mathcal{O}(n)$.

Modifiquemos un poco el problema y en vez de saber si un dígito está en el numero preguntemos si un string está dentro de otro. Por ejemplo, verificar si `abc` está en `abracadabra`. Al ocupar el mismo algoritmo de búsqueda secuencial la complejidad no será de $\mathcal{O}(n)$ ya que la comparación de strings se hace carácter por carácter. De hecho su complejidad es de $\mathcal{O}(n \cdot m)$ donde $m$ es el largo del string que estamos buscando.

Acá es donde entra el algoritmo de **Rolling Hashing**. Este algoritmo nos va a permitir comparar dos strings en $\mathcal{O}(1)$. La intuición por detrás es que vamos a transformar cada substring que queremos comparar en un _dígito_ para que asi hacer uns búsqueda secuencial con números. Los cuales son comparados en $\mathcal{O}(1)$.

!!! info
    Un hash es una función que sirve para almacenar y recuperar datos de una manera eficiente.

## Hashing

Para calcular el hash de una cadena ocupamos _polynomial hashing_. La idea es que cada carácter de la cadena se encripta en un número. Y luego anidamos para alguna _base_.

!!! intuition "Intuición"
    Pasar de `abc` $\rightarrow$ `123` y `dcbe` $\rightarrow$ `4321`.

El problema es que si la cadena es muy larga, el número podría ser muy grande y no caber en un `int` (_overflow_). Para solucionar esto ocuparemos aritmética modular.

Sea $S$ el string que queremos encriptar, y $A$ y $B$ dos primos. Entonces, el hash de $S$ es:

$$
\sum_{i=0}^{n-1} S[i] \cdot A^i \mod B
$$

Cada carácter se multiplica por una potencia de $A$ para minimizar la probabilidad de colisiones. El módulo $B$ es para evitar que el número sea muy grande y tengamos problemas de overflow. El valor de cada carácter ($S[i]$) se puede obtener de la tabla ASCII o de alguna otra tabla que se nos ocurra.

### Ejemplo

Supongamos que queremos calcular el hash de la cadena `"PABLO"`. El valor ASCII de cada carácter es:

<center>

| P | A | B | L | O |
|---|---|---|---|---|
| 80 | 65 | 66 | 76 | 79 |

</center>

Ocupando los primos $A=31$ y $B=10^9 + 7$:

$$
\begin{aligned}
80 \cdot 31^0 + 65 \cdot 31^1 + 66 \cdot 31^2 + 76 \cdot 31^3 + 79 \cdot 31^4 \mod (10^9 + 7) = 75287796
\end{aligned}
$$

En código sería:

!!! code-cpp " "

    ```cpp
    int pol_hash(string s) {
        int A = 31, B = 1e9 + 7;
        int n = s.size(), h = 0;
        for (int i = n - 1; i >= 0; i--) {
            h = (h * A + s[i]) % B;
        }
        return h;
    }
    ```

## Preprocesamiento

Recordemos que queremos ocupar rolling hashing para resolver problemas de búsqueda de un string en otro más grande. En cuyo caso no nos conviene estar calculando el hash de cada substring a comparar en cada consulta. En vez de eso, ocuparemos un arreglo de hashes, donde cada posición $i$ del arreglo contiene el hash de la cadena desde la posición $i$ hasta el final.

Supongamos que $h$ es dicho arreglo y que $i < j$. Entonces:

$$
\begin{aligned}
h[i] = \sum_{k=i}^{n-1} S[k] \cdot A^{k-i} \mod B \\
h[j] = \sum_{k=j}^{n-1} S[k] \cdot A^{k-j} \mod B
\end{aligned}
$$

Si intentamos restar $h[i]$ a $h[j]$ se obtiene:

$$
\begin{aligned}
h[i] - h[j] &= \sum_{k=i}^{n-1} S[k] \cdot A^{k-i} - \sum_{k=j}^{n-1} S[k] \cdot A^{k-j} \mod B \\
&= \left ( \sum_{k=i}^{j-1} S[k] \cdot A^{k-i} + \sum_{k=j}^{n-1} S[k] \cdot A^{k-i} \right ) - \sum_{k=j}^{n-1} S[k] \cdot A^{k-j} \mod B
\end{aligned}
$$

Para cancelar las dos sumatorias de la derecha hace falta multiplicar $h[j]$ por $A^{j-i}$. Ahora si tendremos que:

$$
\begin{aligned}
h[i] - h[j] \cdot A^{j-i} &= \sum_{k=i}^{j-1} S[k] \cdot A^{k-i} \mod B
\end{aligned}
$$

Por lo que $h[i] - h[j] \cdot A^{j-i}$ es el hash de $S[i \dots j]$ (sin contar al carácter $j$-ésimo).

Ahora, veamos cómo calcular $h[i]$ para cada $i$. Para ello podemos aprovecharnos d ela siguiente recursión:

$$
\begin{aligned}
h[0] &= S[0] \\
h[i] &= S[i] + S[i - 1] \cdot A \\
\end{aligned}
$$

Además de esto, ocuparemos un arreglo $p$ que contiene las potencias de $A$:

$$
\begin{aligned}
p[0] &= 1 \\
p[i] &= p[i - 1] \cdot A \mod B \\
\end{aligned}
$$

Así, el hash de un substring $S[i \dots j]$ es:

$$
\begin{aligned}
h[i] - h[j + 1] \cdot p[j - i + 1] \mod B \\
\end{aligned}
$$

y en el caso de que $i = 0$ se reduce a $h[j]$.

## Implementación

### Código

Pueden encontrar la implementación de rolling hashing en el siguiente [link](https://github.com/Wh4rp/Competitive-Programming/blob/main/Notes/Strings/Rolling%20Hashing.h){:target="_blank"}. Esta implementación es con dos $B$, pero es básicamente la misma que se muestra a continuación.

La función `preprocessor` que calcula los hashes de cada posición del string $S$. Y la función `get_hash` que calcula el hash de un substring $S[i \dots j]$:

!!! code-cpp " "
    ```cpp  
    const int MAXN = 1e5 + 5;
    const int A = 31;
    const int B = 1e9 + 7;

    int n;
    string s;
    int h[MAXN], p[MAXN];

    void preprocessor() {
        p[0] = 1;
        for (int i = 1; i <= n; i++) {
            p[i] = (p[i - 1] * A) % B;
        }
        h[0] = s[0];
        for (int i = n - 1; i >= 0; i--) {
            h[i] = (h[i + 1] * A + s[i]) % B;
        }
    }

    int get_hash(int i, int j) {
        return (h[i] - h[j] * p[j - i] + B * B) % B;
    }
    ```

### Uso

Supongamos que queremos encontrar el primer substring de $S$ que es igual a `"PABLO"`. Usando la función `get_hash` podemos calcular el hash de `"PABLO"` y luego comparar con los hashes de cada posición de $S$:

!!! code-cpp " "
    ```cpp
    int main() {
        cin >> s;
        n = s.size();
        preprocessor();
        string r = "PABLO";
        int m = r.size();
        int l = pol_hash(r);
        for (int i = 0; i + m - 1 < n; i++) {
            if (get_hash(i, i + m) == l) {
                cout << i << '\n';
                break;
            }
        }
        return 0;
    }
    ```

## Recomendaciones

- Los jueces pueden tener casos de prueba que haga que se caigan las soluciones con constantes conocidas (a.k.a. $10^9 + 7$). En ese caso, se recomienda ocupar números primos aleatorios, pero que estén en el rango de $10^9$.

## Material consultado

- [Competitive Programmer’s Handbook — String Hashing](https://usaco.guide/CPH.pdf#page=255){:target="_blank"}
- [ProgompCL — Rolling Hashing](https://progcomp.cl/rollinghashing){:target="_blank"}
