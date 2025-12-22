---
layout: page
title: Projects
permalink: /projects/
description: A collection of my cool projects and research work.
nav: true
nav_order: 3
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.data.projects %}
  {% for project in site.data.projects %}
    <div class="project-item mb-4">
      <div class="row">
        {% if project.image %}
          <div class="col-md-3 col-sm-4 mb-3 mb-md-0">
            {% if project.image contains '://' %}
              <img src="{{ project.image }}" alt="{{ project.title }}" class="img-fluid rounded" style="width: 100%; max-width: 200px; height: 150px; object-fit: cover;">
            {% else %}
              {% assign image_path = project.image | prepend: '/assets/img/projects/' %}
              <img src="{{ image_path | relative_url }}" alt="{{ project.title }}" class="img-fluid rounded" style="width: 100%; max-width: 200px; height: 150px; object-fit: cover;">
            {% endif %}
          </div>
          <div class="col-md-9 col-sm-8">
        {% else %}
          <div class="col-12">
        {% endif %}
          <h4 class="mb-2" style="font-size: 1.1rem; font-weight: 600;">{{ project.title }}</h4>
          <p class="mb-2">{{ project.description }}</p>
          {% if project.link %}
            <a href="{{ project.link }}" target="_blank" rel="noopener noreferrer" class="btn btn-sm btn-outline-primary">
              {% if project.link_text %}{{ project.link_text }}{% else %}View Project{% endif %}
              <i class="fa-solid fa-external-link-alt ml-1"></i>
            </a>
          {% endif %}
        </div>
      </div>
    </div>
    {% unless forloop.last %}<hr>{% endunless %}
  {% endfor %}
{% else %}
  <p>No projects configured. Add your projects to <code>_data/projects.yml</code>.</p>
{% endif %}
</div>
