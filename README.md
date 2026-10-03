# PPT Go — Piedra Papel Tijeras retro

Juego clásico de Piedra Papel Tijeras con estética retro de 8 bits,
construido con Go + Vue 3. Corre en local, sin conexión a internet.

## Cómo se juega

- Elige piedra, papel o tijeras cada ronda.
- Gana el primero en llegar a **3 victorias**.
- Al terminar la partida, ingresa **3 letras** para registrar tu puntaje.
- La tabla guarda los **3 mejores puntajes** entre sesiones.

## Puntuación por ronda

| Resultado | Puntos |
|---|---|
| Victoria | +3 |
| Empate | +1 |
| Derrota | −3 |

## Requisitos

- Go 1.24+
- Node 24 LTS

## Arrancar

```sh
# Primera vez
cd web && npm install && npm run build && cd ..
go run .
```

Abrir http://localhost:8080 en el navegador.

## Tests

```sh
go test ./...
```

## Stack

- Backend: Go 1.24, Gin
- Frontend: Vue 3 + Vite + TypeScript
- Persistencia: archivo `scores.json` local
