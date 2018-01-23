---
layout: post
title: Information Gathering Cheatsheet
published: true
---

__Commands done as root__

- Using macchanger

```bash
# first turn the interface down
ifconfig eth0 down
# -r (random) -p (permanent/original)
macchanger -r eth0
# The mac address I want
macchanger -m 00:11:22:33:44:55 eth0
```

- ifconfig is for all interfaces, iwconfig only for wireless extensions.

- Using netdiscover and arp-scan to discover your local network

```bash
netdiscover 
arp-scan --localnet
```

- Check tcp connections

```bash
netstat -ntpl
```
