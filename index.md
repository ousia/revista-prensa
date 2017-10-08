---
tab: none
layout: page
---

De vez en cuando me encuentro con asuntos de prensa que quiero hacer notar.

Este sitio es una reunión de esos comentarios, más o menos ocasionales.

Aquí está la lista:

  {% for path in page_paths %}
    {% assign my_page = site.pages | where: "path", path | first %}
    {% if my_page.tab == "none" %} {% else %}{% if my_page.title %}
    * <a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.label | default: my_page.title }}</a>
    {% endif %}{% endif %}
  {% endfor %}

