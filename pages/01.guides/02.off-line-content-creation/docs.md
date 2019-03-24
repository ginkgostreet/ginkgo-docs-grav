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

## Summary

If you want to participate in a Project Lab, you should create a local grav instance. After the base install, delete `/user` directory and replace it by cloning the Project Lab repo.

```
git@github.com:ginkgostreet/project-docs.git user
```

Remember to use good git workflows:
 -  Use git to edit content in a development environment.
 - Structure commits meaningfully.
 - Use branches and Pull-Requests.

## Environment Config
Grav supports environment configs that are named for the host. So, the default configs are located in `/user/config` but you could configure production as `/user/docs.ginkgo.st/config` and a dev environment as `/user/localhost/config`.

## Initialize the dev environment
Confirm that the `user/localhost` directory exists. 

If not, you can start a new config by creating the file `/user/localhost/config/system.yaml`.
with the contents:
``` yaml
debugger:
  enabled: true
  shutdown:
    close_connection: true
  twig: true
```

Optional: pull-down the user/accounts directory, or else you will have to create a login for yourself.
`rsync -rv rtfm:/home/fis/public_html/user/accounts user/`

Otherwise, you can create a login from `/admin`, or use the cli:
`bin/plugin login`

## PHP built-in server

https://learn.getgrav.org/basics/installation#running-grav-with-the-built-in-php-webserver-using-router-php

You can create a bash function to put in your `.bash_aliases`.

```shell
grav-server()
{
        test -z "$1" && docroot='./' || docroot="$1"
        test  -z "$2" && port=8947 || port=$2
        php -S localhost:$2 -t "$docroot" "$docroot"/system/router.php
}
```

Both arguments are optional, using the current directory and the port 8947 by default.

`grav-server /var/www/grav 8888`

```shell
mzd☯ artichoke :>grav-server 
/var/www/grav/
PHP 7.2.10-0ubuntu0.18.04.1 Development Server started at Fri Feb  8 23:10:21 2019
Listening on http://localhost:8888
Document root is /var/www/grav
Press Ctrl-C to quit.

```

