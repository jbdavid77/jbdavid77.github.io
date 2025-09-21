---
layout: page
title: Blog
permalink: /blog/
regenerate: true
---
<ul>
 {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}

  {% for post in site.posts %}
    <li>
      {{ post.date | date: date_format }} <a href="{{ post.url  }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

