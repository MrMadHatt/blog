---
layout: default
title: Home
---

This is my workspace for sharing what I’m building, the lessons I’m learning, and the ideas I’m testing along the way.

---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
      <div class="post-excerpt">
        {{ post.excerpt }}
      </div>
      <a href="{{ post.url | relative_url }}" class="read-more">Read More →</a>
    </article>
  {% endfor %}
</div>