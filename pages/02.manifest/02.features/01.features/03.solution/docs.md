---
title: Solution
taxonomy:
  category: 
    - docs
  tag:
    - solution
routes:
  canonical: /features/features/solution
---
# Solution: Feature

This Feature is a bootstrapped implementation: providing both a description and an example in itself of a Ginkgo Street Project Lab Feature.

## Tools

- markdown: all documents are composed in [Git-Hub-Flavored Markdown](https://github.github.com/gfm/) to support portability, flexible display (e.g. desktop and mobile), and version control systems.
- Grav, file-based Content Management System.
- YAML front-matter and Grav Taxonomies

## Folder Structure

- Context (Required)
- Discussion
- Resolution
- Solution (Required)
- Release (Required once deployed)

See [terms in the Information Architecture](/features/information-architecture/context#terms) for definitions.

## Canonical URLs and Organizing Folders

To ensure agility: documents should be able to be moved within the CMS without breaking references to the document. Setting a cannonical URL in the frontmatter will provide a way to link to the document in a safe manner.

Cannonical URLs should avoid uncessary depth. This creates the opportunity for collisions, so cannonical URLs should be validated with care.

- Prefix: `/features`
- Name: the name of the feature
- version: the semantic version of the feature. Optional if not slated for development yet and not an update to a feature.
- Component: `/context`, `/discussion`, `/resolution`, `/solution`, `/release`
- Document: (if needed) the unique name of the document.

**All URLs should be all-lowercase and not contain spaces or any characters other than a hyphen between words.**

### Example Cannonical URLs
 - `/features/whiz-bang-concept` - a tentative name for a tentative feature
 - `/features/whiz-bang/v0.1/context` - A single document describing the context of a feature that is under contract to be developed.
 - `/features/whiz-bang/v0.2/discussion/abstracting-the-confabulator` - document capturing research into a modification of the deployed feature.

## Release Notes and Semantic Versioning
Release notes should use semantic versioning, (mostly) independent of code repository version numbers. Release notes should contain a release date at minnimum. It is acceptible, and even encouraged to not duplicate release notes of a code-base. Linking to the relevant release notes is therefore expected. 

It is not yet known what the best practice should be when a product reaches a new major version. Feature versions could be aligned with the product major version, or it might be better to not re-align feature versions when the product version is incremented. One proposal is to not ever re-name previous releases, but if a product version is incremented, any subsequent feature modifications would pick up the product major version. Therefore, we might have sequential feature releases such as: `v0.1, v0.2, v1.3, v4.4`.

### Deploying Features
Deploying a new feature is pretty straightforward. A feature should be readied for deployment by creating the Release Notes folder under `/release`, named for the semantic version. The entire feature can then be copied to the Manifest.

Subsequent releases will be more complex. If features are well decomposed from the beginning, most solutions should be adding and replacing features, and not modifying features. Meta or composite features are our prime-case for feature modifications and should therefore be easy to update because only the solution document with references to child features should change.

When updating a feature, the process is:
 - **copy** everything (excluding `/release`) to the already existing folder for the prior-release, e.g. `/release/v0.1`.
 - merge the new release feature documents to the old documents. This will mostly mean editing the Context and Solution documents.
 - If URL collisions would occur, favor the new documents and update the cannonical URL's using the previous version number. Same for actual directories.

Finally, an entry should be made in the Manifest log of the deployment.

Since deployments involve merging feature documents, a staging of the feature updates is recommended.

### Folder Structure in Roadmap
``` shell
roadmap
└── whiz-bang
    └── v0.2
        └── 00.context
```

### Folder Structure in Manifest
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
