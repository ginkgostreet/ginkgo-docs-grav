---
title: Off-line Content Creation
visible: true

---

Use git to edit content in a development environment.

Structure commits meaningfully.

Use branches and Pull-Requests.



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
Listening on http://localhost:8947
Document root is /home/mzd/work/drafting/docs-grav
Press Ctrl-C to quit.

```

