# 04 — Productos y módulos

Módulos del sistema, sus límites y dependencias.

## Módulos

### backend (Go)

| Paquete | Responsabilidad |
|---|---|
| domain/ | Entidades, reglas de ronda, cálculo de puntuacion |
| storage/ | Lectura y escritura del archivo JSON de la tabla |
| api/ | Handlers HTTP (Gin): iniciar partida, jugar ronda, registrar puntaje |
| main.go | Arranque del servidor, sirve estáticos de web/dist/ |

### frontend (Vue 3 + Vite + TypeScript)

| Componente | Responsabilidad |
|---|---|
| PantallaJuego | Selección de eleccion, muestra resultado de ronda y marcador |
| PantallaFin | Captura 3 letras al terminar y envía al backend |
| TablaRecord | Muestra las 3 entradas de la tabla |
| App.vue | Enruta entre pantallas |

## Dependencias entre módulos

- api/ depende de domain/ y storage/.
- domain/ no depende de nada externo.
- storage/ solo conoce las entidades de domain/.
- El frontend solo se comunica con la API REST.

## Archivo de persistencia

`scores.json` en el directorio de trabajo del binario.
Formato: `[{"iniciales":"AAA","puntuacion":7}, ...]`
