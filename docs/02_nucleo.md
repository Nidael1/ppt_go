# 02 — Núcleo del dominio

Entidades, invariantes y lenguaje del dominio.

## Lenguaje del dominio

| Término | Definición |
|---|---|
| partida | Secuencia de rondas hasta que alguien llega a 3 victorias |
| ronda | Un enfrentamiento: jugador elige, máquina elige, se determina resultado |
| eleccion | piedra, papel o tijeras |
| resultado_ronda | victoria, empate o derrota (desde la perspectiva del jugador) |
| puntuacion | Total de puntos acumulados en una partida |
| iniciales | Tres letras mayúsculas que identifican al jugador (o "XXX" para la máquina) |
| entrada_tabla | Una fila de la tabla de puntajes: iniciales + puntuacion |

## Entidades

### Partida
- victorias_jugador: int (0..3)
- victorias_maquina: int (0..3)
- rondas: []Ronda
- terminada: bool

### Ronda
- eleccion_jugador: Eleccion
- eleccion_maquina: Eleccion
- resultado: ResultadoRonda

### TablaDeRecord
- entradas: []EntradaTabla (máximo 3)

### EntradaTabla
- iniciales: string (exactamente 3 letras A-Z)
- puntuacion: int

## Invariantes

- Una partida tiene exactamente una ganadora al terminar (jugador o máquina);
  no termina en empate global.
- Las iniciales tienen exactamente 3 caracteres alfabéticos en mayúsculas.
- La tabla nunca tiene más de 3 entradas.
- Una entrada no desplaza a otra con igual puntaje; solo si lo supera.
