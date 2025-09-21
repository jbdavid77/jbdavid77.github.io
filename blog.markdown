---
layout: page
title: Blog
permalink: /blog/
regenerate: true
---
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      {{ post.excerpt }}<a href="{{ post.url }}">.. more</a>
    </li>
  {% endfor %}
</ul>

