---
title:
layout: default
permalink: /projects/
published: true
---

<div class="article-list">
  {% assign sorted_projects = site.projects | sort: 'date' | reverse %}
  {% for project in sorted_projects %}
    <h3><a href="{{ project.url | prepend: site.baseurl }}">{{ project.title }}</a></h3>
    <p>{{ project.description }}</p>
  {% endfor %}
</div>