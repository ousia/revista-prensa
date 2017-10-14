---
tab: none
layout: page
---

De vez en cuando me encuentro con asuntos de prensa que quiero hacer notar.

Este sitio es una reunión de esos comentarios, más o menos ocasionales.

Aquí está la lista:

{% assign default_paths = site.pages | map: "path" %}
{% assign page_paths = site.header_pages | default: default_paths %}

{% if page_paths %}
  {% for path in page_paths %}
    {% assign my_page = site.pages | where: "path", path | first %}
    {% if my_page.tab == "none" %}
        {% if my_page.title != "Nada" %}
            {% if my_page.permalink != "/404.html" %}
                {% if my_page.path != "404.md" %}
* [{{ my_page.label | default: my_page.title }}]({{ my_page.url | relative_url }}) (test: {{ my_page.path }})
                {% endif %}
            {% endif %}
        {% endif %}
    {% endif %}
  {% endfor %}
{% endif %}
