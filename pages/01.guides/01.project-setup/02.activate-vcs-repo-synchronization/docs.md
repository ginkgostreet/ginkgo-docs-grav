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

## Create a Repository

On GitHub, create a private repo in the GinkgoStreet organization, initialized with a README.md. It should be named for the project-key/docs-user and the suffix, `-docs`. For example, https://github.com/ginkgosteet/bact-docs.

On the github landing page for the repo, "manage topics" and set the topic, "user-knowledge"

## Set Repository Settings 

Review the Repository Settings. 

- Dis-activate features, such as Wikis and Issues
- Grant the team Admin, Admin privileges
- Grant the project team, Write privileges.

You may want to leave your browser open to the Repository Webhook settings, as you will need to add a Webhook in the process of configuring git-sync.

## Personal Access Token

Create a personal access token in your github account.  A token can be revoked without changing your password.

- In the upper-right on GitHub, choose "Settings" from the drop-down on your avatar.
- Find "Developer Settings" near the bottom of the left-nav-menu.
- Choose "Personal access tokens" in the Developer Settings.
- Use the button to "Generate new token", and name it using the Project Key.
- "Select scopes" and enable "repo - Full control of private repositories"
- Submit the form.
- Copy the token somewhere safe so that you can enter it in the next step.

## Configure the Git-Sync Plugin

Find the git-sync plugin configurations in the Grav Admin interface.
- enter username and access token.
- enter the repo URL.
- enable the Webhook Secret
- Configure the Webhook on the repo following the instructions in gitsync, including the secret provided by git-sync.
- Select all options for folders to sync for git-sync

You will be returned to the git-sync plugin configurations, which you can review.

