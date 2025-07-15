+++
title = "Zellij"
date = "2025-04-01T20:12:21+02:00"
tags = ["Terminal", "CLI", "Linux", "Terminal Multiplexer", ]
draft = true
+++

[Zellij](https://zellij.dev) is a relatively new terminal multiplexer, that is designed to be
easy for beginners to understand and use, <!--but is a little graphically bloated by default.-->
while being very configurable
and full of features more experienced users will appreciate.
<!--more-->

## Installation
One of the things that make zellij interesting, is the ability to try it in your shell before installing it.
```bash
$ bash <(curl -L https://zellij.dev/launch)
```
```fish
$ bash (curl -L https://zellij.dev/launch | psub)
```
## Features
<!-- It has panes, tabs and sessions (like TMUX), and has native session resurrection capabilities. -->
- Panes, Tabs and Sessions (like TMUX)
- [Native Session resurrection capabilities](https://zellij.dev/documentation/session-resurrection.html)
- [Beginner-first approach](https://poor.dev/blog/why-zellij/)
- Built-in plugin manager
- [Layouts](https://zellij.dev/documentation/layouts.html)
## Configuration
The configuration is stored in `$XDG_CONF_HOME/zellij/config.kdl` with language [KDL](https://kdl.dev).


<!--end-->
