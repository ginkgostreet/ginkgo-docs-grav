---
title: Release Versions
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /features/information-architecture/solution/release-versions
---
# Release Notes and Semantic Versioning

Release notes should use semantic versioning, (mostly) independent of code repository version numbers. Release notes should contain a release date at minnimum. It is acceptible, and even encouraged to not duplicate release notes of a code-base. Linking to the relevant release notes is therefore expected. 

It is not yet known what the best practice should be when a product reaches a new major version. Feature versions could be aligned with the product major version, or it might be better to not re-align feature versions when the product version is incremented. One proposal is to not ever re-name previous releases, but if a product version is incremented, any subsequent feature modifications would pick up the product major version. Therefore, we might have sequential feature releases such as: `v0.1, v0.2, v1.3, v4.4`.

### 