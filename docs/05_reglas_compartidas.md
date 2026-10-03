# 05 — Reglas compartidas

Convenciones del proyecto que aplican a todo el código.

## Arquitectura

Hexagonal: domain/ no importa nada de infraestructura. Los adaptadores
(api/, storage/) implementan los puertos definidos en domain/.

## Naming

- Go: identificadores sin acentos ni ñ (ejemplo: `puntuacion`, `eleccion`).
- Términos de dominio en español en doc y en código.
- Vue: componentes en PascalCase; composables con prefijo `use`.
- Archivos Vue en PascalCase; archivos Go en snake_case.

## API REST

| Método | Ruta | Descripción |
|---|---|---|
| POST | /api/partidas | Inicia una partida nueva |
| POST | /api/partidas/:id/rondas | Juega una ronda |
| POST | /api/partidas/:id/finalizar | Registra iniciales y cierra la partida |
| GET | /api/records | Devuelve las 3 entradas de la tabla |

## Convenciones de respuesta

- 200 OK con cuerpo JSON para operaciones exitosas.
- 400 Bad Request si la eleccion es inválida o las iniciales no son 3 letras.
- 409 Conflict si se intenta jugar una ronda en una partida ya terminada.

## Tests

- Tests unitarios en domain/ para cada regla de ronda y de puntuacion.
- Tests de integración en storage/ usando un archivo temporal.
