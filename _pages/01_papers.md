---
layout: page
title: Working Papers
permalink: /papers/
---

{% assign items = site.categories.papers | sort: 'date' %}
{% for post in items reversed %}
<div class="entry">
	<div class="entry-year">{% if post.year and post.year != "" %}{{ post.year }}{% else %}{{ post.date | date: "%Y" }}{% endif %}</div>
	<div>
		<a class="entry-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
		<p class="entry-meta">
			{% if post.status %}{{ post.status }}{% endif %}
			{% if post.authors != site.name %}
				{% assign and_name = site.name | append: ' and' %}
				{% assign name_and = 'and ' | append: site.name %}
				{% if post.status %}&middot;{% endif %}
				{{ post.authors | strip_newlines | remove: name_and | remove: and_name | prepend: 'with ' }}
			{% endif %}
		</p>
	</div>
</div>
{% endfor %}
