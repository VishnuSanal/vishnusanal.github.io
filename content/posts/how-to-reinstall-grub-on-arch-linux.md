---
title: How to Reinstall Grub on Arch Linux
date: 2024-01-19T14:46:17+05:30
author: Vishnu Sanal T
keywords: ["grub", "reinstall", "chroot", "arch", "linux"]
description: "The steps to reinstall grub by chrooting on Arch Linux"
---

Sooo, you have a crucial deadline to meet, or you have an important assignment to complete. You turn on your PC, and, surprise, surprise, the PC decides to go into the BIOS menu! You try to force a restart, only to end up with the same result.

Next, you start panicking & call  "that-Linux-friend". If you don't have such a friend, don't worry; I have got you covered with this blog!

# Steps to reinstall GRUB on Arch Linux via chroot

## 1. Download & Burn

- Visit the [download page](https://archlinux.org/download/), select a mirror, and download the latest ISO file. It would look something like `archlinux-YYYY.MM.DD-x86_64.iso`
- Burn the ISO onto a flash disk. You can use the following command, if you are on a Linux machine (replace `<disk>` with your disk).
    - ```sudo dd bs=4M if=archlinux-YYYY.MM.DD-x86_64.iso of=/dev/<disk> conv=fsync oflag=direct status=progress```

## 2. Boot

- Connect the bootable disk & boot into it.
    - You might want to look up _"<your laptop/PC name & version> boot menu"_ & follow those steps to enter the boot menu.

- Select the first option from the options to boot into the live environment.

## 3. `chroot`

- check your disk partition table with `fdisk`
    - `fdisk -l`
- mount your root partition onto `\mnt` (usually the largest partition)
    - `mount \dev\<your-root-partition \mnt` 
- mount your EFI partition onto `\mnt\boot` (usually the one 512MB in size)
    - `mount \dev\<your-efi-partition \mnt\boot`

## 4. Reinstall GRUB

- Verify you have a UEFI boot (if the command shows some output, then you are good to go)
    - `efibootmgr -uv`
- Create the config file
    - `sudo grub-mkconfig -o /boot/grub/grub.cfg`
- Install GRUB
    - `sudo grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=GRUBNEW`

## 5. Unmount & Reboot

- Unmount
    - `umount \mnt\boot`
    - `umount \mnt`
- Reboot
    - `reboot`

This was a short guide on how to reinstall GRUB on an Arch Linux PC. The same should work for all Arch-based OSs (I have tried on EndeavourOS; I can't vouch for others!). Huge shout out to Jazil, Shidul, Akash, Abhiram, Shijaz, and Roshan, my friends -- break more of your bootloaders!! xD