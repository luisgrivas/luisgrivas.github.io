---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: ¡Hola!
---

Mi nombre es Luis Felipe, soy originario de [Monterrey, México](https://goo.gl/maps/i8RqWkuuvg3iry396). Estudié **matemáticas** en la universidad y realicé estudios de posgrado primero en **inteligencia artificial** y después en matemáticas en el área de **combinatoria y convexidad**. Actualmente trabajo como **científico de datos**. 

Aunque mis intereses son variados, puede decirse que estos se encuentran en la interesección de matemáticas y ciencias computacionales. 

En la industria he trabajado en distintos proyectos: sistemas de recomendación, modelos de pricing, predicción de deserción de clientes, construcción de portafolios, entre otros. 

Mi última publicación: {% for post in site.posts limit:1 %}  <a href="{{post.url | relative_url }}">{{ post.title | escape }}</a> {% endfor %}

<p style="color:white;">"in the beginner's mind there are many possibilities, but in the expert's mind there are few"</p>
