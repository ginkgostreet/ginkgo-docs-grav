---
title: Project Lab Set-Up
taxonomy:
  category: 
    - docs
  tag:
    - content
    - guide
routes:
  canonical: /guides/project-setup
content:
    items: '@self.children'
    limit: 0
    pagination: true
process:
    twig: true
page-toc:
    active: false
---

# Setting up a new Project Lab

## Goal

This guide will walk you through the process of creating a new Project Lab instance on docs.Ginkgo.st. A new project lab consists of a branch of the Grav flat-file CMS and a repo on GitHub.

## Pre-flight Check

You will need:

- A user with shell access on Ginkgo Street Labs (docs.ginkgo.st)
- GitHub [key-based authentication][1] on the docs server. It is recommended that you use [SSH Forward-Agent][2] to achieve this.
- Admin (sudo) privileges
- A GitHub account with rights to create repositories in the GinkgoStreet (https://github.com/ginkgostreet) Organization and manage the team that is to work in the Lab.

[1]: https://help.github.com/en/articles/connecting-to-github-with-ssh "Connecting to Github With SSH"
[2]: https://dev.to/levivm/how-to-use-ssh-and-ssh-agent-forwarding-more-secure-ssh-2c32 "Setup SSH Keys and Agent Forwarding"


## Overview

{% for p in page.collection %}

### [{{ p.title }}]({{ p.url }})
{{ p.summary|striptags|safe_truncate(300) }}
{% endfor %}


