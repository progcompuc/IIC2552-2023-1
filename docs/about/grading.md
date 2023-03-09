---
title: "Cálculo de la Nota Final"
---


# Cálculo de la Nota Final

- Sea $P_i =$ total puntos por problemas resueltos **dentro** de plazo en el contest $i$-ésimo
- Sea $T_i =$ total puntos por problemas resueltos **fuera** de plazo en el contest $i$-ésimo
- Sea $M_i =$ puntaje mínimo esperado para el contest $i$-ésimo
- Sea $A_i = 1$ si viniste a clases para el contest $i$-ésimo, $0$ si no
- Sea $N =$ número de contests

Así, se calcula:

- $D_i = \max(M_i - P_i, 0) =$ deuda de puntaje del contest $i$-ésimo
- $PA_i = 3$ si vienes a clase, $\max(0, \min(3, P_i - M_i))$ si no vienes
- $E_i = \max(P_i - M_i, 0) + T_i - (1-A_i) \cdot PA_i =$ excedente de puntaje del contest $i$-ésimo, considerando posible descuento por inasistencia
- $X_i = 1 - \frac{D_i}{M_i} =$ fracción completada del mínimo esperado para el contest $i$-ésimo
- $D =$ suma de todos los $D_i$
- $E =$ suma de todos los $E_i$
- $X =$ promedio de todos los $X_i$
- $A = \frac{\min(1, \sum PA_i)}{(3 \cdot (N-2))}$, el $-2$ considera dos días de inasistencia perdonados

Así, $E$ se usa para reducir la deuda $D$ de la siguiente manera:

- $D' = \max(D - E \cdot 0.3, 0)$
- $X' = X + (1-X) \cdot \frac{(D-D')}{D}$

Así, se obtiene una nota preliminar

- $\operatorname{Nota}_{V1} = (1 + 6 \cdot X') \cdot 0.75 + (1 + 6 \cdot A) \cdot 0.25$

Sin embargo, luego se bajará la escala del curso, es decir, si ningún alumno alcanzó el $7$, el alumno con mayor nota quedará con $7$ (siempre y cuando la escala baje "poco" - i.e. habrá un límite para bajar la escala con el fin de prevenir "hacks" al sistema).

- $\operatorname{Nota}_{V2} =$ aplicar_escala_reducida($\operatorname{Nota}_{V1}$)

Luego se calcula las décimas de bonus efectivas:

- $B = (BCpp + BRPC + BCI) \cdot \frac{(\operatorname{Nota}_{V1} - 1)}{6}$

Finalmente, la nota final está dada por:

- $\operatorname{Nota}_{V3} = \operatorname{Nota}_{V2} + B$

Todo lo anterior se encuentra formalizado en el spreadsheet de notas y asistencia: [link](https://docs.google.com/spreadsheets/d/1aQw5LfJJjrb4xYWpaZi9x6e6Sv3BpKT0TN-stCyU3_c/)
