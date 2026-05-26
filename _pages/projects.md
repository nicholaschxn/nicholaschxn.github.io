---
title:
layout: default
permalink: /projects/
published: true
---

<div class="article-list">
  {% for project in site.projects %}
    <h2><a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">{{ project.title }}</a></h2>
    <p>{{ project.description }}</p>
    <hr/>
  {% endfor %}
</div>