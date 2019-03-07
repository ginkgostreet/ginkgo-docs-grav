---
title: Features
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /features/information-architecture/solution/features
---
# Feature Information Architecture

## Folder Structure

- Context (Required)
- Discussion
- Resolution
- Solution (Required)
- Release (Required once deployed)

More information in the [Feature Feature](/features/feature).

## Folder Structure in Roadmap
``` shell
roadmap
└── whiz-bang
    └── v0.2
        └── 00.context
```

## Folder Structure in Manifest
``` shell
├── 00.context
├── 01.discussion
├── 02.resolution
├── 03.solution
└── 04.release
    ├── docs.md		<--- required by Grav, can be empty
    ├── v0.1 		<--- Complete copy of the feature as of the first deployment
    │   ├── 00.context
    │   ├── 01.discussion
    │   ├── 02resolutiony
    │   ├── 03.solution
    │   └── 04.release
    │       └── docs.md
    ├── v0.2		<--- Development phase making minor changes (sparsely populated)
    │   ├── 00.context	<--- describes scope of changes, not a full feature
    │   ├── 03.solution	<--- describes changes to the feature, not full feature
    │   └── 04.release
    │       └── docs.md
    └── v0.3
        └── docs.md		<--- only has release notes because this is the current release

```
