---
title: "Dual Booting Windows and Linux"
description: A guide on how to set up a dual boot system with Windows and Linux
date: 2024-09-07
hero_image: dual-boot.webp
tags:
  - Tutorial
  - Personal Setup
---

## Introduction
Dual booting allows you to have both Windows and Linux installed on the same computer, giving you the flexibility to choose which operating system to use when you start your machine. Surely you may choose to use only one machine. However, how do you game on a Linux computer and how do you write programs properly on Windows? The other alternative is to use a virtual machine, but this route is not "clean" to me. As always, I prefer an OS running on physical hardware to achieve the best performance.

Some of you might think of triple booting, as Hackintosh is also a good choice. To me, macOS runs the best on a real Mac, thus I would not consider running macOS on a non-Apple computer. As a personal reference, I would only dual-boot into both Linux and Windows.

For this guide, I would walk through a few booting and partitioning strategies and hardware capabilities that achives the cleanest dual-booting experience.

## CPU PCIe lanes
Normally CPU would have only one direct PCIe x4 lane provided to the drive, and all other SSDs are connected through chipset extension, which incurs extra latency. Normally transmittion through chipset is not a bit problem, and it does not reduce sequential IO ops. However, 4K performance are impacted by around 20%. Most importantly, adding OS drive through chipset is NOT "mentally clean" to some people (obviously, including me). Thus, you either put both OS into the same drive, or buy a motherboard and CPU with two direct SSD interfaces. Currently Ryzen 7000 & 9000 series has 28 PCIe lanes, and there remains 8 PCIe lanes for SSDs after using 16 lanes for GPU and 4 lanes for chipset.

![X670E PCIe Lane Diagram](x670.png)

(This is not writing a academic paper, so I would not put effort into citation & stuffs. Just be mindful that almost all pictures are taken from the internet)

For X670 and AMD Ryzen 7000/9000 series, CPU provides 28 lanes as explained above. Most high end motherboards provide 2 SSDs with direct connection.

The predecessor of X670, on the other hand, provides only 1 direct SSD connection. What happened? Well, for some reason AMD decides to distribute PCIe x4 as dedicated channel for USB4 port, reducing direct SSD ports from 2 to 1. Yes, you are right, AMD is using PCIe gen 5 as gen 4 just for USB4. It is so ammusing. In this case, if you were to install two SSDs on X870 motherboards in direct connection, it would take additional x4 lanes from the second PCIe slot, resulting PCIe x8 gen 5 mode for the primary GPU. This is allowed, however, as the most high end GPU for the next generation might not take full bandwidth of PCIe x8 gen 5.

If you really do not want to split PCIe lanes for your GPU, your choice becomes either: 1. Use X670 motherboard or; 2. Put both OS into the same drive.

Now let's consider dual-booting from the same drive.

## Boot Loading
How do you want during the boot process? A nice GUI boot menu listing all bootable OSs? Or just a simple TUI menu with bootable kernels? For me, I prefer the latter option.

First, let's talk about installation order. Please install Linux after Windows, as the latest boot loader would be defaulted in BIOS. Also, Linux installer would automatically generate Windows boot menu item for its boot loader, making a nicely curated TUI boot loader for grub2. Alternatively, you may choose third-party boot loader programs, including: rEFInd, systemd-boot, opencore. Opencore is specifically designed to boot Hackintosh, but it is also capable of booting both Linux and Windows. You may install them as alternative options.

Some may heard of Windows updates contaminates Linux boot loader. Well, that should not be a problem for disk partitions based on UEFI. It means modern computers should not worry about it.

## Partition
Well, partition in whatever way you like. Just for Linux, you might wanna assign different partitions manually for different mount points. You need to assign `/boot/efi`, `swap` and `/`. You may also alternatively assign a partition, or even an entire disk for `/home`, securing your data across installations. I wish Windows could have similar functionalities for their home directory, but it is not possible due to OS limitation :(.

## My Strategy
After discussion relevant topics about dual-boot, we finally arrive at the section introducing my strategies and ideologies about building a maintainable and easy-to-use machine.

### Case
Well, my dream PC has an ATX compatible case, maximizing the compatibility and configurability. Currently I am looking at PA602,

![PA602](pa602.png)