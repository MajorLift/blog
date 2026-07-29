---
layout: default
title: Criticism
permalink: /criticism/
---

<header class="site-header">
<h1>Criticism</h1>
<p>Film, literature, and music. Written for a reading group, mostly in Korean.</p>
</header>

<ul class="post-list">
{% for post in site.posts %}{% if post.categories contains 'criticism' %}
<li>
<time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
<a href="{{ post.url | relative_url }}">{{ post.title }}</a>
</li>
{% endif %}{% endfor %}
</ul>

<p><a href="{{ '/' | relative_url }}">&larr; essays</a></p>
