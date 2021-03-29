---
title: misc
description: その他雑多な記事を集めてます
---

## misc

| TITLE | CATEGORY |
|:--|:--|{% for page in site.pages %}{% if page.dir contains '/misc/' and page.name != 'index.md' %}
| <a href="{{ page.url }}">{{ page.title }}</a> | {{ page.dir }} | {% endif %}{% endfor %}
