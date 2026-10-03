# ADR-0001 — Almacenamiento en archivo JSON en lugar de PostgreSQL

Fecha: 2026-10-03
Estado: Aceptado

## Contexto

El estándar del método requiere PostgreSQL 16. El proyecto es un juego local
personal que almacena máximo 3 entradas (iniciales + puntuacion).

## Decisión

Usar un archivo JSON (`scores.json`) en lugar de PostgreSQL.

## Justificación

- El volumen de datos es trivial (máximo 3 registros).
- No hay concurrencia: un solo usuario local.
- PostgreSQL añadiría complejidad de instalación y configuración sin beneficio.

## Consecuencias

- Sin migraciones de base de datos.
- Sin dependencia de pgx ni sqlc.
- El archivo scores.json debe respaldarse manualmente si se quiere preservar.
- Si el proyecto crece a multijugador o multiusuario, se revisará esta decisión.
