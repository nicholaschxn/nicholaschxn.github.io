---
title:
layout: default
permalink: /projects/
published: true
---

<div class="article-list">
{% for project in site.projects %}
  <div>
    <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
      <h2>{{ project.title }}</h2>
    </a>
    <p>{{ project.description }}</p>
    <hr/>
  </div>
{% endfor %}
</div>