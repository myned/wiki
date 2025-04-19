---
title: LUKS
description: 
published: true
date: 2025-04-19T19:07:45.351Z
tags: 
editor: markdown
dateCreated: 2025-04-19T19:07:45.351Z
---

# Documentation
https://wiki.archlinux.org/title/Dm-crypt/Specialties
https://wiki.nixos.org/wiki/Full_Disk_Encryption

# Reference

## Add keyfile
```sh
sudo cryptsetup luksAddKey /dev/disk/by-*/<disk> <keyfile>
```

## Dump configuration
```sh
sudo cryptsetup luksDump /dev/disk/by-*/<disk>
```