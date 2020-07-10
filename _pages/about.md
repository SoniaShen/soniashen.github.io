---
layout: archive
permalink: /about/
title: "About"
---

<div class="tiles">
{% for post in site.categories.about %}
        {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

