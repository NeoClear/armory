---
title: "Linux Tools"
description: Cheat sheets containing various common linux utility tools that is used daily. The list has (but not limited to) bluetooth utilities, audio control cli and display manager.
date: 2024-05-11
hero_image: preface.jpg
tags:
  - Tool
---
<!-- TODO: Change the preface  -->

<!-- Linter is getting confused about the asterisks in cron syntax -->
<!-- markdownlint-disable MD037 -->

## Bluetooth Utilities (`bluetoothctl`)
`bluetoothctl` is a cli tool that controls bluetooth connections. Here is a sequence of commands that connects a bluetooth device.

`scan on`: show a list of available devices with their MAC addresses. In this step find the MAC address of the device you are trying to connect.
`scan off`: turn off the scan.
`pair <MAC>`: pair the device.
`connect <MAC>`: connect the device.
`disconnect <MAC>`: disconnect the device.

## Audio Utilities
Mostly, amixer is the right cli tool to control audio. However, I would
recommend using 'alamixer', the front-end tool for amixer. The UI of this tool
is intuitive, thus I would not put any instructions there.

## GUI
Linux window system is powered by various window managers. Famous window managers include: gnome, kde and i3. Usually, starting a window manager is either by executing `startx` or run the window manager manually by `i3 -r`.
Window manager is the window system you interact with. However, the start up menu is powered by display manager. Just to name a few: gdm3 for gnome. I would recommend gdm3 as display manager, as it is small enough and easy to install.

## Linux Common Locations
Linux has some common locations to store config files and assets. Just to name a few:

+ `/etc/apt/source.list`: containd debian packages repository urls. This config file is useful when managing package versions. Also, `/etc/apt/source.list.d/*` contains repository urls for external packages. Just to name a few: 1password.

<!-- TODO: Add more linux locations -->
