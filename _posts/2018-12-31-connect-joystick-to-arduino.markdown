---
title: "Conecta un joystick analógico a Arduino en 3 simples pasos"
layout: post
date: 2018-12-11 09:30
published: true
image: ../assets/posts/joystick_diagram.png
headerImage: true
tag:
- Arduino
- Arduino UNO
- Joystick
- Microcontroller
- Circuits
category: blog
author: rodferro
description: Conectando un joystick analógico a Arduino
---

En este breve post, te compartiré cómo conectar un joystick analógico a tu placa Arduino UNO en tres simples pasos. Para esto, necesitaremos:

- 1x Arduino UNO ([Link a Steren](https://www.steren.com.mx/placa-con-sistema-arduino-uno.html))
- 1x Joystick analógico para Arduino ([Link a Steren](https://www.steren.com.mx/joystick-para-arduino-y-microcontroladores.html))
- 5x Cables Dupont macho-hembra ([Link a Steren](https://www.steren.com.mx/juego-de-80-cables-tipo-dupont-de-15-cm-para-proyectos-arduino.html))

## 1. Sobre el joystick

El joystick analógico es similar a dos potenciómetros conectados entre sí, uno para el movimiento vertical (*eje Y*) y otro para el movimiento horizontal (*eje X*); también tiene un *switch* de selección.

<center>
  <img alt="Joystick analógico para Arduino" src="../assets/posts/joystick.jpg" width="50%">
</center>

El Arduino UNO o cualquier otra placa Arduino que use ATmega328 como microcontrolador tiene una resolución ADC de 10 bits. Por lo tanto, los valores en cada canal analógico pueden variar de `0` a `1023`. Al conectar el `VRx` a `A0` y `VRy` a `A1`, las entradas analógicas deben mostrar los valores como se muestra en la siguiente imagen.

<center>
  <img alt="Diagrama de movimiento para un joystick analógico" src="../assets/posts/joydiag.jpeg">
</center>

La posición inicial para el joystick es en `(x, y) = (511, 511)`. Si el stick se mueve en el *eje X* de un extremo al otro, los valores de `X` cambiarán de `0` a `1023` y sucederá algo similar cuando se mueva a lo largo del *eje Y*. De esta forma, se puede generar cualquier combinación de valores entre `0` y `1023` para cada coordenada.

## 2. Conectando el circuito

Ahora, sólo necesitaremos conectar el circuito como se muestra el siguiente diagrama:

<center>
  <img alt="Diagrama de conexión para un joystick analógico" src="../assets/posts/joystick_diagram.png">
</center>

Nota que las conexiones son como sigue a continuación:

<center>
  <table style="text-align:center;">
    <thead>
      <tr>
        <th>Arduino</th>
        <th></th>
        <th>Joystick</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><code>GND</code></td>
        <td>➡️</td>
        <td><code>GND</code></td>
      </tr>
      <tr>
        <td><code>5V</code></td>
        <td>➡️</td>
        <td><code>+5V</code></td>
      </tr>
      <tr>
        <td><code>A0</code></td>
        <td>➡️</td>
        <td><code>VRx</code></td>
      </tr>
      <tr>
        <td><code>A1</code></td>
        <td>➡️</td>
        <td><code>VRy</code></td>
      </tr>
      <tr>
        <td><code>2</code></td>
        <td>➡️</td>
        <td><code>SW</code></td>
      </tr>
    </tbody>
  </table>
</center>

## 3. Verifica y sube el código a tu Arduino

Una vez conectado el circuito, podemos compilar el código utilizando nuestro IDE de Arduino.

El código es el siguiente:

<script src="https://gist.github.com/RodolfoFerro/f71a37aa705518c3b00c586749b74a84.js"></script>

Asegúrate de conectar tu Arduino y escoger el puerto correcto, con esto, puedes verificar que el código compile correctamente y posterior a ello subirlo a tu Arduino...

#### ¡Listo!

Con esto podrás abrir la consola y verificar que se imprimen las posiciones `(xPosition, yPosition)` después de ser mapeadas a `(0, 255)`.

¿Notaste que no utilizamos el botón de *switch*? Como reto, ¿podrías definirlo en su respectivo puerto e imprimir su valor?

¡Cualquier cosa, te leo en los comentarios! 🤙🏼
