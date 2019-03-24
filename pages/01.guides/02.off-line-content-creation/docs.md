---
title: 'Off-line Content Creation'
taxonomy:
    category:
        - docs
    tag:
        - content
        - guide
routes:
    canonical: /guides/off-line-content-creation
---

# Create a Dev Environment

A dev-environment is a local install of Grav CMS that we then set-up to follow the same repo as the production instance of the Lab. Critically, the git-sync plugin will be disabled. Some other configurations will optimize the instance for a local work-flow.

Remember to use good git workflows:

* Use git to edit content in a development environment.
* Structure commits meaningfully.
* Use branches and Pull-Requests.

## Install Grav-Util

https://github.com/ginkgostreet/grav-util

## Create a new Grav Install

`grav-util create` will create a clean grav install.

## Synchronize with the Lab

The `grav-util dev-env` command will replace a grav `/user` directory by cloning the Lab git repo. The repo URL, as well as the web-root need to be configured.

```shell
export PUBLIC_HTML=project-dir 
export PROJ_LAB_REPO=git@github.com:/ginkgostreet/<project-repo>
grav-util dev-env
```
## Environment Config
Grav supports environment configs that are named for the host. So, the default configs are located in `/user/config` but you could configure production as `/user/docs.ginkgo.st/config` and a dev environment as `/user/localhost/config`.

Do not commit your environment config unless you consult with your team on what configs should be shared. 

Editing site configs in the Admin interface is discouraged. This essentially copies the default config to the environment config files, making maintenance much more difficult. The committed version of the environment config should only contain the overriding configs for transparency.


## PHP built-in server (serve-grav)

https://learn.getgrav.org/basics/installation#running-grav-with-the-built-in-php-webserver-using-router-php

When you install grav-util, it installs the serve-grav command as well. You can override the default hostname and port passed as args e.g. `serve-grav localhost 1234`.

However, `serve-grav` search for an available port automatically, so overriding should be rare.

Change directory to the root of your grav instance before running it.

```shell
mzd☯ artichoke :>serve-grav 
/var/www/grav/
PHP 7.2.10-0ubuntu0.18.04.1 Development Server started at Fri Feb  8 23:10:21 2019
Listening on http://localhost:8888
Document root is /var/www/grav
Press Ctrl-C to quit.

```

