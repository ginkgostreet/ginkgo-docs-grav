---
title: 'Project Setup'
visible: true
---

## docs-user

Create a user and set-up the web-root, including permissions.

You can re-run the permissions with `docs-user facls`.

## grav-util

Create grav instances using the Ginkgo Street Labs template.

## Add the Dev Environment starter

TODO: make this mo-betta

Confirm env vars: `PUBLIC_HTML` `USER_NAME`

`make -f /usr/local/lib/grav-util/ginkgo-grav/Makefile dev-env`

## git-sync

- create a repo on github, initialized with a README.md
- create a personal access token in your github account.  A token can be revoked without changing your password.
- configure the git-sync plugin in the grav admin:
  - enter username and access token.
  - enter the repo URL.
  - enable the Webhook Secret
  - Configure the Webhook on the repo following the instructions in gitsync, including the secret provided by git-sync.
  - Select all options for folders to sync for git-sync
- On the github landing page for the repo, "manage topics"
   - set the topic, "user-knowledge"

## Configure Site

* Review site configuration - See [Roadmap](/backlog) for suggestions:
* Configure Site Options
  * Site Title: e.g. "Museum of Math Knowledgebase"
  * Default Author: Ginkgo
  * Default Email: devs@ginkgostreet.com

