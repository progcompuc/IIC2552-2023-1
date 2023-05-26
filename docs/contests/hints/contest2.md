---
title: contest 2 - hints y códigos de ejemplo
---

# Contest 2 - hints y códigos de ejemplo

### A - Reversed Binary Numbers
<details> 
   <summary>Hint</summary>
   Si bien en python hay funciones que entregan la representación binaria de un número, traten de construirla, recuerden los operadores bitwise vistos en la clase.
</details>

### B - Two distinct points
<details> 
   <summary>Hint</summary>
   Basta con elegir un número cualquiera del primer segmento y para el segundo elegir alguno de los vértices, mientras sea distinto al punto elegido para el primer segmento.
</details>

### C - Evening Out 1
<details> 
   <summary>Hint</summary>
   Piensen en como usar el resto de A dividido B (A % B).
</details>

### D - Remove Smallest
<details> 
   <summary>Hint</summary>
   Piensen en cómo lo harían si el arreglo estuviera ordenado de mayor a menor.
</details>

### E - Pizza Hawaii
<details> 
   <summary>Hint</summary>
   Podemos guardar en diccionarios/maps para cada ingrediente en qué recetas aparece.
</details>

### F - Chocolate Division
<details> 
   <summary>Hint</summary>
   Busquen una invariante en cuanto a la paridad de los turnos, dependiendo sólo de R y C.
</details>

### G - Zagrade
<details> 
   <summary>Hint</summary>
   Primero debemos obtener una lista de pares de indices correspondientes a pares de paréntesis correlacionados. Para esto basta leer el string dado de izquierda a derecha y tener una lista de posiciones de abre paréntesís aún no acoplados, cada vez que encontremos un cierra paréntesis lo acoplamos con el último abre paréntesis en la lista (y lo quitamos de la lista). Usando esto sólo tenemos que ver todas las combinaciones de pares de paréntesis a eliminar, armar los strings respectivos y ordenar la lista de respuestas.
</details>

### H - Sum
<details> 
   <summary>Hint</summary>
   Primero debemos encontrar una base que genere el mayor largo en la suma, una base que siempre sirve para esto es el mayor dígito que nos dieron en el input + 1.
</details>

### I - Making Sequences is Fun
<details> 
   <summary>Hint</summary>
   Podemos ir agregando los números de n dígitos en bloques mientras sea posible, empezando con n = #(dígitos en m). la cantidad de números con n dígitos que se pueden agregar en un principio es (10^n - m) sumamos eso a la respuesta, updateamos m a 10^n, sumamos uno a n y repetimos mientras no nos pasemos de w.
</details>

### J - Hyperset
<details> 
   <summary>Hint</summary>
   Podemos recorrer cada par de string en el input en O(N^2), para cada par podemos determinar únicamente cuál sería el tercero que armaría un set con estos, por cada caracter si son iguales el tercero debe ser igual y si son distintos el tercero debe tener el que falta, luego basta chequear si el string armado estaba en el input (esto se puede hacer rápido con un set). La complejidad si es bien implementado de esta solución es de O(k * N^2 * log(N)) que pasa en el tiempo.
</details>