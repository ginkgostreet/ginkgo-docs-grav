---
title: 'Ginkgo RTFM Theme'
taxonomy:
    category:
        - docs
    tag:
        - user-docs
visible: true
routes:
    cannonical: /ginkgo-rtfm-theme
---

## General

At the very least our `ginkgo-rtfm` theme will be added to our Grav sites as a submodule.

Set the path in `.gitmodules` or by issuing the command: `git something something`

## Adding the Gingko RTFM theme as a Submodule

Here is an example of adding a git submodule using our RTFM theme as an example. The details here are probably more than necessary for most submodules, since it was written for the Gingko RTFM theme which we do the dev on.

- SSH into the RTFM server
- `cd /path/to/user`
- At this point it's probably wise to do a fetch and pull, and make sure you're on the right branch, etc.
- `git submodule add git@github.com:ginkgostreet/grav-theme-ginkgo-rtfm.git themes/ginkgo-rtfm`
- Note: The name of the directory you clone the repo into is important. It needs to be named what the theme is named, or this won't work.
- After the theme repo has been added as a submodule, you should now see a `.gitmodules` file in the parent repo. Doing a `cat .gitmodules` should show you that it's in there.
- Update `/user/config/system.yaml` to set the theme to Ginkgo RTFM:
```
pages:
  theme: ginkgo-rtfm
```
- You might also need to add the `page-toc` plugin as a dependency, and `active: true` in it's YAML configs file.
- Check the front-facing environment you're working on to ensure changes are happening
- Do the git add, commit, and push dance to the GitHub repo... then git pull to some other remote repo (either local dev or remote prod) that you didn't do the initial install on.
- There was definitely some shenanigans that I didn't quite capture to add or init the submodule on this "second remote" repo. After I did a `git pull` the directory was created, but no files were in it. I ended up having to do a `touch .gitmodules` and adding the info on the submodule manually, then did:
  - `git submodule init`
  - `git submodule update`
- After that, the other environment front-end updated with the them, and all was good with the world. 
- Viola!

## Updating the theme submodule

It appears submodules don't update themselves in repos, so if you know submodules have been update (e.g. theme updates or additions have been made) then `ssh` into the `rtfm` server, `cd` to the site's `user` directory, and do:

- `git fetch`
- `git status`
- Other `git` functions as necessary (maybe you have content updates to pull?)
- `submodule update --remote --checkout themes/ginkgo-rtfm`
- Might be adviseable to fetch, status, add, commit, and push the parent repo if the update of the submodule creates changes in the parent repo.

Bingo's your monkey!

