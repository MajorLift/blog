---
layout: default
---

<header class="site-header">
<h1><a href="{{ '/' | relative_url }}">Jongsun Suh</a></h1>
<p>Essays on oversight, agents, and delegation.</p>
</header>

<ul class="post-list">
{% for post in site.posts %}{% unless post.categories contains 'criticism' %}
<li>
<time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
<a href="{{ post.url | relative_url }}">{{ post.title }}</a>
</li>
{% endunless %}{% endfor %}
</ul>

<p><a href="{{ '/criticism/' | relative_url }}">criticism &rarr;</a> &middot; <a href="{{ '/papers/' | relative_url }}">papers &rarr;</a></p>
