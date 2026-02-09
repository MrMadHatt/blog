---
layout: default
title: Posts
---

## All Posts

{% for post in site.posts %}
  <article class="post-item">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
    <p>{{ post.excerpt }}</p>
  </article>
{% endfor %}