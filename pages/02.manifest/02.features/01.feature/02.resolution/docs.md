---
title: Resolutions
taxonomy:
  category: 
    - docs
  tag:
    - resolution
routes:
  canonical: /features/feature/resolution
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Resolution

Resolutions are the conclusions of [Discussions](/features/feature/discussion).

They should document both the decision and the justification for the decision.

A full-recap of the discussion should be avoided. 

Provide a link to the Discussion the Resolution addresses.

{% for p in page.collection %}

### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}

[About using the Roadmap](https://rtfm.ginkgo.st/~docs/grav/features/information-architecture/solution#roadmap)
