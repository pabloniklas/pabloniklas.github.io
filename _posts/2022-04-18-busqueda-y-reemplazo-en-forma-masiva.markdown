---
layout: post
title:  "Busqueda y reemplazo en forma masiva"
date:   2022-04-18 22:19:23 -0300
categories: shell linux
---
Cuando quieren realizar una búsqueda y reemplazo masiva en archivos, el viejo PERL viene a darnos una mano.

```shell
perl -pi -e 's/<texto a reemplaza>/<texto de reemplazo>/' <archivo*>
```
