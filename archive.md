---
layout: default
title: Archive
---

# Arşiv

Listelemeleri ay ve yıl olarak sınıflandırılmış bir şekilde burada bulabilirsiniz.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
