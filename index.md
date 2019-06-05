---
layout: home
permalink: /
title:
image:
  feature: 
---

## About us

TODO: who we are and what we do...


## Would you like to join the group?
### Future Undergraduate Members

If you are interested in volunteering in the lab please [e-mail me](mailto:terps@auburn.edu) a 3-5 sentence statement of your research interests, your CV/resume, and current (unofficial) GPA.


### Future Graduate Students and Postdocs

If you are interested in working on a fellowship application, I would be very happy to collaborate. Please [contact me](mailto:terps@auburn.edu).


## Recent News

<div class="tiles">
{% for post in site.categories.news %}
	{% include post-list.html %}
{% endfor %}
</div><!-- /.tiles -->


## Recent Posts

<div class="tiles">
{% for post in site.categories.articles %}
	{% include post-list.html %}
{% endfor %}
</div><!-- /.tiles -->

