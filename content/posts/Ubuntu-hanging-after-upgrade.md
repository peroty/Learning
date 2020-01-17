---
title: "Ubuntu hangs trying to mount a share"
date: 2019-12-20T10:04:47 2020-01-16T19:02:41
draft: false
category: learning, linux
---



After upgrading my Ubuntu desktop box from 18.04 to 20.x, after the reboot, the startup process hung trying to mount an NFS share.

`a start job is running for /mnt/location`

To resolve this, I had to boot into recovery mode.

`Hold left shift at startup`

Then edit the fstab file

`nano /etc/fstab`

And removed the NFS shares I was mounting on startup.

I learned this is what the `noauto` option is for when mounting a share. It won't mount the share at startup so it will prevent the machine from hanging like this.