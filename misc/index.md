---
layout: index
title: misc
description: その他雑多な記事を集めてます
---

## misc

{% for page in site.pages %}
{% if page.dir == '/misc/' and page.name != 'index.md' %}
- <a href="{{ page.url }}">{{ page.title }}</a>
{% endif %}
{% endfor %}

