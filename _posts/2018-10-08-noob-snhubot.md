---
layout: post
title:  "Noob SNHUbot Enhancement Project"
date:   2018-10-08
excerpt: "CS499 Enhancement Artifacts"
project: true
tag:
- Noob SNHUbot
---

{% assign this_word = "Noob SNHUbot" %}

<article>
    <h2 id="{{ this_word }}" class="tag-heading">{{ this_word }}</h2>    
    | Date | Title | Excerpt |
    |:--------|:-------:|--------:|
    {% for post in site.tags[this_word] %}{% if post.title != null %}
    | {{ post.date }} | <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a> | {{ post.excerpt }} |
    {% endif %}{% endfor %}
</article><!-- /.hentry -->
