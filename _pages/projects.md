---
layout: page
title: Projects
permalink: /projects/
description: A collection of my GitHub repositories and projects.
nav: true
nav_order: 3
---

<!-- pages/projects.md -->
<div class="projects">
{% if site.data.repositories.github_repos or site.data.projects %}

{% if site.data.repositories.github_repos %}
## GitHub Repositories

<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 mb-5">
  {% for repo in site.data.repositories.github_repos %}
  <div class="col">
    {% include repository/repo.liquid repository=repo %}
  </div>
  {% endfor %}
</div>
{% endif %}

{% if site.data.projects %}
## Reports & Projects

<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
  {% for project in site.data.projects %}
    {% include project_card.liquid project=project %}
  {% endfor %}
</div>
{% endif %}

{% else %}
<p>No projects configured. Add your GitHub repositories to <code>_data/repositories.yml</code> and custom projects to <code>_data/projects.yml</code>.</p>
{% endif %}
</div>
