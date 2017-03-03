---
layout: page
title: Working Papers
permalink: /papers/
---

<ul>
{% assign items = site.categories.papers | sort: 'date' %}
{% for post in items reversed %}
		<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> ({{post.authors}})</li>
{% endfor %}
</ul>
