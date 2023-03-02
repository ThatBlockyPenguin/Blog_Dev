# Home | BlockyPenguin's Blog

{% assign doclist = site.pages | sort: 'date' %}
{% assign root = page.dir %}
{% assign baseurl = site.baseurl | append: '/' %}

{% for doc in doclist %}
  {{ doc.path }}
  {{ doc.url }}
  {% if doc.path contains '/article/' %}
    <a href="{{ baseurl }}{{ doc.url }}">{{ doc.title }}</a><br>
  {% endif %}
{% endfor %}