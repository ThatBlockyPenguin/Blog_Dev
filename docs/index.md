# Articles
{% include dev_status.html %}
{% assign doclist = site.pages | sort: 'date' %}

<ul>
  {% for doc in doclist %}
    {% if doc.path contains 'article/' %}
      <!-- TODO: Add category & brief preview -->
      <li><a href="{{ doc.url }}">{{ doc.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>