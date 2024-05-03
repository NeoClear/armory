---
title: "Assistance Tools"
description: Tools to automate daily tasks and make your development experience better. Keep an entry in the blog for caching
date: 2022-11-28
images:
  - assistance-tools/preface.png
tags:
  - Tool
---

<!-- Linter is getting confused about the asterisks in cron syntax -->
<!-- markdownlint-disable MD037 -->

## Setup Tools
These tools are really useful when bootstraping from a new machine.

+ **direnv**: A tool to autoload env for each directory.
+ **Kitty, Wezterm, Alacritty, Contour**: Terminal emulators.
+ **asdf**: Package version control tool.
+ **mise**: An alternative to **asdf** and **rtx**. (you probably want to use
  this)
+ [**nix**](https://determinate.systems/posts/determinate-nix-installer/): It is
  another environment manager for builds; I am not sure if I would use these.

## Regular Tools
Below are useful but unnecessary tools.

+ [**aria2c**](https://aria2.github.io/): aria2c is a tool to download files
  with any protocols. It supports BitTorrent, magnet link and many more. It also
  has a C++ library that allows you to build tools on top of libaria2.

+ **firewall-cmd & firewalld**: **firewalld** is the daemon process that manages
  port visibility. **firewall-cmd** is the command line tool that configures
  firewalld.

+ [**Eternal Terminal**](https://eternalterminal.dev/): **et** is a kind of
  persistent ssh. To set it up properly on the server, you need to set the port
  number in _/etc/et.cfg_, and also enable the port number using
  **firewall-cmd**. The default port for **et** is 2022.

+ **systemctl**: The command line tool to start/stop/manage daemon process.

+ [**Fig**](https://fig.io/): A great command line autocomplete tool for mac &
  iTerm2. Currently it does not work well on Linux server.

+ [**Prezto**](https://github.com/sorin-ionescu/prezto): A framework to improve
  zsh experience.

+ **tmux**: Terminal multiplexter to make a better shell experience. Both iTerm2
  & ET supports integration with **tmux**.

+ [**hugo**](https://gohugo.io/): A fast framework to build static websites
  fast. It is suggested over **hexo** for building blogs.
  {{<img src="hugo.png" alt="hugo server" caption="Hugo local server">}}

+ [**fzf**](https://github.com/junegunn/fzf): A framework to easily traverse
  through command line history.

+ [**tpm**](https://github.com/tmux-plugins/tpm): tmux plugin manager.

+ [**tmux-continuum**](https://github.com/tmux-plugins/tmux-continuum): tmux
  plugin to save and restore tmux sessions on reboot.

+ [**asciinema**](https://asciinema.org/): Record terminal sessions without
  barrier.

+ [**balenaEtcher**](https://www.balena.io/etcher/): A software burns images to
  usb drives.

+ [**Helix**](https://helix-editor.com/): A post-modern editor that serves as an
  alternative to vim/neovim. The terminal editor is written in Rust and starts
  fast. The edit mode is a bit different from vim, and batch edits are based on
  selection. You may find it useful when it comes to editing code. And it loads
  fast.

+ **Raycast**: Alternative to default Spotlight on Mac.

+ **OrbStack**: An alternative to Docker on Mac.
