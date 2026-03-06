---
layout: page
permalink: /media/
title: media & news
description: Press coverage, interviews, opinion columns, and conference presentations.
nav: true
nav_order: 5
pagination:
  enabled: true
---

<div class="post">
  <ul class="post-list">
    {% for post in site.posts %}
    <li>
      <h3>
        <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">{{ post.date | date: "%B %Y" }}</p>
    </li>
    {% endfor %}
  </ul>
</div>
