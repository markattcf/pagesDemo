# Pages Demo
Hello

<!-- Dynamic Sidebar -->

{% for page in site.pages %}
  {% if page.url != "/404.html" %}
    {% assign page_segments = page.url | split: '/' %}
    {% if page_segments.size == 1 %}
      - [{{ page.title }}]({{ page.url }})
    {% else %}
      {% assign depth = page_segments.size | minus: 2 %}
      {% assign indent = depth | times: 2 %}
      {% assign padding = " " | times: indent %}
      {{ padding }}- [{{ page.title }}]({{ page.url }})
    {% endif %}
  {% endif %}
{% endfor %}

<!-- End of Sidebar -->