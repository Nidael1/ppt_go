# 01 — Contexto

Define el problema, los usuarios y lo que el sistema NO hace.

## Problema

Tener un juego local de Piedra Papel Tijeras con estética retro y tabla de
puntajes persistente entre sesiones.

## Usuario

Una sola persona, en su máquina local, jugando contra la máquina.

## Alcance funcional — v1

- Jugar una partida: el jugador elige piedra, papel o tijeras cada ronda.
- La partida termina cuando alguien llega a 3 victorias.
- Al terminar la partida, el jugador ingresa 3 letras como identificador.
- La máquina registra sus victorias con el identificador "XXX".
- La tabla muestra los 3 puntajes más altos.
- La tabla persiste en un archivo JSON entre sesiones.

## Exclusiones explícitas

1. Sin conexión a internet ni funcionalidades de red.
2. Sin modo multijugador (local o en línea).
3. Sin sonido ni efectos de audio.
4. Sin cuentas de usuario ni autenticación.
5. Sin Docker ni despliegue en la nube.
