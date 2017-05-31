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
			{% assign and_name = site.name | append: ' and' %}
			{% assign name_and = 'and ' | append : site.name %}
			({{ post.authors | strip_newlines | remove: name_and | remove: and_name | prepend: 'with ' }})
		{% endif %}
	 </li>
{% endfor %}
</ul>
