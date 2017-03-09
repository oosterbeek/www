---
layout: page
title: Working Papers
permalink: /papers/
---

<ul>
{% assign items = site.categories.papers | sort: 'date' %}
{% for post in items reversed %}
	<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
	{% if post.authors != site.name %}
	({{ post.authors | strip_newlines | remove: 'Edwin Leuven and' | remove: 'and Edwin Leuven' | prepend: 'with ' }})
	{% endif %}
	</li>
{% endfor %}
</ul>
