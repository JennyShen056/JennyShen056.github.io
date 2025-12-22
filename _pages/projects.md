---
layout: page
title: Projects
permalink: /projects/
description: A collection of my projects and research work.
nav: true
nav_order: 3
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.data.projects %}
  {% for project in site.data.projects %}
    <div class="project-item mb-4">
      <h3 class="mb-2">{{ project.title }}</h3>
      <p class="mb-2">{{ project.description }}</p>
      {% if project.link %}
        <a href="{{ project.link }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-outline-primary">
          {% if project.link_text %}{{ project.link_text }}{% else %}View Project{% endif %}
          <i class="fa-solid fa-external-link-alt ml-1"></i>
        </a>
      {% endif %}
    </div>
    {% unless forloop.last %}<hr>{% endunless %}
  {% endfor %}
{% else %}
  <p>No projects configured. Add your projects to <code>_data/projects.yml</code>.</p>
{% endif %}
</div>
