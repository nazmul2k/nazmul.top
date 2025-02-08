---
title: "How to Connect Wifi in Vanilla Arch Linux"
date: 2025-02-08T12:46:03+06:00
draft: false
tags: ['arch linux', 'arch linux install', 'wifi']
---

Connect wifi during installation

```sh
wpa_supplicant -B -i wlan0 -c <(wpa_passphrase "ssid" "passphrase")
```

## Conntect WiFi on first boot

**N.B: Required Network Manager**

```bash
nmcli device wifi connect Your_SSID password Your_Password
```
