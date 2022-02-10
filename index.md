---
title: 'Brian Artschwager'
---

Senior Systems Engineer on the IT Team at Stack Overflow.

<h2>Posts</h2>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }} <small>({{ post.date | date: '%B %d, %Y' }})</small></a>
    </li>
  {% endfor %}
</ul>

---
Disclaimers:

Any opinions expressed are solely my own and do not express the views or opinions of my employer.
