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
    <table>
        <tr>
            <th>Posted</th>
            <th>Title</th>
            <th>Excerpt</th>
        </tr>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
        <tr>
            <td>{{ post.date | date_to_string }}</td>
            <td><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></td>
            <td>{{ post.excerpt }}</td>
        </tr>
    {% endif %}{% endfor %}
    </table>
