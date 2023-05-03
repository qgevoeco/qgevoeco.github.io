---
layout: home
permalink: /
title:
image:
  feature: shakyCmacBox.gif  
---

## About us

We are evolutionary ecologists seeking to explain how organisms adapt to their environments. The overarching question of our research is **how do natural selection and inheritance interact to shape phenotypes over time?** We study the factors within populations that generate among individual differences in highly conspicuous features of mating systems, life histories, and sexual dimorphisms. These features dynamically interact to determine the transmission of alleles between generations and to govern population demography. Thus, our research addresses fundamental questions in biology regarding how organisms mate, what maintains adaptive genetic variation, and how do populations respond to environmental change. 

Our group is committed to creating a successful and positive dynamic in which to further the group research goals with the highest scientific integrity. This involves being patient, careful, and detailed while respecting people's time, opinions, contributions, and backgrounds. We believe it is our shared responsibility to provide a welcoming space for all people to make scientific and academic advancements, to not tolerate speech or actions that are discriminatory, racist, or offensive, and to recognize our own biases and work to break down these and other barriers to inclusivity and equity in academia.

## Would you like to join the group?

See current announcements/opportunities in the [Opportunities section](./opportunities)
 

## Recent News
<div class="tiles">
{% for post in site.categories.news %}
      {% if forloop.index > 4 %}
          {% break %}
        {% endif %}
      {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

<div> 
  <br>
</div>

## Recent Posts

<div class="tiles">
{% for post in site.categories.posts %}
      {% if forloop.index > 4 %}
          {% break %}
        {% endif %}
      {% include post-list.html %}
{% endfor %}
</div><!-- /.tiles -->

