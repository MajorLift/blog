---
layout: default
---

<header class="site-header">
<h1><a href="{{ '/' | relative_url }}">Jongsun Suh</a></h1>
<p>Essays on oversight, agents, and delegation.</p>
</header>

<ul class="post-list">
{% for post in site.posts %}
<li>
<time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
<a href="{{ post.url | relative_url }}">{{ post.title }}</a>
</li>
{% endfor %}
</ul>
