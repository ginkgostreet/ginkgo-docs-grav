---
title: Discussion
taxonomy:
  category: 
    - docs
  tag:
    - discussion
routes:
  canonical: /features/information-architecture/discussion
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Discussion

{% for p in page.collection %}
### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}

