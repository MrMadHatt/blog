---
layout: default
title: Archive
---

<style>
  .archive {
    font-family: "SFMono-Regular", Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
    color: #b5e853;
  }

  .archive-year {
    margin-top: 2rem;
    font-size: 1.5rem;
    color: #00ff00;
  }

  .archive-list {
    list-style: none;
    padding-left: 0;
    margin: 0.75rem 0 0;
  }

  .archive-item {
    display: flex;
    gap: 1rem;
    align-items: baseline;
    padding: 0.35rem 0;
    border-bottom: 1px solid #222;
  }

  .archive-date {
    color: #6adf65;
    min-width: 7.5rem;
  }

  .archive-link {
    color: #5dc4ff;
    text-decoration: none;
  }

  .archive-link:hover,
  .archive-link:focus-visible {
    color: #00ffee;
    text-decoration: underline;
  }
</style>

<section class="archive">
  {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
  {% for year in posts_by_year %}
    <h2 class="archive-year">{{ year.name }}</h2>
    <ul class="archive-list">
      {% for post in year.items %}
        <li class="archive-item">
          <span class="archive-date">{{ post.date | date: "%b %d" }}</span>
          <a class="archive-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  {% endfor %}
</section>
