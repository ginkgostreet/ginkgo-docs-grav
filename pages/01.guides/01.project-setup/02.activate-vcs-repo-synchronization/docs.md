---
title: Activate VCS Repo Synchronization
taxonomy:
  category:
    - docs
  tag:
    - content
    - guide
routes:
  canonical: /guides/project-setup/activate-vcs-repo-synchronization
---
# Activate VCS Repo Synchronization

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