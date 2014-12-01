---
layout: default
title: Guides
use:
    - guides_parent_guide
---

# Parent Guides

<ul>
    {% for parent_guide,guides in data.guides_parent_guide %}
        <h4><li><a href="{{ site.url }}/guides/{{ parent_guide|url_encode(true) }}">{{ parent_guide }}</a></li></h4>
    {% endfor %}
</ul>