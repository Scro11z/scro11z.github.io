---
layout: page
title: Categories
permalink: /categories/
---
<div>
  {% for category in site.categories %}
    <h3>
      {% if category[0] == 'hackerrank' %}
        HackerRank
      {% else %}
        {{ category[0] | capitalize }}
      {% endfor %}
    </h3>
    <ul>
      {% for post in category[1] %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
  {% endfor %}
  {% endif %}
</div>
