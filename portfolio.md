---
layout: page
title: Portfolio
permalink: /portfolio/
---
### Portfolio

{% for project in site.portfolio %}
### [{{ project.title }}]({{ project.url | relative_url }})
![{{ project.title }}]({{ project.image | relative_url }})
{% endfor %}
