---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: ¡Hola!
---

Mi nombre es Luis González Rivas, soy egresado de la licenciatura en matemáticas de la UANL. Actualmente estoy inscrito en la [maestría en matemáticas](http://www.posgrado.unam.mx/matematicas/es/inicio) de la UNAM. Mi asesor es el [Dr. Luis Montejano](https://www.matem.unam.mx/fsd/luis). 

Estoy muy interesado en variedades de dimensiones bajas y su estudio mediante herramientas algebraicas. Anteriormente, trabajé en proyectos de machine learning aplicados a la industria: sistemas de recomendación, segmentación de clientes, pricing de productos, entre otros.

Mi última publicación en mi blog: {% for post in site.posts limit:1 %}  <a href="{{post.url | relative_url }}">{{ post.title | escape }}</a> {% endfor %}