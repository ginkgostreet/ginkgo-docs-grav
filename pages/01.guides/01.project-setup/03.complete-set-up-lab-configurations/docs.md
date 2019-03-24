---
title: Complete Set-up Lab Configurations
taxonomy:
  category:
    - docs
  tag:
    - content
    - guide
routes:
  canonical: /guides/project-setup/complete-set-up-lab-configurations
---
# Complete Set-up Lab Configurations

* Review site configuration - See [Roadmap: #More Default Configs](/roadmap/ginkgo-grav-install-profile) for suggestions:
* Configure Site Options
  * Site Title: e.g. "Museum of Math Knowledgebase"
  * Default Author: Ginkgo
  * Default Email: devs@ginkgostreet.com
* Initialize dev-environment config (on the server)
```shell
export PUBLIC_HTML=project-dir 
grav-util dev-env
export PROJ_LAB_REPO=git@github.com:/ginkgostreet/<project-repo>
grav-util project-lab-repo
```
You will have to override the `.gitignore` to commit the directory. After committing locally, use the git-sync in the Admin interface to push the changes.