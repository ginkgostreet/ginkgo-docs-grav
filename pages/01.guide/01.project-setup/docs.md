---
title: 'Project Setup'
taxonomy:
    category:
        - docs
    tag:
        - user-docs
visible: true
---

## docs-user

Create a user and set-up the web-root, including permissions.

You can re-run the permissions with `docs-user facls`.

## grav-util

Create grav instances using the Ginkgo Street Labs template.

**TO-DO:** Add the [Ginkgo RTFM theme](https://github.com/ginkgostreet/grav-theme-ginkgo-rtfm) to the template. Or possibly add creating the theme as a submodule to the utility. This theme is currently configured as a `submodule` in the `ca-docs` instance, and it works pretty well. The theme doesn't sync with `git-sync` like the rest of the file; one has to `cd` to the `user` directory of the instance they want to update and do a `git submodule update --init --recursive` sorta thing. Honestly the `--init` and `--recursive` bits are unnecessary if this is the only submodule, but there's probably no harm in adding those parameters.

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

**TO-DO:** Configure some sort of black magic to keep submodules in sync. Shell script? Something more automagic? Might not be a bad idea to have this be semi-manual for the time being.

## Add the Dev Environment starter

**TO-DO:** make this mo-betta

Confirm env vars: `PUBLIC_HTML` `USER_NAME`

`make -f /usr/local/lib/grav-util/ginkgo-grav/Makefile dev-env`

#### Add dev-env config to content repo
The localhost environment config is ignored by the git-sync setup.

Update the `.gitignore` (add the last two lines) to match:
```shell
/*
!/pages
!/themes
!/plugins
!/config
!/data
!/localhost
/localhost/config/security.yaml
```
Commit the config to the repo:
`git add localhost`

Trigger a git-sync in the Admin UI to publish the config to the repo.

## Configure Site

* Review site configuration - See [Roadmap: #More Default Configs](/backlog) for suggestions:
* Configure Site Options
  * Site Title: e.g. "Museum of Math Knowledgebase"
  * Default Author: Ginkgo
  * Default Email: devs@ginkgostreet.com

