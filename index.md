---
layout: default
title: 'Brian Artschwager'
---

Senior Systems Engineer on the IT Team at Stack Overflow.

<h1>Posts</h1>
{% for post in site.posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date: '%B %d, %Y' }})</small></h2>
  <p>{{ post.description }}</p>
{% endfor %}

---
Disclaimers:

Any opinions expressed are solely my own and do not express the views or opinions of my employer.
