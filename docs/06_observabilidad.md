# 06 — Observabilidad

Define qué se registra y qué no.

## Qué se registra (Zap, nivel INFO)

- Arranque del servidor: puerto y ruta del archivo scores.json.
- Inicio de partida: ID generado.
- Fin de partida: ganador (jugador o máquina), puntuacion, si entró en tabla.
- Error al leer o escribir scores.json: nivel ERROR con la ruta y el error.

## Qué no se registra

- Cada ronda individual (demasiado verboso para un juego local).
- Las iniciales del jugador en logs (aunque no son sensibles, no aportan).

## Formato

JSON estructurado con Zap. En desarrollo: salida legible (`zap.NewDevelopment()`).
