# COMANDOS

Comandos útiles del proyecto. Revisar con el uso; pueden quedar desactualizados.
Se consolida al cerrar el sprint.

## Desarrollo

```sh
# Instalar dependencias del frontend
cd web && npm install

# Compilar frontend
cd web && npm run build

# Arrancar servidor
go run .

# Tests del backend
go test ./...

# Vet
go vet ./...
```

## Compilar para distribuir

```sh
cd web && npm run build && cd ..
go build -o ppt_go .
```
