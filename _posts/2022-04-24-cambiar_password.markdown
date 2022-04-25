---
layout: post
title:  "Procedimiento de blanqueo de password de root"
date:   2022-04-24 12:19:23 -0300
description: Como blanquear la password de root. # Add post description (optional)
img: recuperacion01.png
fig-caption: # Add figcaption (optional)
categories: linux
---

Puede pasar que nos olvidemos la clave de root. Si bien no podemos recuperarla, ya que los algoritmos de cifrado de password son one-way, hay una forma de poder ingresar al sistema operativo y cambiarla.

Para lograr dicho cometido, debemos seguir los siguientes pasos.

Iniciamos la PC. En ese momento se nos presenta el menú de GRUB

![Recup01]({{site.baseurl}}/assets/img/recuperacion01.png)

Parar la cuenta regresiva del GRUB presionando cualquier tecla. Editar la entrada de grub que usualmente booteamos al inicio.

![Recup02]({{site.baseurl}}/assets/img/recuperacion02.png)

Agregarle la entrada ```init=/bin/bash```.

![Recup03]({{site.baseurl}}/assets/img/recuperacion03.png)

Booteamos la entrada editada con ```F10``` o ```CTRL+x```:

![Recup04]({{site.baseurl}}/assets/img/recuperacion04.png)

Verificar el estado del filesystem ```/```, y veremos que está montado _Read Only_.

![Recup05]({{site.baseurl}}/assets/img/recuperacion05.png)

Debemos remontar el filesystem en modo _Read/Write_ y para poder cambiar la password, ya que sino no sería posibla a ```passwd```, escribir el archivo ```/etc/shadow```.

![Recup06]({{site.baseurl}}/assets/img/recuperacion06.png)

Luego escriban ```exit```. No deben asustarse por el _kernel panic_. Es natural dado que se reemplazo el proceso ```init``` por el shell que acabamos de terminar.
