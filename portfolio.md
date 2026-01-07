---
layout: page
title: Portfolio
permalink: /portfolio/
---

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@600&display=swap" rel="stylesheet">

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
    grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
    gap: 30px;
    padding: 20px 0;
  }

  /* 2. THE CARD (16/10 Ratio) */
  .portfolio-card {
    position: relative;
    width: 100%;
    aspect-ratio: 16 / 10; /* Precise 16/10 format */
    border-radius: 12px;
    overflow: hidden;
    cursor: pointer;
    /* Lighter, subtle shadow */
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.08); 
    display: block;
    text-decoration: none !important;
    background: #1a1a1a;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .portfolio-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12); /* Slightly deeper on hover */
  }

  /* 3. IMAGE FOCUS EFFECT */
  .portfolio-card img { 
    width: 100%;
    height: 100%;
    object-fit: cover; 
    transition: filter 0.6s ease;
    filter: blur(6px) brightness(0.8); 
  }

  .portfolio-card:hover img {
    filter: blur(0px) brightness(1);
  }

  /* 4. LOWER FIFTH GLASS BAR */
  .card-overlay {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    /* Approximately 1/5th of the height */
    height: 22%; 
    padding: 0 20px;
    
    display: flex;
    flex-direction: column;
    justify-content: center;

    /* Blur + Darken Effect */
    background: rgba(0, 0, 0, 0.4); 
    backdrop-filter: blur(15px);
    -webkit-backdrop-filter: blur(15px);
    
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    z-index: 2;
    transition: background 0.3s ease;
  }

  .portfolio-card:hover .card-overlay {
    background: rgba(0, 0, 0, 0.6); /* Darkens further on hover */
  }

  /* 5. TYPOGRAPHY (Poppins) */
  .card-overlay h3 { 
    margin: 0 !important; 
    font-size: 1.1rem !important; 
    font-family: 'Poppins', sans-serif !important;
    font-weight: 600 !important;
    color: white !important;
    letter-spacing: -0.02em;
  }

  .card-overlay p { 
    margin: 2px 0 0 !important; 
    font-size: 0.8rem !important; 
    opacity: 0.8 !important; 
    color: #e0e0e0 !important;
    font-family: sans-serif;
  }
</style>
