---
layout: post
title:  "Noob SNHUbot Enhancement Project"
date:   2018-10-08
excerpt: "CS499 Enhancement Artifacts"
project: true
---

{% assign this_word = "Noob SNHUbot" %}

<article>
	<h2 id="{{ this_word }}" class="tag-heading">{{ this_word }}</h2>
	<ul>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
        <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></li> posted {{ post.date | date_to_string }}
    {% endif %}{% endfor %}
	</ul>
</article><!-- /.hentry -->
