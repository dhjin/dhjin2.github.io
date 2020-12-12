---
title: "Talks"
permalink: /talks/
author_profile: true
---
{% include base_path %}
  {% for post in site.categories.talks %}
    {% include archive-single.html %}
  {% endfor %}
