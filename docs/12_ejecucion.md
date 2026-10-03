# 12 — Ejecución

Cómo clonar, correr, probar y compilar.

## Requisitos

- Go 1.24+
- Node 24 LTS
- Git

## Primera vez

```sh
git clone https://github.com/Nidael1/ppt_go
cd ppt_go
cd web && npm install && npm run build && cd ..
go run .
```

Abrir http://localhost:8080 en el navegador.

## Tests

```sh
# Backend
go test ./...

# Frontend (si se agregan tests Vitest en sprint 2)
cd web && npx vitest run
```

## Compilar binario

```sh
cd web && npm run build && cd ..
go build -o ppt_go .
./ppt_go
```

## Estrategia de pruebas

- Unitarios en `domain/`: cubren todas las reglas de ronda y puntuacion.
- Integración en `storage/`: usan archivo temporal, lo eliminan al terminar.
- Handlers en `api/`: usan `httptest` de Go, sin levantar servidor real.
- Sin tests de UI en v1.
