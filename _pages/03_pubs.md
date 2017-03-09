---
layout: page
title: Publications
permalink: /pubs/
---

<ul>
{% assign items = site.categories.pub | sort: date | sort: 'year' %}
{% for post in items reversed %}
	<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>. 
		{% if post.type == "article" %}
			<i>
			{{post.journal}}
			{% if post.volume != empty %}
				{{post.volume}}
			{% endif %}
			</i>
			{% if post.number != empty %}
				({{post.number}}).
			{% endif %}
				({{post.year}}).
			{% if post.pages != empty %}
			 {{post.pages}}.
			{% endif %}
		{% endif %}
		{% if post.type == "incollection" %}
			In: {{post.editor}}, eds. <i>{{post.booktitle}}</i>. {{post.publisher}}. ({{post.year}}). 
		{% endif %}
		{% if post.authors != site.name %}
		 ({{ post.authors | strip_newlines | remove: 'Edwin Leuven and' | remove: 'and Edwin Leuven' | prepend: 'with ' }})
		{% endif %}
	 </li>
{% endfor %}
</ul>
