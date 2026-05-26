---
title:
layout: default
permalink: /projects/
published: true
---

<div class="article-list">
  {% for project in site.projects %}
    <h3><a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">{{ project.title }}</a></h3>
    <p>{{ project.description }}</p>
  {% endfor %}
</div>