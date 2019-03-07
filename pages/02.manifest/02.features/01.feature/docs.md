---
title: Feature
taxonomy:
  category: 
    - docs
  tag:
    - feature
routes:
  canonical: /features/feature
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Feature

A Feature is a functional unit that is a contract that ensures that stakeholders and collaborators of a product project share a common understanding. 

Features provide a common repository for all types of documentation. A Feature is created as the initial step of any project, and persists indefinitely, recording history, status, and comprehensive definitions.

See the article on [Features in the Information Architecture](/features/information-architecture/solution/features) for details of managing features in Labs.

Important information for using features is still located in the [initial brainstorm](/features/information-architecture/discussion/initial-brainstorm) doc.

Since this is the primordial feature, it does not follow the feature format. Each standard component of this feature instead contains documentation of what the component is. Whereas in any other Feature Implementation, such documentation herein would be contained within the Solution folder. 

## Technical Solution

* markdown: all documents are composed in [Git-Hub-Flavored Markdown](https://github.github.com/gfm/) to support portability, flexible display (e.g. desktop and mobile), and version control systems.
* Grav, file-based Content Management System.
* YAML front-matter and Grav Taxonomies

# Components of Features

{% for p in page.collection %}

### [{{ p.title }}]({{ p.url }})

{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}

