---
title: contest 1 - hints y códigos de ejemplo
---

# Contest 1 - hints y códigos de ejemplo

### A - Watermelon
<details> 
   <summary>Hint</summary>
   Lo vimos en clases.
</details>

### B - Stones on the Table
<details> 
   <summary>Hint</summary>
   Basta recorrer el string y sumar uno a la respuesta cada vez que una letra sea igual a la anterior
</details>

### C - Sum of the Others
<details> 
   <summary>Hint</summary>
   Piensen en cuanto debe ser la suma de todo (incluyendo el resultado) si el resultado es igual a la suma
</details>

### D - Temporarily unavailable
<details> 
   <summary>Hint</summary>
   Podemos chequear si no hay intersección y retornar 0 (basta ver si el comienzo de cobertura esta después del final del recorrido o si el final del radio de cobertura está antes del inicio del recorrido), en otro caso basta sumar el tamaño del principio al comienzo del radio de cobertura y del final del radio de cobertura hasta el final del recorrido (si son positivos).
</details>

### E - H-Index
<details> 
   <summary>Hint</summary>
   Se debe encontrar el mayor H tal que tenemos al menos H papers con al menos H citas. Para esto piensen cómo facilita el cálculo ordenar las citas de cada paper de mayor a menor. Ojo que no se puede resolver viendo todas las posibilidades de H y chequeando porque no pasa en el tiempo límite.
</details>

### F - Four Segments
<details> 
   <summary>Hint</summary>
   Busque características necesarias y suficientes para determinar que los segmentos entregados forman un rectángulo, por ejemplo, hay exactamente 4 puntos y 4 segmentos, 2 verticales y 2 horizontales.
</details>

### G - Touchscreen Keyboard
<details> 
   <summary>Hint</summary>
   Podemos asignarles coordenadas de fila y columna a cada letra. Usando esto es fácil obterner la solución calculando distancias y ordenando. Pueden guardar las coordenadas en un diccionario de python o en un map de c++.
</details>

### H - Adding Words
<details> 
   <summary>Hint</summary>
   Pueden usar diccionarios de Python o maps de c++ para asignar valores a las palabras y palabras a los valores. Usando esto piensen en cómo implementar el resto.
</details>

### I - They Are Everywhere
<details> 
   <summary>Hint</summary>
   Hay varias formas de hacerlo, una de las más simple consiste en mantener un rango en que están presentes todos los pokemons para cada posición final. Empezando de la primera posición en que estén todos los pokemons hacia la izquierda, si avanzamos el borde derecho en una posición podemos mover el izquierdo mientras la ocurrencia del pokemon en el borde izquierdo dentro del rango sea mayor a 1. La respuesta final será el mínimo de estos rangos. Está técnica es una aplicación de dos punteros y es un enfoque bastante usado en programación competitiva.
</details>

### J - Problema Horrible 1
<details> 
   <summary>Hint</summary>
   Basta implementar lo descrito en el enunciado. Cuidado con los casos especiales de alineamiento, si hay una cantidad impar de espacio, se da menos espacio a la izquierda primero, la próxima vez con espacios impares a la derecha y así.
</details>
