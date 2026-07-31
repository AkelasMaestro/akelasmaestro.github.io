---
share: true
layout: default
title: blog page
order: 3
---

<h2>Blog Posts</h2>

Opinion pieces, reviews, and other miscellaneous writings
all listed with the latest half-formed thought on top.
<!-- make a list of all the posts in the blog category -->
{% for post in site.categories.blog %}
  <p><a href="{{ post.url }}">{{ post.title }}</a>
  <span class="postDate">{{ post.date | date: "%Y-%m-%d" }}.</span> <br>
  {{ post.excerpt | strip_html }}
    </p>
{% endfor %}
