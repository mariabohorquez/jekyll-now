---
layout: post
title: Arch Linux Cheatsheet
published: true
---

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
# if you want free space with desperation. WARNING this erases all the cache
sudo pacman -Scc
```
  
- Knowing how much space is being used by the cache

```bash
du -sh /var/cache/pacman/pkg/
```

- Example of using grep to print a section of a man page

```bash
man pacman | grep sync
```

- Reporting a problem in the forum

```bash
journalctl --since=yesterday | grep "io-slave"
```
- Update to a faster mirrorlist

Create a mirrorlist with [Pacman Mirrorlist Generator](https://www.archlinux.org/mirrorlist/).

```bash
# Modify the file adding your genetared mirrorlist, uncommenting the servers
sudo nano /etc/pacman.d/mirrorlist
# Then refrest the package list
sudo pacman -Syyu
```


