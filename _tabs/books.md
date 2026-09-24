---
layout: page
icon: fas fa-book
order: 2
title: Books / 読書
---

<ul>
{% for post in site.categories["Books"] %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="color: gray;">({{ post.date | date: "%Y-%m-%d" }})</span>
  </li>
{% endfor %}
</ul>
