---
title: Information Architecture
taxonomy:
  category: 
    - docs
  tag:
    - feature
routes:
  canonical: /features/information-architecture
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Lab Information Architecture

The essence of a Project Lab is it's information architecture. The Lab is the nexus of the project and provides all of the context -- past, present, and future -- for the future as well as how to find project resources such as servers, services, and personnel.

{% for p in page.collection %}
### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}