---
title: Release
taxonomy:
  category: 
    - docs
  tag:
    - release
routes:
  canonical: /features/feature/release
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---
# Release

as of Mar 7, 2019, this is just lifted from the [initial brainstorm](/features/information-architecture/discussion/initial-brainstorm).

## Feature Lifecycle

1. New feature will start off as a Roadmap item under Architecture.
2. Articulate the context (i.e. users and stories).
3. Do some brainstorming to create possible solutions, questions to be answered, etc.
4. Perform technical discovery to answer questions, inform decisions, determine feasibility of proposed solutions, etc.
5. Draft solution(s) that implement the feature
6. All roles in the project review the proposed solutions and documentation to date, to ensure, validate, and verify that any concerns from all perspectives have been addressed. 

## New Releases

**Scenario #1:** A feature is in production for some time, the org evolves, they want to make changes…assuming this is a minor change, that would equate to a Minor Release. We would create a Feature for the Minor Release e.g. `myFeature_v1.1`.The contents of the Feature would address the development of the changes, referencing the deployed Feature as appropriate and not duplicating it.

When it comes time to deploy the Minor Release, the whole Feature is simply moved into the Root of the Deployed Feature. 

Bam.

**Scenario #2:** The change is not minor and constitutes a Major Release e.g. `myFeature_v2.0`. As with the Minor Release, avoiding duplication is the strategy. When it comes time to deploy, the Major Releases replaces the earlier version of the Feature but maintains the previous version as a child.

Double Bam.

## Releases of the Feature Feature

{% for p in page.collection %}

### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}