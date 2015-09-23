---
layout: page
title: "Scaps: Blog"
---

{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a> <small>{{ post.date | date: '%B %d, %Y' }}</small></h2>
  {{ post.excerpt }} <a href="{{ post.url }}">> read more</a>
{% endfor %}