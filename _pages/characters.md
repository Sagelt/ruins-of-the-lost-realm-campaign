---
layout: page
title: Characters
id: characters
permalink: /collections/characters
---

{% assign characters = site.entries | where_exp: "entry", "entry.path contains 'characters'" | sort_natural: "name" %}

{% for character in characters %}
  <h1><a class="internal-link" href="{{character.url}}">{{character.name}}</a></h1>
  <p>{{character.content | strip_html | remove: "[" | remove: "]" | truncatewords: 20}}</p>
{% endfor %}