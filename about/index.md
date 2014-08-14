---
layout: page
title: About
permalink: /about/
---

Your current student officers are: 

{% comment %}

Using the data provided in '_data/officers.yaml' we can not only
generate a list of active officers, but also give their position,
personal website and more.

{% endcomment %}

<ul>
{% for officer in site.data.officers %}
	<li>{{ officer.name }} as {{ officer.position }}.
	{% if officer.site %}
		They have a personal website located here: <a href="{{ officer.site }}">{{ officer.site | truncate: 32 }}</a>.
	{% endif %}
	</li>
{% endfor %}
</ul>
