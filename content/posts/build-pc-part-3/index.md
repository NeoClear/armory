---
title: "Secret of Motherboard"
description:
date: 2025-05-09
tags:
  - Tutorial
  - Personal Setup
---

## Windows Installation
1. Windows orders disk different from motherboard. Also, because Windows installation media requires a specific disk to be picked on startup, Windows can only install to the first disk in the list. When dual-booting Windows, please only put 1 disk on the Motherboard.
2. The best practice is to give each OS its individual disk.
3. Windows installation media tool formats disk to FAT32 by default, and that doesn't work for Windows 11. Use Rufus instead.

## Linux Installation
1. To update grub menu options, run `sudo grub2-mkconfig -o /boot/grub2/grub.cfg`
