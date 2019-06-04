---
title: Creating and Managing User Accounts
taxonomy:
  category: 
    - docs
  tag:
    - feature
routes:
  canonical: /features/grav-security-authentication/creating-and-managing-user-accounts
---
# Creating and Managing User Accounts

This topic covers both configuration and use of enabling User Accounts in a Project Lab, for the purpose of facilitating client access to the Admin Panel to edit and add documentation. First, some official documentation:

* https://learn.getgrav.org/16/security/users#grav-users-and-the-administration-panel
* https://learn.getgrav.org/16/admin-panel/dashboard/profile#access-levels
* https://learn.getgrav.org/16/advanced/groups-and-permissions

## Basic Configuration

You will need to set up two Groups to manage different levels of user access to the Admin Panel. We have selected the names `Administrators` and `Staff` to denote the two levels of access. Essentially, Administrators have full access to the Admin Panel, can configure and update Plugins, Users, Groups, etc. as well as create and edit site content. Staff users only have access to create and edit content, as well as clear the cache. Helpful links:

* [Groups and Permissions documentation](https://learn.getgrav.org/16/advanced/groups-and-permissions)
* [Sample Groups settings .yaml file](groups.txt)

## Required Plugins

* [Admin Panel](https://github.com/getgrav/grav-plugin-admin)
* [Login](https://github.com/getgrav/grav-plugin-login)
* [Email](https://github.com/getgrav/grav-plugin-email)
* [Admin Addon User Manager](https://github.com/david-szabo97/grav-plugin-admin-addon-user-manager)

## Plugin Configurations

### Admin Panel

No additional configuration required to enable user account access

### Login

The Login plugin doesn't appear to be able to specifically grant Admin Panel access on account creation. This isfine, since the client will be able to designate a staff person to manage client account access using the Admin Add-on User Manager plugin. Additionally, the Login plugin can place new users into [Groups](https://learn.getgrav.org/16/advanced/groups-and-permissions) at the time of registration. The Login plugin will need some additional configuration in the `user_registration` section to enable self-serve user account creation:

* `user_registration.enabled: true`
* `user_registration.redirect_after_registration: /admin`
* `user_registration.set_user_disabled: false`
* `user_registration.send_notification_email: true`
* `user_registration.send_welcome_email: true`
* `user_registration.groups: - staff`

These settings will redirect the self-registered user to the `/admin` login screen after they register, and will also send an email to the "site administrator" (i.e. the "To: email address configured in the Email plugin") as well as the newly self-registered user. The new user is set to active by default.

Please see [this text file](login.txt) for an example of a complete sample Login settings .yaml file.

### Email

Configure the `from`, `from_name`, `to`, `to_name`, `cc`, `cc_name`, `bcc`, and `bcc_name` fields as required for the client's needs. Suggested config is From is `noreply@ginkgostreet.com` and the From name is `<client_name> Project Lab`. To email and name should be the client's designated admin, and we can set the CC or BCC to `clients+XX@ginkgostreet.com` so we get notified as well.

### Admin Add-on User Manager

It appears we're using this plugin with t's default configuration, which is that it is `enabled`.

## New User Registration

New users can be created in a few ways:

### Self-Registration

This is going to be the preferred and recommend method of creating and managing new and existing users for our clients. Basically, the staff user who desires an account creates it themselves, and then the client admin user sets the appropriate level of permissions using the 

1. Staff user goes to the Project Lab front-end and clicks the "Register" link in the left nav bar.
2. Staff user fills out reg form, submits it.
3. Staff user and staff admin both receive email notification that a new account has been created. Staff user should have have access to the Admin Panel by default, due to being added to the `Staff` group.
4. Staff Admin can log in to Admin Panel, and by using the User Manager in the left-hand nav, can edit or add additional permissions for the new user, if required.

### Admin Creation Using Admin Panel

1. Staff admin logs in to Admin Panel and selects the User Manager in the left-hand nav
2. Staff admin clicks the "Add" button in the upper right-hand corner
3. Staff admin enters the new username in the pop-up modal and clicks "Continue"
4. On the next screen, the staff admin enters the required user info, and ensures the new user is placed in the `Staff` group.
5. After saving the new user, it does not appear that any emails are sent to the new user or to the site admin. This is problematic, but if the site admin informs the staff user that the account has been created the staff user can do a "Forgot Password" from the login screen and set the password to whatever they would like.

**Note:** The staff admin MUST enter a password for the new user, otherwise the Password Reset function might (definitely) not work.

### Admin Creation Using the CLI

Instructions for creating a new user on the command line can be found here: https://github.com/getgrav/grav-plugin-login#cli-usage

Not recommended as assigning permissions isn't very granular.

### Admin Manual Creation via .yaml File

Instructions/overview of creating a new user by creating a user by creating a `.yaml` file on the server are here: https://github.com/getgrav/grav-plugin-login#manual-user-creation

Not recommended / not going to provide this options as setting a password seems damn near impossible, and the client admin would require access to the server.

