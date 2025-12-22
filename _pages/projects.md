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
{% if site.data.repositories.github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% else %}
<p>No repositories configured. Add your GitHub repositories to <code>_data/repositories.yml</code>.</p>
{% endif %}
</div>
