# BlockyPenguin Blog

{% assign doclist = site.pages | sort: 'date' %}
{% assign root = page.dir %}
{% assign baseurl = site.baseurl | append: '/' %}

{% capture tree %}
  {% for doc in doclist %}
    {% if doc.name contains '.md' %}
      {% assign parts = doc.url | split: '/' %}
      {% if parts[0] == root or (parts | size > 1 and parts[1] == root) %}
        {% assign level = parts | size %}
        {% assign indent = level | minus: 2 %}
        {% assign padding = '' | append: '&nbsp;&nbsp;&nbsp;&nbsp;' | times: indent %}
        {{ padding }}- <a href="{{ baseurl }}{{ doc.url }}">{{ doc.title }}</a><br>
      {% endif %}
    {% endif %}
  {% endfor %}
{% endcapture %}

{{ tree | newline_to_br }}