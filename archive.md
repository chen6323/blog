---
layout: page
title: 文章
permalink: /archive/
---

{% assign dates = site.posts | group_by_exp: "post", "post.date | date: '%Y-%m'" %}

{% for group in dates %}

<h2 id="{{ group.name }}">{{ group.name }}</h2>

{% for post in group.items %}

<p>
  <a href="{{ post.url | relative_url }}">
    {{ post.date | date: "%Y-%m-%d" }}　{{ post.title }}
  </a>
</p>

{% endfor %}

{% endfor %}
