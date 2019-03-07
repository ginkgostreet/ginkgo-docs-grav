---
title: Deployments
taxonomy:
  category: 
    - docs
  tag:
    - content
routes:
  canonical: /features/information-architecture/solution/deployments
---
# Deploying Features

Deploying a new feature is pretty straightforward. A feature should be readied for deployment by creating the Release Notes folder under `/release`, named for the semantic version. The entire feature can then be copied to the Manifest.

Subsequent releases will be more complex. If features are well decomposed from the beginning, most solutions should be adding and replacing features, and not modifying features. Meta or composite features are our prime-case for feature modifications and should therefore be easy to update because only the solution document with references to child features should change.

When updating a feature, the process is:

* **copy** everything (excluding `/release`) to the already existing folder for the prior-release, e.g. `/release/v0.1`.
* merge the new release feature documents to the old documents. This will mostly mean editing the Context and Solution documents.
* If URL collisions would occur, favor the new documents and update the cannonical URL's using the previous version number. Same for actual directories.

Finally, an entry should be made in the Manifest log of the deployment.

Since deployments involve merging feature documents, a staging of the feature updates is recommended.

