---
title: Solution
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /features/information-architecture/solution/solution
---
# Solution Documents

## Top-Level

* Guides
* Manifest
* Roadmap

## Guides

Step-by-Step how-to's. Conceptual introductions.

Best practice is to keep guides objective-focused. That is, don't create a guide that explains all of the things you can do with an interface, instead, create guides that match real-world workflows and assume general familiarity with the system. This will make guides more useful to beginners as well as advanced users and limit the changes needed as the solution evolves.

Conceptual or foundational guides are the exception but still should not be tightly bound to the solution interfaces which are likely to change in disorienting ways. Keep concept guides abstract.

A third kind of user documentation is "Reference Documentation." References can be third-party documents, especially for pre-existing tools that the solution builds upon, such as a WYSIWYG editor, or doing searches in Elastic Search, etc.

A single Reference document should be created in the Guides with links to third-party documentation as well as User Interface documentation contained in feature Solution documentation.

**For emphasis**: Comprehensive User Interface documentation is expected to be maintained in Features, especially meta and composite features that are built of several child features. This helps to ensure that documentation impacted by feature changes are updated.

## Manifest

The Manifest models the state of the Solution, in production, dev-ops, and development project lifecycle.

### Log

A sequential (descending) log of changes to the system: deployments and configuration changes.

### Resources

Manifest of resources comprising the system. Servers and accounts especially. **NO LOGIN CREDENTIALS**,  use a password safe.

### Features

[Features](/features/features/context) that have been deployed.

### Control

Project Control (aka Project Management).

Especially:

* Contracts
* Authorizations
* Change Orders
* Burn Tracking
* Timelines
* Project Journal
* Meeting Notes and Important Communications



## Roadmap

[Features](/features/features/context) in conception or under development. 



## Example

```shell
├── 00.guides
│   ├── 00.welcome
│   ├── 01.tutorial
│   ├── 02.refunds
│   ├── 03.tps-reports
│   └── 04.exports
├── 00.manifest
│   ├── 00.log
│   ├── 01.resources
│   ├── 02.features
│   └── 03.control
└── 00.roadmap
    ├── account-creation
    ├── advanced-search
    ├── interactive-map
    ├── payment-form
    ├── report-export
    ├── report-filter
    ├── report-graph
    └── report-scheduled-email
```