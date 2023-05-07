---
title: Kali Tricks
author: Fitz
date: 2023-01-15 20:12:00 +0000
categories: [Notes, Kali]
tags: [notes, kali]
---

### Invalid Repos - No packages found
When getting a message like
```
E: Release file for http://http.kali.org/kali/dists/kali-rolling/InRelease is not valid yet (invalid for another 4h 8min 16s). Updates for this repository will not be applied.
```

Typically the time is out of sync
Run the following to fix

```bash
timedatectl status
systemctl restart systemd-timesyncd
timedatectl status
apt update
```
