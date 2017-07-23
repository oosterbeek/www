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
		{% assign and_name = site.name | append: ' and' %}
		{% assign name_and = 'and ' | append : site.name %}
		({{ post.authors | strip_newlines | remove: name_and | remove: and_name | prepend: 'with ' }})
	{% endif %}
	</li>
{% endfor %}
</ul>
