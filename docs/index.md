# Pages Demo
Hello

<!-- Dynamic Sidebar -->

{% assign depth = 0 %}
{% assign in_section = false %}

{% for page in site.pages %}
  {% if page.url != "/404.html" %}
    {% assign page_segments = page.url | split: '/' %}
    
    {% if page_segments.size > depth %}
      {% assign depth = page_segments.size %}
    {% endif %}
    
    {% if page_segments.size == 1 %}
      - [{{ page.title }}]({{ page.url }})
    {% else %}
      {% if in_section == false %}
        {% assign in_section = true %}
        - {{ page_segments[0] }}
      {% endif %}
      
      {% assign indent = page_segments.size | minus: depth | times: 2 %}
      {% assign padding = " " | times: indent %}
      {{ padding }}- [{{ page.title }}]({{ page.url }})
    {% endif %}
  {% endif %}
{% endfor %}

<!-- End of Sidebar -->