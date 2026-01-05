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
  /* 1. GRID SETUP */
  .portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 30px;
    padding: 20px 0;
  }

  /* 2. THE CARD */
  .portfolio-card {
    position: relative;
    height: 280px;
    border-radius: 15px;
    overflow: hidden;
    cursor: pointer;
    box-shadow: 0 10px 30px rgba(0,0,0,0.4);
    display: block;
    text-decoration: none !important;
    background: #000;
  }

  /* 3. IMAGE FOCUS EFFECT */
  .portfolio-card img { 
    width: 100%;
    height: 100%;
    object-fit: cover; 
    transition: filter 0.5s ease, transform 0.5s ease;
    /* Default: Blurry and slightly dark */
    filter: blur(8px) brightness(0.7); 
  }

  /* When hovering, clear the blur and zoom slightly */
  .portfolio-card:hover img {
    filter: blur(0px) brightness(1);
    transform: scale(1.05);
  }

  /* 4. FLOATING GLASS BOX */
  .card-overlay {
    position: absolute;
    bottom: 20px;
    left: 20px;
    right: 20px;
    padding: 15px;
    border-radius: 10px;
    
    /* Glassmorphism */
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    
    color: white !important;
    z-index: 2;
    transition: all 0.3s ease;
  }

  /* Lift the box slightly on hover */
  .portfolio-card:hover .card-overlay {
    background: rgba(255, 255, 255, 0.2);
    transform: translateY(-5px);
    border: 1px solid rgba(255, 255, 255, 0.4);
  }

  /* 5. TEXT STYLING */
  .card-overlay h3 { 
    margin: 0 !important; 
    font-size: 1.2rem !important; 
    font-family: 'Raleway', sans-serif !important;
    font-weight: 700 !important;
    color: white !important;
    text-shadow: 0 2px 4px rgba(0,0,0,0.3);
  }

  .card-overlay p { 
    margin: 4px 0 0 !important; 
    font-size: 0.85rem !important; 
    opacity: 0.9 !important; 
    color: white !important;
    text-shadow: 0 2px 4px rgba(0,0,0,0.3);
  }
</style>
