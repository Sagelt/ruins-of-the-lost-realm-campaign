---
layout: page
title: Items
id: items
permalink: /collections/items
---

{% assign items = site.entries | where_exp: "entry", "entry.path contains 'items'" | sort_natural: "name" %}

{% for item in items %}
  <h1><a class="internal-link" href="{{item.url}}">{{item.name}}</a></h1>
  <p>{{item.content | strip_html | remove: "[" | remove: "]" | truncatewords: 20}}</p>
{% endfor %}