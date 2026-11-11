---
share: true
layout: default
title: home
order: 1
---

<h2>Welcome!</h2>

<p>
This is my place to keep all my thoughts and various projects
organized and shareable. Creation is what makes us human and having an
audience, even an unseen and anonymous one, helps motivate me to keep
making things. Poke around, read the
<a href="{% link about.md %}">about page</a>.
   If you like something or want to know more, feel free to
reach out.
</p>

<h3>Game Weekend!!!</h3>

<p>
 Here some quick links to game selection spinners: <br>
 
 <a href="https://missingdice.com/spin-the-wheel/?values=Age%20of%20Mythology+Among%20Us+Hoard+Killing%20Floor%202+Last%20Train%20Outta%20Wormtown+Lort+Obilteracers+Peak+Rocket%20League+Strange%20Brigade+Super%20Battle%20Golf+Tanks%20the%20Crusade+Total%20War%20Warhammer%203+Albion+Beyond%20All%20Reason+Call%20of%20Duty%202+Counter%20Strike+Dota%202+Isonzo+Starship%20Troopers%20Extermination">All games</a><br>

<a href="https://missingdice.com/spin-the-wheel/?values=Among%20Us+Hoard+Obilteracers+Rocket%20League+Super%20Battle%20Golf+Tanks%20the%20Crusade+Albion+Call%20of%20Duty%202+Counter%20Strike+Isonzo">Shorter games</a><br>
</p>

<h3>Thought of the Day</h3>

{% assign daily = site.posts | where: "categories", "daily-thought" | first %}
<p>
{{ daily.excerpt }}
</p>

<p>
For previous daily thoughts
<a href="{% link _posts/2026-04-08-daily-blog.md %}">click here</a>.
</p>

<h3>Featured Post</h3>

{% assign featured_post = site.posts | where: "title", "Have a Good Wallet" | first %}
<p>
<a href="{{ featured_post.url }}">{{ featured_post.title }}</a>
<span class="postDate">{{ featured_post.date | date: "%Y-%m-%d" }}. </span> <br>
{{ featured_post.excerpt | strip_html }}
</p>

<h3>Latest Posts:</h3>

{% for post in site.posts limit:5 %}
  {% unless post.path == "_posts/2026-04-08-daily-blog.md" %}
  <p>
  <a href="{{ post.url }}">{{ post.title }}</a>
  <span class="postDate">{{ post.date | date: "%Y-%m-%d" }}.</span> <br>
  {{ post.excerpt | strip_html }}
  </p>
  {% endunless %}
{% endfor %}
