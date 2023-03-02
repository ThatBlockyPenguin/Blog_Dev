# Home | BlockyPenguin's Blog

{% assign doclist = site.pages | sort: 'date' %}
{% assign root = page.dir %}
{% assign baseurl = site.baseurl | append: '/' %}

{% for doc in doclist %}
  {% if doc.path contains 'article/' %}
    {{ doc.path }}
    {{ doc.url }}

    <a href="{{ baseurl }}{{ doc.url }}">{{ doc.title }}</a><br>
  {% endif %}
{% endfor %}