# BlockyPenguin Blog

{% assign doclist = site.pages | sort: 'date' %}
{% assign root = page.dir %}
<ul>
{% for doc in doclist %}
  {% if doc.name contains '.md' %}
    {% assign parts = doc.url | split: '/' %}
    {% if parts[0] == root or (parts | size > 1 and parts[1] == root) %}
      {% assign level = parts | size %}
      {% assign indent = level | minus: 1 %}
      {% capture padding %}{% for i in (1..indent) %}&nbsp;&nbsp;&nbsp;&nbsp;{% endfor %}{% endcapture %}
      <li><a href="{{ site.baseurl }}{{ doc.url }}">{{ padding }}{{ doc.title }}</a></li>
    {% endif %}
  {% endif %}
{% endfor %}
</ul>