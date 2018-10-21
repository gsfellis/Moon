---
layout: post
title:  "Noob SNHUbot Enhancement Project"
date:   2018-10-08
excerpt: "CS499 Enhancement Artifacts"
project: true
---

{% assign this_word = "Noob SNHUbot" %}

These are all of the blog posts pertaining to the Noob SNHUbot enhancement project for the CS499 course portfolio.

<article>
	<ul>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
        <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a> posted {{ post.date | date_to_string }} </li>
    {% endif %}{% endfor %}
	</ul>
</article><!-- /.hentry -->
