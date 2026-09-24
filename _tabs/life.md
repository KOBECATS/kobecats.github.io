---
layout: page
icon: fas fa-house
order: 3
title: Life / 生活
---

{% assign life_posts = site.categories["Life"] %}
{% assign all_tags = "" | split: "" %}
{% for post in life_posts %}
  {% for tag in post.tags %}
    {% unless all_tags contains tag %}
      {% assign all_tags = all_tags | push: tag %}
    {% endunless %}
  {% endfor %}
{% endfor %}

{% for tag in all_tags %}
### {{ tag }}

<ul>
{% for post in life_posts %}
  {% if post.tags contains tag %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="color: gray;">({{ post.date | date: "%Y-%m-%d" }})</span>
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}
