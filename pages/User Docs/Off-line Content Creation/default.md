---
title: 'Off-line Content Creation'
visible: true
routes:
    cannonical: /dev-env
---

Use git to edit content in a development environment.

Structure commits meaningfully.

Use branches and Pull-Requests.

## Create a Grav Base-install

```shell
compser create-project --no-dev getgrav/grav project-dir/
cd project-dir
bin/gpm self-upgrade -y
```
* upgrade after installing via composer because sometimes composer package is not up to date with the Stable release.

## Clone the Intance Repo
Remove the default `user/` directory and replace it with the git-sync'd repo:
```shell
cd project-dir/
rm -rf user/
git clone git@github.com:ginkgostreet/fis-docs.git user
```

Confirm that the `user/localhost` directory exists. If not, follow the [instructions for adding the dev-env config](/project%20setup) to the content repo.

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
./
PHP 7.2.10-0ubuntu0.18.04.1 Development Server started at Fri Feb  8 23:10:21 2019
Listening on http://localhost:8888
Document root is /home/mzd/work/drafting/docs-grav
Press Ctrl-C to quit.

```

