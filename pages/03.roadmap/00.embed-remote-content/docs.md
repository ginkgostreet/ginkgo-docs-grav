---
title: Embed Remote Content
taxonomy:
  category: 
    - docs
  tag:
    - feature
routes:
  canonical: /features/embed-remote-content
---
# Embed Markdown From Source Control

Our primary use case is to display the README doc from repos, always updated without copypasta them into the Project Lab. The idea is that the README would be largely kept up-to-date for usage, particularly with org agnostic extensions, modules, etc. and so having the Project Lab mirror that content would be convenient.

## Initial Research and Discovery of Embedding Plugins

Embed repo README docs. 

...or any remote content?
 - https://github.com/GertSallaerts/grav-plugin-embed
 - https://github.com/Sommerregen/grav-plugin-mediaembed
 - https://github.com/sommerregen/grav-plugin-textformatter
 - https://github.com/cworreschk/grav-plugin-vimeo
 - https://github.com/getgrav/grav-plugin-youtube
 - https://github.com/andrewscofield/grav-plugin-codepen-embed
 - https://github.com/mikahanninen/grav-plugin-facebook
 - https://github.com/Nebulius/grav-plugin-static-social-embeds

## Embed Local Content

- https://github.com/getgrav/grav-plugin-page-inject

## Use the GitHub API?

The [Grav GitHub plugin](https://github.com/getgrav/grav-plugin-github) enables access to the GitHub API, so assumably anything you can do via the API you could do with this plugin… for instance getting the raw content of a blob such as a READM.md file and shoving it onto a Grav page?

- Grav Plugin that wraps the [GitHub v3 API](https://developer.github.com/v3/): https://github.com/getgrav/grav-plugin-github
- The plugin itself relies on the [php-github-api](https://github.com/KnpLabs/php-github-api/) library to wrap GitHub… not sure if this would also need to be installed on the server?
- Maybe we just want to Get a Blob? https://developer.github.com/v3/git/blobs/#get-a-blob
- Probably raw? https://developer.github.com/v3/media/#git-blob-properties

