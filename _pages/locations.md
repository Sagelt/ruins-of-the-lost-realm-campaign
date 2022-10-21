---
layout: page
title: Locations
id: locations
permalink: /collections/locations
---

{% assign locations = site.entries | where_exp: "entry", "entry.path contains 'locations'" | sort_natural: "name" %}

{% for location in locations %}
  <h1><a class="internal-link" href="{{location.url}}">{{location.name}}</a></h1>
  <p>{{location.content | strip_html | remove: "[" | remove: "]" | truncatewords: 20}}</p>
{% endfor %}