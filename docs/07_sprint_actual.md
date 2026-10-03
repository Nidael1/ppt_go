# 07 — Sprint actual

Sprint: 1.0 | Fecha de inicio: 2026-10-03

## Issues

### Issue #1 — Estructura inicial del proyecto y servidor HTTP

- [ ] Inicializar módulo Go (`go mod init github.com/Nidael1/ppt_go`)
- [ ] Crear estructura de carpetas: `domain/`, `storage/`, `api/`, `web/`
- [ ] Configurar Gin con ruta de estáticos apuntando a `web/dist/`
- [ ] Inicializar proyecto Vue 3 + Vite + TypeScript en `web/`
- [ ] Verificar que `go run .` sirve la página de Vue en localhost:8080

**Criterios de aceptación:**
- `go run .` arranca sin error.
- `curl localhost:8080` devuelve el HTML de Vue.
- `go vet ./...` sin errores.

**Tests:** ninguno en este issue (solo scaffolding).

---

### Issue #2 — Motor de juego (dominio)

- [ ] Definir tipos: `Eleccion`, `ResultadoRonda`, `Ronda`, `Partida`
- [ ] Implementar `ResolverRonda(jugador, maquina Eleccion) ResultadoRonda`
- [ ] Implementar `EleccionAleatoria() Eleccion`
- [ ] Implementar `CalcularPuntos(resultado ResultadoRonda) int`
- [ ] Implementar `PartidaTerminada(p Partida) bool`

**Criterios de aceptación:**
- Las 9 combinaciones de ronda devuelven el resultado correcto.
- `CalcularPuntos` devuelve +3, +1 o −3 según corresponde.
- `PartidaTerminada` es true exactamente cuando alguien llega a 3 victorias.

**Tests:** unitarios en `domain/juego_test.go`, una prueba por regla de ronda.

---

### Issue #3 — Persistencia JSON de la tabla de records

- [ ] Definir `EntradaTabla` y `TablaDeRecord`
- [ ] Implementar `CargarTabla(ruta string) (TablaDeRecord, error)`
- [ ] Implementar `GuardarTabla(ruta string, t TablaDeRecord) error`
- [ ] Implementar `IntentarAgregar(t *TablaDeRecord, e EntradaTabla) bool`

**Criterios de aceptación:**
- Una tabla vacía acepta la primera entrada.
- Con 3 entradas, solo entra si la puntuacion supera la menor.
- En empate exacto, no desplaza a la entrada existente.
- El archivo JSON se escribe y se lee correctamente.

**Tests:** integración en `storage/tabla_test.go` con archivo temporal.

---

### Issue #4 — API REST

- [ ] `POST /api/partidas` → crea y devuelve ID de partida
- [ ] `POST /api/partidas/:id/rondas` → recibe eleccion, devuelve resultado de ronda y estado de partida
- [ ] `POST /api/partidas/:id/finalizar` → recibe iniciales, guarda en tabla si aplica
- [ ] `GET /api/records` → devuelve las 3 entradas

**Criterios de aceptación:**
- 400 si la eleccion no es piedra/papel/tijeras.
- 400 si las iniciales no son exactamente 3 letras A-Z.
- 409 si se intenta jugar en una partida ya terminada.
- La tabla en disco se actualiza tras `finalizar`.

**Tests:** unitarios en `api/handlers_test.go` con servidor de test de Gin.

---

### Issue #5 — Frontend: pantalla de juego y tabla de records

- [ ] `PantallaJuego`: botones piedra/papel/tijeras, resultado de ronda, marcador
- [ ] `PantallaFin`: input de 3 letras y botón enviar
- [ ] `TablaRecord`: lista las 3 entradas
- [ ] Estilo retro: fuente monoespaciada (VT323 o similar), paleta oscura, pixelada
- [ ] Flujo completo: inicio → juego → fin → tabla

**Criterios de aceptación:**
- El jugador puede completar una partida de inicio a fin sin recargar.
- La tabla se actualiza al volver a la pantalla principal.
- El diseño es legible en una ventana de 800×600px.

**Tests:** ninguno de UI en v1 (fuera de alcance).
