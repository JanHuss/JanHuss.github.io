---
layout: page
title: Home
permalink: /
---

<div class="main-content">

  <!-- Main Sections That Fade In -->
  <div class="fade-in">
    <h2>About Me</h2>
    <p>
A look at some of my most exciting projects — where **game development**
meets **audio programming**.</p>
  </div>

  <!-- Projects -->
{% for project in site.data.projects %}
<div class="project fade-in">
  {% if forloop.index0 | modulo: 2 == 1 %}
    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
    <div class="project-content">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description | markdownify }}</p> <!-- Converts Markdown to HTML -->
    </div>
  {% else %}
    <div class="project-content">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description | markdownify }}</p>
    </div>
    <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
  {% endif %}
</div>
{% endfor %}

</div>

<style>
  .landing-hero {
  text-align: center;
  padding: 60px 20px;
  background: #f0f0f0;
}

/* Smooth fade-in effect */
.fade-in {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.8s ease-out, transform 0.8s ease-out;
}

/* Elements become visible */
.fade-in.visible {
  opacity: 1;
  transform: translateY(0);
}

/* Project Layout */
.project {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 60px;
  flex-wrap: wrap; /* Ensures proper wrapping on smaller screens */
}
.project:nth-child(odd) {
  flex-direction: row-reverse;
}
.project img {
  flex: 1; /* Allows the image to take a portion of available space */
  max-width: 25%; /* Keeps it at roughly 1/4 of the text space */
  height: auto;
  border-radius: 8px;
  min-width: 200px; /* Ensures images don’t shrink too much */
}
.project-content {
  flex: 3; /* Ensures text takes up 3/4 of the available space */
  max-width: 75%;
}

/* CTA Section */
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

}
</style>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const fadeElements = document.querySelectorAll(".fade-in");

    const fadeInOnScroll = () => {
      fadeElements.forEach((el) => {
        const rect = el.getBoundingClientRect();
        if (rect.top < window.innerHeight * 0.9 && rect.bottom > 0) {
          el.classList.add("visible");
        } else {
          el.classList.remove("visible");
        }
      });
    };

    fadeInOnScroll(); // Run on page load
    window.addEventListener("scroll", fadeInOnScroll);
  });
</script>
