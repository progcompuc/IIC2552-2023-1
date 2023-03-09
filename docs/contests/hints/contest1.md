---
title: contest 1 - hints y códigos de ejemplo
---

# Contest 1 - hints y códigos de ejemplo

### A - Largest Rectangle in a Histogram

<details>
  <summary>Hint</summary>
  El rectángulo máximo necesariamente tiene una altura igual a alguna columna. Sólo hay N columnas, así que puedes ponerte en los N casos, y sólo te falta saber el ancho. Dada una columna i-ésima, piensa en alguna forma de encontrar los extremos L[i] y R[i] del rectángulo maximal que se formaría si expandimos la columna i-ésima lo más que se puede hacia ambos lados.
</details>
<details>
  <summary>Solución + código</summary>
  Primero calculamos L[i] de izquierda a derecha (para R[i] podemos hacer lo mismo al revés). Para ello mantenemos un stack, en cada instante el stack guarda los distintos mínimos acumulados de las alturas de las columnas medidos desde la columna i-1 hacia la izquierda, junto con el extremo derecho donde comienza a regir cada mínimo (para entender mejor esto, dibujar un histograma, pararse en alguna columna de al medio y dibujar la altura del mínimo acumulado hacia la izquierda, se ve como una función escalonada). Con ese stack es fácil encontrar L[i] (hacemos pop hasta que llegamos a un mínimo < H[i]) y actualizarlo (pusheamos el par (H[i],i)). Como cada columna es pusheada y popeada sólo 1 vez, la complejidad es O(N). <a href="https://github.com/PabloMessina/Competitive-Programming-Material/blob/master/Solved%20problems/SPOJ/HISTOGRA_LargestRectangleInAHistogram.cpp">Código de ejemplo</a>
</details>
