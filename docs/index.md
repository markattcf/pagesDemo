# Pages Demo
Hello
[test](/)

<!-- Dynamic Sidebar -->

{% assign depth = 0 %}

{% for page in site.pages %}
  {% if page.url != "/404.html" %}
    {% assign page_segments = page.url | split: '/' %}
    {% if page_segments.size > depth %}
      {% assign depth = page_segments.size %}
    {% endif %}
    
    {% assign indent = page_segments.size | minus: depth | times: 2 %}
    {% assign padding = " " | times: indent %}
    [test](/)
    [{{ page.title }}]({{ page.url}})
  {% endif %}
{% endfor %}

<!-- End of Sidebar -->
