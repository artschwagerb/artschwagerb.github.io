---
layout: bootstrap
title: 'Brian Artschwager'
---

# Posts
{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date: '%B %d, %Y' }})</small></h2>
  <p>{{ post.description }}</p>
{% endfor %}
