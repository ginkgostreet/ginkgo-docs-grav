---
title: New File
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /features/information-architecture/solution/canonical-urls
---
# Canonical URLs and Organizing Folders

To ensure agility: documents should be able to be moved within the CMS without breaking references to the document. Setting a canonical URL in the frontmatter will provide a way to link to the document in a safe manner.

Canonical URLs should avoid unnecessary depth. This creates the opportunity for collisions, so canonical URLs should be validated with care.

## URL Components

* Prefix: `/features`
* Name: the name of the feature
* version: the semantic version of the feature. Optional if not slated for development yet and not an update to a feature.
* Component: `/context`, `/discussion`, `/resolution`, `/solution`, `/release`
* Document: (if needed) the unique name of the document.

**All URLs should be all-lowercase and not contain spaces or any characters other than a hyphen between words.**

## Example Cannonical URLs

* `/features/whiz-bang-concept` - a tentative name for a tentative feature
* `/features/whiz-bang/v0.1/context` - A single document describing the context of a feature that is under contract to be developed.
* `/features/whiz-bang/v0.2/discussion/abstracting-the-confabulator` - document capturing research into a modification of the deployed feature.