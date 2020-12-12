---
title: "Research"
permalink: /research/
author_profile: true
---
<ul>
  {% for post in site.categories.research %}
    {% if post.url %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>
