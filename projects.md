---
share: true
layout: default
title: projects page
order: 4
---
<h2>Projects</h2>

This is where I keep notes and updates on ongoing, future, or forgotten
projects. This list is as much for me as it is for you. It acts as a sort
of repository of all my side interests. Notes, progress reports, what I
want to do next. The latest update will get moved to the top of the list.
<!-- Make a list of all the projects -->
{% for post in site.categories.projects %}
  <p><a href="{{ post.url }}">{{ post.title }}</a>
  <span class="postDate">{{ post.date | date: "%Y-%m-%d" }}.</span> <br>
  <!-- Add the first paragrah has a description -->
  {{ post.excerpt | strip_html }}
    </p>
{% endfor %}
