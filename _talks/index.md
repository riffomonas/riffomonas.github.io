---
layout: default
category: index
title: Talks
---

## {{ page.title }}

{% for t in site.talks %}

{% if t.category != "index" %}
[{{ t.title }}]({{t.url}})
{% endif %}

{% endfor %}
