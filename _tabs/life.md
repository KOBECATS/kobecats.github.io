---
layout: page
icon: fas fa-house
order: 3
title: Life / 生活
---

<ul>
{% for post in site.categories["Life"] %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span style="color: gray;">({{ post.date | date: "%Y-%m-%d" }})</span>
  </li>
{% endfor %}
</ul>
