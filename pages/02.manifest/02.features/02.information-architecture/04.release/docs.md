---
title: Releases
taxonomy:
  category: 
    - docs
  tag:
    - content
    - top
routes:
  canonical: /features/information-architecture/releases
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Releases

{% for p in page.collection %}
### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}