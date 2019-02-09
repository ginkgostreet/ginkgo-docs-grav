---
title: 'Research & Development'
visible: true
---

## Security and Authentication

* Deny un-authenticated access
* Creating User Accounts

## Edit In-place

Writers should be able to edit content without using the Admin.

Instead of providing the link to edit on GitHub, provide a link (to permissioned users) to open an editor on the front-end.

## Broken Link Checker

Add the broken link checker plugin into the default install profile.

https://github.com/jgonyea/grav-plugin-broken-link-checker

Document it's usage.

Any way to automate via git-hooks?

## Enabling Forward-Next Links

The Grav docs have a nifty trick where pages are linked to each other in a previous-next relationship.

## Theme Titles

The Learn2 (and related themes) display the title from the frontmatter as a header-1. The title is necessary for the menu system. This results in a few awkward scenarios. As the default grav theme does, the frontmatter title should not be rendered as a title on the page, so that an explicit title can be set. 

## Table of Contents

Add an auto-generated Table of Contents to the theme.

Look for an example in an existing Theme.

## What can be done with Page Collections?

https://learn.getgrav.org/content/collections

## Upstream Issues to Track
* [Admin plugin dirties environment configs](https://github.com/getgrav/grav-plugin-admin/issues/1614)

