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

At the very least our `ginkgo-rtfm` theme will be added to our Grav sites as a submodule.

Set the path in `.gitmodules` or by issuing the command: `git something something`

It appears submodules don't update themselves in repos, so if you know submodules have been update (e.g. theme updates or additions have been made) then `ssh` into the `rtfm` server, `cd` to the site's `user` directory, and do:

- `git fetch`
- `git status`
- Other `git` functions as necessary (maybe you have content updates to pull?)

- `submodule update --remote --checkout themes/ginkgo-rtfm`

Bingo's your monkey!