---
layout: page
title: Sessions
id: sessions
permalink: /collections/sessions
---

{% assign sessions = site.entries | where_exp: "entry", "entry.path contains 'sessions'" | sort_natural %}

{% for session in sessions %}
  {% assign file = session.path | split: "/" | slice: -1  %}
  {% assign session_date = file[0] | slice: 0,10 %}
  <h1><a class="internal-link" href="{{session.url}}">{{session.title}}</a></h1>
  <p>{{session.content | strip_html | remove: "[" | remove: "]" | truncatewords: 20}}</p>
{% endfor %}