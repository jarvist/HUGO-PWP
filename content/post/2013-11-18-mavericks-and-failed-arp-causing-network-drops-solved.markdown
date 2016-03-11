---
author: jarvistmoorefrost
comments: true
date: 2013-11-18 11:28:20+00:00
layout: post
slug: mavericks-and-failed-arp-causing-network-drops-solved
title: Mavericks and Failed ARP causing network drops - solved
wordpress_id: 225
post_format:
- Link
tags:
- bath
- bath.ac.uk
- Mavericks
- OS X Mavericks
---

[Mavericks and Failed ARP causing network drops - solved](https://discussions.apple.com/thread/5483424?tstart=0)

Since I started at Bath on an OS X Mavericks machine, my SSH sessions were pausing for 4-6s every minute or so (randomly). Playing with Ping, I saw that correct packet routing was simply failing (averaging 7% packet loss for ping).

Much wailing and gnashing of teeth later, and I found a simple fix. OS X Mavericks Unicast ARP packets were failing - so turn them off with 'sudo sysctl -w net.link.ether.inet.arp_unicast_lim=0'.

2014 update:

Some nice person has now written a little shell script which will automatically apply this patch + create an /etc/sysctl.conf file to rerun the fix at every boot (setting permissions correctly etc.).

[https://raw.github.com/MacMiniVault/Mac-Scripts/master/unicastarp/unicastarp.sh](https://raw.github.com/MacMiniVault/Mac-Scripts/master/unicastarp/unicastarp.sh)
