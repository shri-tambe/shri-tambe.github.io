---
layout: default
title: Blog — Shrikant Tambe
---

# Blog

<ul class="post-list">
{% for post in site.posts %}
<li>
<span class="date">{{ post.date | date: "%B %d, %Y" }}</span><br>
<a class="title" href="{{ post.url }}">{{ post.title }}</a>
</li>
{% endfor %}
</ul>
