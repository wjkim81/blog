---
layout: default
title: Categories
permalink: /categories/
---

<h1>Categories</h1>

<ul>
  {% for category in site.categories %}
    <li>
      <a href="#{{ category[0] | slugify }}">{{ category[0] }} ({{ category[1].size }})</a>
    </li>
  {% endfor %}
</ul>

<hr>

{% for category in site.categories %}
  <h2 id="{{ category[0] | slugify }}">{{ category[0] }}</h2>
  <ul>
    {% for post in category[1] %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
