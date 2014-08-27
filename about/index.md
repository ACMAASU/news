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
		{% comment %}
			These filters remove the implied http/https and 'www.' from the URL. Then split it on the first slash, meaning it only retrieves the domain.
		{% endcomment %}
		Personal website: <a href="{{ officer.site }}">{{ officer.site | remove:'https://' | remove:'http://' | remove_first:'www.' | split:'/' | first }}</a>.
	{% endif %}
	</li>
{% endfor %}
</ul>
