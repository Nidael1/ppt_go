# 11 — Seguridad

Datos sensibles y controles aplicables.

## Datos manejados

- Iniciales del jugador (3 letras): no son datos personales sensibles.
- Puntuaciones: sin información personal.

## Controles

- El servidor solo escucha en localhost; no exponer al exterior.
- Validar que las iniciales sean exactamente 3 caracteres A-Z antes de guardar.
- Validar que la eleccion sea uno de los tres valores válidos antes de procesar.

## Fuera de alcance

Sin autenticación, sin HTTPS, sin datos sensibles de usuario.
