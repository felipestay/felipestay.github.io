---
layout: page
permalink: /media/
title: media
description: Press coverage, opinion columns, and interviews.
nav: true
nav_order: 5
pagination:
  enabled: true
---

<div class="post">

  <ul class="post-list">
    {% assign media_posts = site.posts | where: "category", "media" %}
    {% for post in site.posts %}
    <li>
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
      {% assign year = post.date | date: "%Y" %}

      <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% elsif post.redirect contains "://" %}
          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>
          <svg width="1rem" height="1rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        {% else %}
          <a class="post-title" href="{{ post.redirect | relative_url }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-meta">
        {{ read_time }} min read &nbsp; &middot; &nbsp;
        {{ post.date | date: "%B %-d, %Y" }}
      </p>
    </li>
    {% endfor %}
  </ul>

</div>
