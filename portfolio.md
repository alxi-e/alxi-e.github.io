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

<style>
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
    padding: 20px 0;
  }

  .portfolio-card {
    position: relative;
    display: block;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid #ddd;
    aspect-ratio: 16 / 10;
    text-decoration: none !important;
    transition: transform 0.3s ease;
  }

  .portfolio-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.15);
  }

  .portfolio-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }

  .card-overlay {
    position: absolute;
    bottom: 0;
    width: 100%;
    background: linear-gradient(to top, rgba(0,0,0,0.8) 0%, rgba(0,0,0,0) 100%);
    padding: 30px 15px 15px;
    color: white !important;
  }

  .card-overlay h3 {
    margin: 0;
    font-family: 'Raleway', sans-serif !important;
    font-size: 1.2rem;
    color: white !important;
  }

  .card-overlay p {
    margin: 5px 0 0;
    font-size: 0.85rem;
    color: #eee !important;
  }
</style>
