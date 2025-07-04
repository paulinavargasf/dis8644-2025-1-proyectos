# proyecto-02

## Acerca del proyecto

- Grupo: 05
- Integrantes:
  - Antonia Cristi
  - Natalia Pilar
  - Paulina Vargas
- Chips usados:
  - Chip LM324
  - Chip NE555
  - Chip CD4017

## Presentación textual

Sensor "de vibra" que activa una ruleta de luces mediante la sombra de la mano del usuario.

El proyecto consiste en una entrada que detecta sombra, para encender una secuencia de luces LED.

Se incluye un circuito que detecta la entrada de sonido para encender un solo LED, pero su única finalidad es engañar al usuario.

## Dibujos de diagramas del circuito (1 punto)

Este es el diagrama a mano.

![Dibujo del diagrama a mano](./imagenes/diagrama-mano.jpg)

En este dibujo mostramos XX.

## Prototipado de circuitos en protoboard (1 punto)

A continuación se presentan imágenes de las protoboards usadas.

![Vista protoboards de frente](./imagenes/tme-grupo05-registro01.jpg)

![Vista protoboard principal de frente](./imagenes/tme-grupo05-registro02.jpg)

![Vista protoboard principal de arriba](./imagenes/tme-grupo05-registro03.jpg)

![Vista protoboard principal detalle 1](./imagenes/tme-grupo05-registro04.jpg)

![Vista protoboard principal detalle 2](./imagenes/tme-grupo05-registro06.jpg)

A continuación se presentan textos explicativos del prototipado.

El circuito de entrada usa un LDR para medir la entrada de luz, el umbral de esta se controla por medio de un potenciómetro.

El circuito de salida usa un chip CD4017 para activar una secuencia de 10 luces LED.

### Bill of Materials (1 punto)

|QTY|REFERENCE|VALUE|FOOTPRINT|OBS
|:-:|-|-|-|-
|3|U1,U4,U5|~|Socket 8-pin|-
|1|U2|~|Socket 14-pin|-
|1|U3|~|Socket 18-pin|-
|4|R2,R3,R4,R5,R8,R10,R11|10k|Resistencia|-
|5|R7,R9,R12|1k|Resistencia|-
|1|R6|100k|Resistencia|-
|1|R1|LDR|LDR|-
|3|C1,C4,C7|474n|Condensador cerámico|474
|1|Q1|PN2222A|Transistor|-
|1|MK1|MIC|Micrófono electret|-
|3|C3,C5,C6|1u|Condensador electrolítico|-
|1|C2|100u|Condensador electrolítico|-
|12|D1~D11|LED|LED 5mm|Distintos colores
|1|RV1|500k|Potenciómetro|-
|3|U1,U4,U5|NE555|DIP-8|Van en los socket U1, U4, y U5
|1|U2|LM324|DIP-14|Va en el socket U2
|1|U3|CD4017|DIP-16|Va en el socket U3

## Ayudas y comunicación con colegas (1 punto)

FranUDP del grupo 0c nos ayudó al principio del protipado recomendándonos comenzar a usar el circuito del detector de sombra.

Misaa (docente) nos entregó el esquemático de un circuito que utiliza un micrófono para la entrada y de salida enciende un LED.

FranUDP del grupo 0c nos ayudó agregando un circuito astable entre nuestro chip LM324 y el NE555 monostable que teníamos.

Intentamos ayudar a Sofía Cartes del proyecto 03 en cómo regular la sensibilidad del micrófono de su circuito. Le dijimos que podrían conectar el pin 15 del chip 4017 a tierra, pero no se resolvió el problema.

## Esquematico en Kicad (1 punto)

![Esquemático general](./imagenes/esquematico_general01.png)

![Esquemático general](./imagenes/esquematico_general02.png)

![Esquemático detalles](./imagenes/esquematico_detalle01.png)

![Esquemático detalles](./imagenes/esquematico_detalle02.png)

El esquemático utiliza un sensor de luz, comparador, dos temporizadores 555 y un contador 4017 para activar una secuencia de LEDs de forma controlada por la presencia de sombra.

El detector de sombra funciona por medio de una fotoresistencia que detecta luz, un potenciómetro forma un divisor de voltaje que establece un umbral ajustable, y un chip LM324 que actúa como comparador; la salida es baja si hay luz, y alta si hay sombra.

El circuito sigue con un chip NE555 monostable que genera un pulso cada vez que cambia la salida del comparador, el cual actúa como interruptor que habilita temporalmente el oscilador del siguiente chip NE555 astable.

Seguido por un contador 4017, cada salida alta enciende un LED en secuencia. Cada vez que se detecta sombra &rarr; se genera un pulso &rarr; el contador avanza &rarr; un LED se enciende.

## PCB en Kicad (1 punto)

![PCB general](./imagenes/pcb_general_bw.png)

![PCB general](./imagenes/pcb_general.png)

![PCB detalles](./imagenes/pcb_detalle01.png)

![PCB detalles](./imagenes/pcb_detalle02.png)

![PCB detalles](./imagenes/pcb_detalle03.png)

![PCB 3D](./imagenes/pcb_3d.png)

![PCB 3D](./imagenes/pcb_3d_perspectiva.png)

## Recursos adicionales

## Bibliografía
