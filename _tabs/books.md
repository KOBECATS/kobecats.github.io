---
layout: page
icon: fas fa-book
order: 2
title: Bookshelf / 書棚
---

{% assign book_posts = site.categories["Books"] %}
{% assign all_tags = "" | split: "" %}
{% for post in book_posts %}
  {% for tag in post.tags %}
    {% unless all_tags contains tag %}
      {% assign all_tags = all_tags | push: tag %}
    {% endunless %}
  {% endfor %}
{% endfor %}

{% for tag in all_tags %}
### {{ tag }}

<ul>
{% for post in book_posts %}
  {% if post.tags contains tag %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="color: gray;">({{ post.date | date: "%Y-%m-%d" }})</span>
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}
