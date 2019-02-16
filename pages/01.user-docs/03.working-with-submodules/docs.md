---
title: 'Working With Submodules'
taxonomy:
    category:
        - docs
    tag:
        - user-docs
visible: true
routes:
    cannonical: /submodules
---

## General

At the very least our `ginkgo-rtfm` theme will be added to our Grav sites as a submodule.

Set the path in `.gitmodules` or by issuing the command: `git something something`

## Adding a Submodule

Here is an example of adding a git submodule using our RTFM theme as an example:

- SSH into the RTFM server
- `cd /path/to/user`
- At this point it's probably wise to do a fetch and pull, and make sure you're on the right branch, etc.
- `git submodule add git@github.com:ginkgostreet/grav-theme-ginkgo-rtfm.git themes/ginkgo-rtfm`
- Note: The name of the directory you clone the repo into is important. It needs to be named what the theme is named, or this won't work.
- After the theme repo has been added as a submodule, you should now see a `.gitmodules` file in the parent repo. Doing a `cat .gitmodules` should show you that it's in there.
- 

## Updating Submodules

It appears submodules don't update themselves in repos, so if you know submodules have been update (e.g. theme updates or additions have been made) then `ssh` into the `rtfm` server, `cd` to the site's `user` directory, and do:

- `git fetch`
- `git status`
- Other `git` functions as necessary (maybe you have content updates to pull?)

- `submodule update --remote --checkout themes/ginkgo-rtfm`

Bingo's your monkey!

