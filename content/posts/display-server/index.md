---
title: "Display Server Comparisons"
description: Different from Windows/Mac, GUI of Linux is a separate module powered by display server.
date: 2024-05-21
images:
    - display-server/wayland.png
tags:
  - Tool
---

<!-- Linter is getting confused about the asterisks in cron syntax -->
<!-- markdownlint-disable MD037 -->

Display server connects clients with compositor and various peripherals like
keyboard and mouse. Being production ready for decades, X11 display server
powers most Linux GUI apps despite its complexity. On the other hand, Wayland
features simpler architecture that improves performance. However, Wayland has
worse compatibility due to smaller number of supported apps.

For Linux desktop experience, I would recommend using X11 despite its
state-of-the-art efficiency, as lots of apps still lack Wayland support. For
example, Chrome does not support Wayland yet.

Given the above reason, I would recommend using X11 for now to optimize Linux
desktop experience. Do not risk yourself heading into Wayland and found most
applications broken on your screen!
