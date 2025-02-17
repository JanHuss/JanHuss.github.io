---
layout: page
title: Home
permalink: /
---
# Welcome to My Portfolio

Discover projects that blend innovative technology with creative storytelling—from advanced audio systems to transformative game experiences.

{% for project in site.data.projects %}
<div class="project">
  {% if forloop.index0 | modulo: 2 == 0 %}
    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
    <div class="project-content">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </div>
  {% else %}
    <div class="project-content">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </div>
    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
  {% endif %}
</div>
{% endfor %}

<div class="cta">
  <p>Interested in collaborating or learning more?</p>
  <a href="/contact">Contact Me</a>
</div>

<style>
  .project {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-bottom: 60px;
  }
  .project:nth-child(even) {
    flex-direction: row-reverse;
  }
  .project img {
    width: 300px;
    height: auto;
    border-radius: 8px;
  }
  .project-content {
    max-width: 600px;
  }
  .project-content h2 {
    margin-top: 0;
    font-size: 1.8em;
    color: #222;
  }
  .cta {
    text-align: center;
    padding: 40px 20px;
    background: #e0e0e0;
  }
  .cta a {
    display: inline-block;
    padding: 10px 20px;
    background: #333;
    color: #fff;
    text-decoration: none;
    border-radius: 4px;
    font-size: 1em;
  }
</style>
