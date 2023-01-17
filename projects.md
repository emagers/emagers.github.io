---
layout: page
title: Projects
permalink: /projects/
---

{% for project in site.projects %}
  <h2>
    <a href="{{ project.url }}">
      {{ project.name }}
    </a>
  </h2>
  <p>{{ project.excerpt | markdownify }}</p>
{% endfor %}