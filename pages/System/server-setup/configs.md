---
title: Server Configs

---

# Server Configs

## Apache Userdir

#### `/etc/apache2/mods-enabled/userdir.conf`

Modify `AllowOverride`

```shell
<IfModule mod_userdir.c>
        UserDir public_html
        UserDir disabled root

        <Directory /home/*/public_html>
                # AllowOverride FileInfo AuthConfig Limit Indexes
                AllowOverride All
                Options MultiViews Indexes SymLinksIfOwnerMatch IncludesNoExec
                Require method GET POST OPTIONS
        </Directory>
</IfModule>

```



#### `/etc/apache2/mods-enabled/php7.2.conf`

comment-out IfModule

```shell
# Running PHP scripts in user directories is disabled by default
# 
# To re-enable PHP in user directories comment the following lines
# (from <IfModule ...> to </IfModule>.) Do NOT set it to On as it
# prevents .htaccess files from disabling it.
#<IfModule mod_userdir.c>
#    <Directory /home/*/public_html>
#        php_admin_flag engine Off
#    </Directory>
#</IfModule>

```

## PHP Modules

```shell
sudo phpenmod \
pdo \
pdo_mysql \
pdo_sqlite
```

## PHP Composer

```shell
sudo make -f /root/stand-up make/web-utils.mk web-utils.composer
```

