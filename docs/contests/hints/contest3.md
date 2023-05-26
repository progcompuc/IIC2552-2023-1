---
title: contest 3 - hints y códigos de ejemplo
---

# Contest 3 - hints y códigos de ejemplo

### A - Ehab Is an Odd Person
<details> 
   <summary>Hint</summary>
   Todo depende de si hay al menos un número de paridad distinta al resto.
</details>

### B - Positive Divisors
<details> 
   <summary>Hint</summary>
   Notemos que si x divide a N entonces o x < sqrt(N) o N/x < sqrt(N). Luego basta revisar los divisores <= sqrt(N).
</details>

### C - Cumulative Sum Query
<details> 
   <summary>Hint</summary>
   Piensen en como usar un arreglo de sumas acumuladas, es decir, u arreglo A donde A[i] guarde la suma de los primeros i valores.
</details>

### D - Massive Card Game
<details> 
   <summary>Hint</summary>
   Primero ordenemos el arreglo, luego podemos usar 2 búsquedas binarias, ver los problemas E y F como primer paso.
</details>

### E - Búsqueda Binaria
<details> 
   <summary>Hint</summary>
   Implementación 101 de búsqueda binaria lower bound, pueden buscar ejemplos de implementación adicional en materiales del curso.
</details>

### F - Búsqueda Binaria 2
<details> 
   <summary>Hint</summary>
   Implementación 101 de búsqueda binaria upper bound, pueden buscar ejemplos de implementación adicional en materiales del curso.
</details>

### G - Berland collider
<details> 
   <summary>Hint</summary>
   Deben hacer búsqueda binaria decimal en el tiempo, para esto deben poder checkear dado un tiempo si es que ha habido un choque hasta ese momento. Piensen en cómo chequear eso.
</details>

### H - Vanya and Lanterns
<details> 
   <summary>Hint</summary>
   Si usamos búsqueda binaria para encontrar el radio pedido, debemos pensar en un predicado que dado un radio nos diga si es suficiente para cubrir el camino o no. Pueden chequear esto linealmente recorriendo las lámparas y marcando recordando la máxima coordenada iluminada hacia la derecha, si en algún punto el radio hacia la izquierda no alcanza la coordenada recordada hasta el paso anterior, entonces no cubre todo el camino. Ojo con que la coordenada recordada empieza siendo 0 y que al final deben chequear que se llegue al largo final del camino.
</details>

### I - Need for Speed
<details> 
   <summary>Hint</summary>
   Si usamos búsqueda binaria para encontrar el c pedido, debemos pensar en un predicado que dado un c nos diga si el tiempo que toma es menor o no al tiempo que sabemos que demora el camino. En caso de ser menor necesitamos un c más pequeño y viceversa. Piensen en cómo calculan el tiempo que demoraría el camino dado un c.
</details>

### J - The Meeting Place Cannot Be Changed
<details> 
   <summary>Hint</summary>
   Si usamos búsqueda binaria para poder calcular el menor tiempo necesario para juntarse, debemos generar un predicado que dado un tiempo t nos diga si es posible juntarse o no en ese tiempo. Para esto usen que cada persona i en un tiempo t puede llegar a cualquier punto en un rango (x[i] - v[i] * t, x[i] + v[i] * t).
</details>