---
layout: page
title: TechNudge
title_section:
  first: Tech
  second: Nudge
tagline: A few learning from the software engineering side of my world
---
{% include JB/setup %}

## Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span class='font-mono'>{{ post.date | date_to_string }}</span> -- <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

## About
This blog is my attempt to document my learnings as a software engineer .. well at least i'm hoping its about that, we'll see :)
