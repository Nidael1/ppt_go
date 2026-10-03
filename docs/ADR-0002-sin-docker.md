# ADR-0002 — Sin Docker

Fecha: 2026-10-03
Estado: Aceptado

## Contexto

El estándar del método incluye contenedores Docker para el entorno de desarrollo
y despliegue.

## Decisión

No usar Docker en este proyecto.

## Justificación

- Uso personal local; el desarrollador controla el entorno directamente.
- Go compila a binario único; no hay dependencias de runtime complejas.
- Sin base de datos en contenedor (ver ADR-0001).

## Consecuencias

- El entorno de desarrollo depende de Go y Node instalados en la máquina.
- Sin aislamiento de contenedor, pero no es necesario para uso personal.
