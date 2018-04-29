---
date: 2018-03-10
linktitle: ¡Coyote time!
prev: /tutorials/mathjax
title: ¡Coyote time!
draft: true
tags: [
    "gamedev",
    "unity",
]
---

## ¿Que es el coyote time?
¿Recuerdas esos dibujos animados donde el personaje deja de estar sobre el suelo pero no cae de forma inmediata? 
![alt text](https://media.giphy.com/media/wPjJqp5iTzlsc/giphy.gif "Coyote time")

Pues esto es a lo que nos referimos con "Coyote Time", en honor a Willy E. Coyote.

Es un truco bastante util a la hora de realizar un juego de plataformas, podemos darle al jugador unos cuantos frames de gracia antes que la gravedad entre en acción, permitiendole saltar y llegar a una posición segura.

## ¿Como lo puedo implementar en mi juego?

Para usar el coyote time en nuestro juego, necesitamos un par de cosas:

- Conocer si el jugador esta en el suelo.
- Llevar un control de cuantos cuadros han pasado desde que el jugador dejo de estar en el suelo.

Pseudocódigo de la lógica necesaria:

```
si (jugador.estaEnElSuelo)
{
  ultimoFrame = frameActual;
  puedeSaltar = true;
}
de lo contrario si (jugador.noEstaEnElSuelo)
{
  if (frameActual - ultimoFrame > framesAEsperar)
  {
    puedeSaltar = false;
  }
}
```

## ¿Hey lo podria hacer en Unity?

¡Por supuesto! Vamos a realizar una simple implementación usando Colliders y RigidBodies

