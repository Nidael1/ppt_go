# 03 — Reglas de negocio y casos borde

Define el comportamiento esperado con precisión.

## Reglas de ronda

| Jugador | Máquina | Resultado |
|---|---|---|
| piedra | tijeras | victoria |
| papel | piedra | victoria |
| tijeras | papel | victoria |
| piedra | piedra | empate |
| papel | papel | empate |
| tijeras | tijeras | empate |
| tijeras | piedra | derrota |
| piedra | papel | derrota |
| papel | tijeras | derrota |

## Puntuación por ronda

- victoria: +3 puntos
- empate: +1 punto
- derrota: −3 puntos

La puntuacion de una partida es la suma de puntos de todas las rondas
jugadas hasta que termina (incluyendo las rondas que perdió el jugador).

## Fin de partida

La partida termina cuando jugador o máquina acumula 3 victorias de ronda.
No hay empate global posible.

## Tabla de puntajes

- Capacidad: máximo 3 entradas.
- Al terminar una partida, se evalúa si la puntuacion entra en la tabla:
  - Si hay menos de 3 entradas: entra siempre.
  - Si hay 3 entradas y la puntuacion supera la menor: reemplaza la menor.
  - Si hay empate con la menor: no entra (se queda el primero en llegar).
- La máquina registra su victoria con iniciales "XXX".
- Si la máquina gana, también se evalúa si "XXX" entra en la tabla con
  la misma lógica.

## Casos borde

- Puntuacion mínima posible en una partida: jugador pierde 3-0 → −9 puntos.
- Puntuacion máxima posible: jugador gana 3-0 → +9 puntos.
- Si todas las entradas de la tabla tienen la misma puntuacion que la nueva,
  no se agrega.
- Las iniciales "XXX" son válidas para un jugador humano también.
