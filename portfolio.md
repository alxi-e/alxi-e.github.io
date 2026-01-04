---
layout: page
title: Portfolio
permalink: /portfolio/
---
### Portfolio

{% for project in site.portfolio %}
<a href="{{ project.url | relative_url }}">
  {% if project.image %}
  ![{{ project.title }}]({{ project.image | relative_url }})
  {% endif %}
  <p>{{ project.title }}</p>
</a>
{% endfor %}
