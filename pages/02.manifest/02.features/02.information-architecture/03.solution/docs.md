---
title: Solution
taxonomy:
  category: 
    - docs
  tag:
    - Solution
routes:
  canonical: /features/information-architecture/solution
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Solution

{% for p in page.collection %}
### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}

