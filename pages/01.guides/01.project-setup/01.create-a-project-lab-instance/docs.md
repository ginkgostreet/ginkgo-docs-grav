---
title: Create a Project Lab Instance
taxonomy:
  category:
    - docs
  tag:
    - content
    - guide
routes:
  canonical: /guides/project-setup/create-a-project-lab-instance
---
# Create a Project Lab Instance



## Log into the docs server

SSH into the docs server and confirm that you have the necessary permissions.

``` shell
mzd@rtfm:~$ groups
mzd www-data maint
mzd@rtfm:~$ 
```

You must belong to the `maint` group to have the necessary permissions.

## Confirm the Project Key

Confirm that the Project Key you want to use is available. We prefer 3-character project keys. As long as it does not exist under `/home`, it is okay to use your desired Project Key.

``` shell
mzd@rtfm:~$ ls -l /home
total 48
drwxr-xr-x   3 bact   bact   4096 Feb 14 02:06 bact
drwxrwxr-x+  6 ca     ca     4096 Feb  1 00:30 ca
drwxr-xr-x   3 docs   docs   4096 Feb  9 00:50 docs
drwxr-xr-x   4 fis    fis    4096 Mar 19 15:18 fis
drwxr-xr-x   3 hfa    hfa    4096 Feb 10 14:57 hfa
drwxr-xr-x   3 im4us  im4us  4096 Mar 22 22:02 im4us
drwxr-xr-x   3 msa    msa    4096 Mar 23 23:53 msa
drwxr-xr-x   3 varl   varl   4096 Mar  5 03:35 varl
drwxr-xr-x   2 vcs    vcs    4096 Feb 12 03:15 vcs
drwxr-xr-x   3 vol    vol    4096 Feb 10 14:53 vol

```

If you like, you can set the project key for your shell session to avoid passing it to commands explicitly.

``` shell
mzd@rtfm:~$ export USER_NAME='msa'
```

## Instantiate a Lab

``` shell
mzd@rtfm:~$ grav-util project-lab USER_NAME=msa
```

A lot of information will be displayed in your terminal. Give it a visual scan for errors. If you find any, notify the administrator.

If you are prompted to remove existing version control history, it is safe to answer "Yes".

``` shell
Generating autoload files
Do you want to remove the existing VCS (.git, .svn..) history? [Y,n]? Y

```

Near the end of the project-lab command you should see:

``` shell
Clearing cache

Cleared:  /home/msa/public_html/cache/compiled/*

Touched: /home/msa/public_html/user/config/system.yaml

```

This confirms that Grav is functional.

## Confirm the Installation

### Browse Files

The web-root of the Lab should be found in the `public_html` dir of the newly-created user.

``` shell
mzd@rtfm:~$ ls /home/msa/public_html/ -l
total 336
-rw-rw-r--   1 mzd mzd 113583 Mar 21 20:16 CHANGELOG.md
-rw-rw-r--   1 mzd mzd   3216 Mar 21 20:16 CODE_OF_CONDUCT.md
-rw-rw-r--   1 mzd mzd   7081 Mar 21 20:16 CONTRIBUTING.md
-rw-rw-r--   1 mzd mzd   1071 Mar 21 20:16 LICENSE.txt
-rw-rw-r--   1 mzd mzd   6509 Mar 21 20:16 README.md
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 assets
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 backup
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 bin
drwxrwxr-x   5 mzd mzd   4096 Mar 23 23:53 cache
-rw-rw-r--   1 mzd mzd    302 Mar 21 20:16 codeception.yml
-rw-rw-r--   1 mzd mzd   2368 Mar 21 20:16 composer.json
-rw-rw-r--   1 mzd mzd 134174 Mar 21 20:16 composer.lock
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 images
-rw-rw-r--   1 mzd mzd   1543 Mar 21 20:16 index.php
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 logs
-rw-rw-r--   1 mzd mzd    218 Mar 21 20:16 robots.txt
drwxrwxr-x  10 mzd mzd   4096 Mar 21 20:16 system
drwxrwxr-x   7 mzd mzd   4096 Mar 21 20:16 tests
drwxrwxr-x   2 mzd mzd   4096 Mar 23 23:53 tmp
drwxrwxr-x   8 mzd mzd   4096 Mar 21 20:16 user
drwxrwxr-x+ 24 mzd mzd   4096 Mar 23 23:53 vendor
drwxrwxr-x   2 mzd mzd   4096 Mar 21 20:16 webserver-configs

```

### Open in your Web Browser

Point your web browser to https://docs.ginkgo.st/~key, where `key` is your selected project-key.

It has been observed that occasionally a dreaded [WSOD](https://en.wikipedia.org/wiki/Screen_of_death) is encountered after install. Use the `docs-user destroy-user` command, providing the `USER_NAME` variable, and perform the Lab Instantiation again.

### Confirm Login as Admin

Add `/admin` to the address-bar of your browser and confirm that you can login as `admin` using the credentials in the password-safe.  (Yes, we are using a single shared password at the moment.)

