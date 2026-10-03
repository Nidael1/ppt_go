# ADR-0003 — Sin despliegue en Fly.io

Fecha: 2026-10-03
Estado: Aceptado

## Contexto

El estándar del método usa Fly.io para despliegue en producción.

## Decisión

No desplegar en Fly.io ni en ningún servicio en la nube.

## Justificación

- El juego corre exclusivamente en localhost para uso personal.
- Sin requisito de acceso remoto ni compartir con otros usuarios.

## Consecuencias

- Sin CI/CD de despliegue (GitHub Actions solo para CI si se configura).
- El binario se ejecuta directamente en la máquina del desarrollador.
