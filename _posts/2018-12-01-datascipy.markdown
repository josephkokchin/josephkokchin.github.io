---
title: "#PythonDayMX18: Data Science con SciPy"
layout: post
date: 2018-12-01 11:00
published: true
image: "https://github.com/RodolfoFerro/DataSciPy/blob/master/assets/DataSciPy.png?raw=true"
headerImage: false
tag:
- Python
- SciPy
- Talk
- Guadalajara
category: blog
author: rodferro
description: Simulación de datos a partir de muestras
# jemoji: '<img class="emoji" title=":ramen:" alt=":ramen:" src="https://assets.github.com/images/icons/emoji/unicode/1f35c.png" height="20" width="20" align="absmiddle">'
---

![DataSciPy](https://github.com/RodolfoFerro/DataSciPy/blob/master/assets/DataSciPy.png?raw=true)

Este 1 de diciembre se lleva a cabo el segundo día del PythonDayMX 2018 en CUCEA (UdeG), en Guadalajara; donde tuve la oportunidad de compartir la presente charla.

## Data Science con SciPy

En esta charla se ilustrará una técnica de ciencia de datos para estimar distribuciones probabilísticas de datos y con ello poder simular nuevos datos que sean válidos, aleatorios y se distribuyan de igual manera que los datos originales. Todo ello con el poder de SciPy.

La idea es que a partir de una muestra de datos (*variables aleatorias*) utilicemos `scipy.stats` para estimar la distribución de probabilidad, así como los parámetros de dicha distribución y con ello utilizar el [*Teorema de la Transformada Inversa*](https://es.wikipedia.org/wiki/M%C3%A9todo_de_la_transformada_inversa) para generar nuevas variables aleatorias con dicha distribución. De esta manera se generan nuevos datos aleatorios pertenecientes a la misma familia que los datos originales.

Para este taller necesitas conocimientos básicos sobre programación en Python. Parte de los objetivos es que posterior a la charla se cuente con una nueva técnica para generación de datos aleatorios bien distribuidos; con Python, obviamente.


<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vSBnIZlooCKP5_DTdHAyyOZCTU6DHaZFCBSel6GztrE04ymWYzJ0ll2gkLLRxCUfFo3frNbmsADobci/embed?start=false&loop=false&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

El repositorio del taller se encuentra en el siguiente enlace: [https://github.com/RodolfoFerro/DataSciPy/](https://github.com/RodolfoFerro/DataSciPy/)

Las transmisiones en vivo: [http://cucea.udg.mx/python-day-2018-live](http://cucea.udg.mx/python-day-2018-live)

Cualquier cosa, te leo en los comentarios.

¡Disfruta!
