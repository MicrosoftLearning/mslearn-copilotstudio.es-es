---
title: Instrucciones hospedadas en línea
permalink: index.html
layout: home
---

# Ejercicios de Copilot Studio

A continuación se enumeran los vínculos a los ejercicios de Copilot Studio de Microsoft Learn.

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %} {% for activity in labs  %}
- [{{ activity.lab.title }}]({{ site.github.url }}{{ activity.url }}) {% endfor %}
