---
layout: page
title: TechExtract
title_section:
  first: Tech
  second: Extract
tagline: A few learning from the software engineering side of my world
---
{% include JB/setup %}

## About
This blog is my attempt to document my learnings and findings as a software engineer .. well at least i'm hoping  its about that, we'll see :)

## Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
