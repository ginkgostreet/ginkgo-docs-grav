---
title: Features
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /manifest/features
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Deployed Features

{% for p in page.collection %}
### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}
