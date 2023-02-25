# BlockyPenguin Blog

{% assign pages = site.pages | sort: 'date' %}

<ul>
  {% assign dirs = pages | map: 'dir' | uniq %}
  {% for dir in dirs %}
    {% assign parts = dir | split: '/' %}
    {% assign node = '' %}
    {% for part in parts %}
      {% assign node = node | append: '/' | append: part %}
      {% unless node == dir %}
        {% assign name = part | capitalize %}
        {% assign prev = node | remove_first: part | remove_first: '/' %}
        {% assign prev_node = site.baseurl | append: '/' | append: prev %}
        {% unless prev == '' %}
          <li><a href="{{ prev_node }}">{{ prev | capitalize }}</a></li>
        {% endunless %}
      {% endunless %}
    {% endfor %}
    <li><a href="{{ site.baseurl }}/{{ dir }}">{{ name }}</a></li>
    {% for page in pages %}
      {% if page.name contains '.md' and page.dir == dir %}
        <ul>
          <li><a href="{{ site.baseurl }}/{{ page.url }}">{{ page.title }}</a></li>
        </ul>
      {% endif %}
    {% endfor %}
  {% endfor %}
</ul>
