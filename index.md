---
title: 'Brian Artschwager'
---

<h2>Posts</h2>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }} <small>({{ page.date | date: '%B %d, %Y' }})</small></a>
    </li>
  {% endfor %}
</ul>