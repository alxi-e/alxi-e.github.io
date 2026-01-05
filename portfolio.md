---
layout: page
title: Portfolio
permalink: /portfolio/
---

<div class="portfolio-grid">
  {% for project in site.projects %}
  <a href="{{ project.url | relative_url }}" class="portfolio-card">
    <div class="card-image-container">
      <img src="{{ project.thumbnail | relative_url }}" alt="{{ project.title }}">
      <div class="card-overlay">
        <div class="card-text">
          <h3>{{ project.title }}</h3>
          <p>{{ project.subtitle }}</p>
        </div>
      </div>
    </div>
  </a>
  {% endfor %}
</div>
