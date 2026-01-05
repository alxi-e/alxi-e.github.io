---
layout: page
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-grid">
  {% for project in site.projects %}
    <a href="{{ project.url | relative_url }}" class="portfolio-card">
      <img src="{{ project.thumbnail | relative_url }}" alt="{{ project.title }}">
      <div class="card-overlay">
        <h3>{{ project.title }}</h3>
        <p>{{ project.subtitle }}</p>
      </div>
    </a>
  {% endfor %}
</div>
