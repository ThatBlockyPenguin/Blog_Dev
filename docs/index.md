# BlockyPenguin Blog

{% assign doclist = site.pages | sort: 'date' %}

<ul>
  {% for doc in doclist %}
    {% if doc.name contains '.md' %}
      {% if page.url == doc.url %}
        {% continue %}
      {% endif %}
      
      {% assign url = doc.url %}
      {% if doc.url contains '.html' %}
        {% assign url = url | split: '.' | slice: 0 %}
      {% endif %}
      
      <li><a href="{{ site.baseurl }}{{ url }}" target="_blank">{{ doc.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>
