---
layout: page
title: Publications
permalink: /pubs/
---

{% assign items = site.categories.pub | sort: date | sort: 'year' %}
{% for post in items reversed %}
<div class="entry">
	<div class="entry-year">{% if post.year == "Forthcoming" %}Forthc.{% else %}{{ post.year }}{% endif %}</div>
	<div>
		<a class="entry-title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
		<p class="entry-meta">
			{% if post.type == "article" %}
				<i>{{ post.journal }}{% if post.volume != empty %} {{ post.volume }}{% endif %}</i>{% if post.number != empty %}({{ post.number }}){% endif %}{% if post.pages != empty %}, {{ post.pages }}{% endif %}
			{% endif %}
			{% if post.type == "incollection" %}
				In: {{ post.editor }}, eds. <i>{{ post.booktitle }}</i>. {{ post.publisher }}
			{% endif %}
			{% if post.authors != site.name %}
				{% assign and_name = site.name | append: ' and' %}
				{% assign name_and = 'and ' | append: site.name %}
				&middot; {{ post.authors | strip_newlines | remove: name_and | remove: and_name | prepend: 'with ' }}
			{% endif %}
		</p>
	</div>
</div>
{% endfor %}
