---
layout: page
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-grid">
  {% for item in site.portfolio %}
    <a class="portfolio-card" href="{{ item.url | relative_url }}">
      <img src="{{ item.image | relative_url }}" alt="{{ item.title }}">
      <div class="portfolio-title">{{ item.title }}</div>
    </a>
  {% endfor %}
</div>
