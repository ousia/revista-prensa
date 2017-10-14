---
tab: none
layout: page
---

De vez en cuando me encuentro con asuntos de prensa que quiero hacer notar.

Este sitio es una reunión de esos comentarios, más o menos ocasionales.

Aquí está la lista:

<ul>
  {% for page in site.pages %}
    {% if page.resource == true %}
      {% for pc in page.categories %}
        {% if my_page.tab == "none" %}
          <li><a href="{{ page.url }}">{{ page.title }}</a></li>
        {% endif %}   <!-- cat-match-p -->
      {% endfor %}  <!-- page-category -->
    {% endif %}   <!-- resource-p -->
  {% endfor %}  <!-- page -->
</ul>

<ul>
  {% for page in site.pages %}
    {% if my_page.tab == "none" %}
            <li><p><a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.label | default: my_page.title }}</a></p></li>
    {% endif %} <!-- no-tab -->
  {% endfor %} <!-- page-paths -->
</ul>

<ul>
  {% for path in page_paths %}
    {% assign my_page = site.pages | where: "path", path | first %} <!-- assign mp -->
    {% if my_page.tab == "none" %}
        {% if my_page.title %}
        <li><p><a class="page-link" href="{{ my_page.url | relative_url }}">{{ my_page.label | default: my_page.title }}</a></p></li>
        {% endif %} <!-- page -->
    {% endif %} <!-- no-tab -->
  {% endfor %} <!-- page-paths -->
</ul>
