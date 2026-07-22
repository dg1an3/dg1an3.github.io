---
layout: default
title: Blog
---

# Blog

Imported from [dg1an3](http://www.dg1an3.net) — {{ site.time | date: "%Y" }}.

<ul>
{% assign entries = site.pages | where_exp: "p", "p.date" | sort: "date" | reverse %}
{% for p in entries %}
  {% if p.dir == "/blog/" %}
  <li>
    <strong>{{ p.date | date: "%Y-%m-%d" }}</strong> —
    <a href="{{ p.url | relative_url }}">{{ p.title }}</a>
  </li>
  {% endif %}
{% endfor %}
</ul>
