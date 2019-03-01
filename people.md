---
layout: archive
permalink: /people/
title: "Meet the Group"
---

<div class="tiles">
{% for post in site.posts %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
