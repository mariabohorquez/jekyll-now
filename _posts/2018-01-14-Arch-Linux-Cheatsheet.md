---
layout: post
title: Arch Linux Cheatsheet
published: true
---

## Useful commands

- Updating System

```bash
sudo pacman -Syu
```
    
- Cleaning pacman's cache

```bash
# leaving 3 of the last versions of each package
sudo paccache -r
# leaving only 1
sudo paccache -rk 1
```
  
- Knowing how much space is being used by the cache

```bash
du -sh /var/cache/pacman/pkg/
```

- Example of using grep to print a section of a man page

```bash
man pacman | grep sync
```


