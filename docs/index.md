# Pages Demo
Hello

<!-- Dynamic Sidebar -->

{% for page in site.pages %}
  {% if page.url != "/404.html" %}
    {% assign segments = page.url | split: '/' %}
    {% if segments.size > 1 %}
      {% assign depth = segments.size | minus: 2 %}
      {% assign indent = depth | times: 2 %}
      {% assign padding = " " | times: indent %}
      {{ padding }}- [{{ page.title }}]({{ page.url | relative_url }})
    {% else %}
      - [{{ page.title }}]({{ page.url | relative_url }})
    {% endif %}
  {% endif %}
{% endfor %}

<!-- End of Sidebar -->
