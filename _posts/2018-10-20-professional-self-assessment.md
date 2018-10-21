---
layout: post
title:  "Professional Self-Assessment"
date:   2018-10-08
excerpt: "CS499 Professional Self-Assessment Posts"
project: true
---

{% assign this_word = "Professional Self-Assessment" %}

These are all the blog posts pertaining to the Professional Self-Assessment component of the CS499 Course Portfolio.

<article>
	<ul>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
        <li class="entry-title"><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a> posted {{ post.date | date_to_string }} </li>
    {% endif %}{% endfor %}
	</ul>
</article><!-- /.hentry -->
