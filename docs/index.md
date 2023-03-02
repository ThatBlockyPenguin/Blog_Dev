# Home | BlockyPenguin's Blog

{% assign doclist = site.pages | sort: 'date' %}

<ul>
  {% for doc in doclist %}
    {% if doc.path contains 'article/' %}
      <li><a href="{{ doc.url }}">{{ doc.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>