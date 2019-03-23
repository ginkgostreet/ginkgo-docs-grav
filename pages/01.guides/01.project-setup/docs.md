---
title: 'Project Setup'
taxonomy:
    category:
        - docs
    tag:
        - user-docs
routes:
    canonical: /guides/project-setup
---

# Setting up a new Project Lab

We have created tools to make setting up a Project Lab on the RTFM server easy and consistent. Using the `grab-utils` module for `make-do` most of the process is automatic. See https://github.com/ginkgostreet/grav-util for further documentation not captured here.

## 1. User Setup

The following is written assuming you are creating a new Project Lab on the RTFM Server. Please adjust paths and other variables for your local environment if required.

1. Login in to the Project lab server by doing  `ssh rtfm` 
2. Set your sessions variable for the user (client) you want to set up
   - `export USER_NAME=docs`
   - `export PUBLIC_HTML=/home/${USER_NAME}/public_html`
3. Run `grav-util docs-user` to create the user, you might need to run it as `sudo`
4. This command not only creates a user and sets-up the web-root, it sets some permissions.
5. You can re-run the permissions with `docs-user facls`.

## 2. Create the Grav instance

1. If this is the first instance of the Project Lab, it is probably best to go ahead and set up the repo for the project in GitHub at this point. Naming convention looks like `gsl-docs` where `gsl` is the client code we use. See the [git-sync](#git-sync) instructions below for GitHub setup.
2. Set your sessions variable for the user (client) you want to set up
   - `export PUBLIC_HTML=<project-dir>` where `<project-dir>` is the path the where you want the Grav site to libe e.g. `export PUBLIC_HTML=/home/${USER_NAME}/public_html`
   - Replace `<project-repo>` with the proper repo URL:  `export PROJ_LAB_REPO=git@github.com:/ginkgostreet/<project-repo>`
3. Run the `grav-util create` command to create a Grav instances using the Ginkgo Street Labs template.
1. Things that came up in install:
   - Do you want to remove the existing VCS (.git, .svn..) history? [Y,n]? 
   - Also this command did NOT create a Grav instance with the GSL template.
4. Thinking that I am following the `grab-util` README, I ran `grav-util dev-env` with the following result:
  ```shell
  ---
  $PUBLIC_HTML is /home/im4us/public_html
  ---
  composer create-project getgrav/grav /home/im4us/public_html --no-dev
  Installing getgrav/grav (1.5.10)

    [InvalidArgumentException]                                
    Project directory /home/im4us/public_html/ is not empty.  

  create-project [-s|--stability STABILITY] [--prefer-source] [--prefer-dist] [--repository REPOSITORY] [--repository-url REPOSITORY-URL] [--dev] [--no-dev] [--no-custom-installers] [--no-scripts] [--no-progress] [--no-secure-http] [--keep-vcs] [--remove-vcs] [--no-install] [--ignore-platform-reqs] [--] [<package>] [<directory>] [<version>]

  /usr/local/lib/grav-util/Makefile:18: recipe for target 'grav-install' failed
  make: *** [grav-install] Error 1
  ```
5. Run `grav-util ginkgo-grav` to add the GSL plugins, themes, etc. This seemed to work okay, except the theme still wasn't set and there was no "skeleton" of a Project Lab like I expected.
6. Deleted all the files in `public_html` and ran `grav-util project-lab USER_NAME=im4us` thinking this would spin it up proper. This is what I got in the shell:
  ```shell
  ---
  $PUBLIC_HTML is /home/im4us/public_html
  ---
  docs-user user_name=im4us facls
  sh: 1: docs-user: Permission denied
  /usr/local/lib/grav-util/Makefile:27: recipe for target 'docs-user' failed
  make: *** [docs-user] Error 126
  ```
7. Okay, fine, I'll try it as `sudo grav-util project-lab USER_NAME=im4us` and see what that does:
  ```shell
  ---
  $PUBLIC_HTML is /home/im4us/public_html
  ---
  docs-user user_name=im4us facls
  make[1]: Entering directory '/usr/local/lib/docs-user'
  
  ---
  $USER_NAME is im4us
  ---
  sudo setfacl -Rm 'mask:rwx' /home/im4us/public_html
  sudo setfacl -Rm 'd:u:www-data:rwX,u:www-data:rwX' /home/im4us/public_html
  sudo setfacl -Rm 'd:g:maint:rwX,g:maint:rwX' /home/im4us/public_html
  make[1]: Leaving directory '/usr/local/lib/docs-user'
  Declining to run as root.
  composer create-project getgrav/grav /home/im4us/public_html --no-dev
  Do not run Composer as root/super user! See https://getcomposer.org/root for details
  Installing getgrav/grav (1.5.10)
    - Installing getgrav/grav (1.5.10): Downloading (100%)         
  Created project in /home/im4us/public_html
  Loading composer repositories with package information
  Installing dependencies from lock file
  Package operations: 35 installs, 0 updates, 0 removals
    - Installing antoligy/dom-string-iterators (v1.0.1): Downloading (100%)         
    - Installing composer/ca-bundle (1.1.4): Downloading (100%)         
    - Installing doctrine/cache (v1.6.2): Downloading (100%)         
    - Installing doctrine/collections (v1.4.0): Downloading (100%)         
    - Installing donatj/phpuseragentparser (v0.13.0): Downloading (100%)         
    - Installing erusev/parsedown (1.6.4): Downloading (100%)         
    - Installing erusev/parsedown-extra (0.7.1): Downloading (100%)         
    - Installing psr/log (1.1.0): Downloading (100%)         
    - Installing filp/whoops (2.3.1): Downloading (100%)         
    - Installing gregwar/cache (v1.0.12): Downloading (100%)         
    - Installing gregwar/image (v2.0.24): Downloading (100%)         
    - Installing ralouphie/getallheaders (2.0.5): Downloading (100%)         
    - Installing psr/http-message (1.0.1): Downloading (100%)         
    - Installing guzzlehttp/psr7 (1.5.2): Downloading (100%)         
    - Installing seld/cli-prompt (1.0.3): Downloading (100%)         
    - Installing league/climate (3.4.1): Downloading (100%)         
    - Installing matthiasmullie/path-converter (1.1.2): Downloading (100%)         
    - Installing matthiasmullie/minify (1.3.61): Downloading (100%)         
    - Installing symfony/polyfill-mbstring (v1.10.0): Downloading (100%)         
    - Installing symfony/var-dumper (v3.4.23): Downloading (100%)         
    - Installing maximebf/debugbar (v1.15.0): Downloading (100%)         
    - Installing miljar/php-exif (v0.6.4): Downloading (100%)         
    - Installing monolog/monolog (1.24.0): Downloading (100%)         
    - Installing symfony/polyfill-ctype (v1.10.0): Downloading (100%)         
    - Installing twig/twig (v1.38.2): Downloading (100%)         
    - Installing phive/twig-extensions-deferred (v1.0.2): Downloading (100%)         
    - Installing psr/container (1.0.0): Downloading (100%)         
    - Installing psr/simple-cache (1.0.1): Downloading (100%)         
    - Installing symfony/yaml (v3.4.23): Downloading (100%)         
    - Installing symfony/event-dispatcher (v3.4.23): Downloading (100%)         
    - Installing pimple/pimple (v3.2.3): Downloading (100%)         
    - Installing rockettheme/toolbox (1.4.2): Downloading (100%)         
    - Installing symfony/debug (v3.4.23): Downloading (100%)         
    - Installing symfony/console (v3.4.23): Downloading (100%)         
    - Installing symfony/polyfill-iconv (v1.10.0): Downloading (100%)         
  Generating autoload files
  > bin/grav install
  
  Installing vendor dependencies
  Do not run Composer as root/super user! See https://getcomposer.org/root for details
  Loading composer repositories with package information
  Installing dependencies from lock file
  Nothing to install or update
  Generating optimized autoload files
  
  Cloning Bits
  ============
  
  Cloning into 'user/plugins/problems'...
  SUCCESS cloned https://github.com/getgrav/grav-plugin-problems -> /home/im4us/public_html/user/plugins/problems
  
  Cloning into 'user/plugins/error'...
  SUCCESS cloned https://github.com/getgrav/grav-plugin-error -> /home/im4us/public_html/user/plugins/error
  
  Cloning into 'user/plugins/markdown-notices'...
  SUCCESS cloned https://github.com/getgrav/grav-plugin-markdown-notices -> /home/im4us/public_html/user/plugins/markdown-notices
  
  Cloning into 'user/themes/quark'...
  SUCCESS cloned https://github.com/getgrav/grav-theme-quark -> /home/im4us/public_html/user/themes/quark
  
  make -f /usr/local/lib/grav-util/ginkgo-grav/Makefile
  make[1]: Entering directory '/home/im4us/public_html'
  cd /home/im4us/public_html && \
  /home/im4us/public_html/bin/gpm selfupgrade -yf
  
  GPM Releases Configuration: Stable
  
  You are already running the latest version of Grav (v1.5.10) released on Thu Mar 21 20:17:07 2019
  cd /home/im4us/public_html && \
  /home/im4us/public_html/bin/gpm install -n admin archives email error external_links featherlight feed form git-sync \
  login markdown-fontawesome page-inject pagination problems relatedpages simplesearch sitemap taxonomylist \
  youtube learn2
  
  GPM Releases Configuration: Stable
  
  Preparing to install Admin Panel [v1.8.20]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Archives [v1.5.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Email [v2.7.2]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Package error not overwritten
  Preparing to install External Links [v1.6.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Featherlight [v1.5.0]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Feed [v1.6.2]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Form [v2.16.4]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Git Sync [v2.0.3]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Login [v2.8.4]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Markdown Font Awesome [v1.0.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Page Inject [v1.3.0]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Pagination [v1.4.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Package problems not overwritten
  Preparing to install Related Pages [v1.2.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install SimpleSearch [v1.14.2]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Sitemap [v1.9.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Taxonomy List [v1.3.3]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install YouTube [v3.0.1]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Preparing to install Learn2 [v1.8.0]
    |- Downloading package...   100%
    |- Checking destination...  ok
    |- Installing package...    ok                             
    '- Success!  
  
  Clearing cache
  
  Cleared:  /home/im4us/public_html/cache/compiled/*
  
  Touched: /home/im4us/public_html/user/config/system.yaml
  
  cd /home/im4us/public_html/user/plugins && \
  git clone git@github.com:fulltrucker/modified-date.git
  Cloning into 'modified-date'...
  git@github.com: Permission denied (publickey).
  fatal: Could not read from remote repository.
  
  Please make sure you have the correct access rights
  and the repository exists.
  /usr/local/lib/grav-util/ginkgo-grav/Makefile:16: recipe for target 'skelington' failed
  make[1]: *** [skelington] Error 128
  make[1]: Leaving directory '/home/im4us/public_html'
  make-do.mk:46: recipe for target 'ginkgo-grav' failed
  make: *** [ginkgo-grav] Error 2
  ```
8. Okay, I'm kinda of over this now… probably gonna commit changes to this Guide and call it.


## git-sync

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

## Configure Site

* Review site configuration - See [Roadmap: #More Default Configs](/roadmap/ginkgo-grav-install-profile) for suggestions:
* Configure Site Options
  * Site Title: e.g. "Museum of Math Knowledgebase"
  * Default Author: Ginkgo
  * Default Email: devs@ginkgostreet.com
* Initialize dev-environment config (on the server)
  ​```shell
  export PUBLIC_HTML=project-dir 
  grav-util dev-env
  export PROJ_LAB_REPO=git@github.com:/ginkgostreet/<project-repo>
  grav-util project-lab-repo
  ```
  You will have to override the `.gitignore` to commit the directory. After committing locally, use the git-sync in the Admin interface to push the changes.
  ```


