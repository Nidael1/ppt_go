# 10 — Operativos

Cómo desplegar y operar el sistema.

## Entorno

Solo local. Sin Docker. Sin Fly.io. Ver ADR-0002 y ADR-0003.

## Arranque

```sh
# Compilar frontend
cd web && npm run build && cd ..

# Arrancar servidor
go run .
```

El servidor escucha en `localhost:8080` por defecto.
La variable de entorno `PORT` cambia el puerto.
La variable `SCORES_FILE` cambia la ruta del archivo JSON (default: `scores.json`).

## Actualizar dependencias

```sh
go get -u ./...
cd web && npm update
```

## Backup del archivo de records

`scores.json` en el directorio del binario. Copiarlo manualmente si se quiere
preservar la tabla entre reinstalaciones.
