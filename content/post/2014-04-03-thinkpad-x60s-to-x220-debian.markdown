---
author: jarvistmoorefrost
comments: true
date: 2014-04-03 23:05:19+00:00
layout: post
slug: thinkpad-x60s-to-x220-debian
title: Thinkpad X60s to X220 - Debian
wordpress_id: 334
---

I've just bought a new (secondhand) Thinkpad. My previous, a X60s (bought for £150 in Oct 2009) with a cheap generic 8-cell battery, has done me well over the years. Last year I upgraded it to a Samsung SSD, which made playing on the command line super speedy, but websites tended to drag a bit, and PDFs sometimes staggered between frames for tenths of a second when giving talks.
The main issue was that the lovely matt 4:3 ratio screen was dying, the CCFL back light getting weaker and weaker. The screen was never that good, but it was now getting difficult to use during the day.

So I decided to upgrade - and found an el-cheapo X220 (with a French keyboard, AZERTY!) for £172 on eBay. This is the last Thinkpad with the traditional keyboard & aesthetics. I was hoping for one of the 'Premium HD' (IPS) screens, but got a standard TN one. Still, it is much sharper (smaller pixels), brighter and more even than the X60s screen.

Installing Debian Testing from USB (netinstall) was easy enough (it even resized the windows 7 partition, setup dual boot, and with the addition of the requested firmware pulled up my home WiFi for apt-get). I've set up so many accounts recently that cloning & linking in my dot files was second nature.

[![IMG_20140403_232753](http://jarvistmoorefrost.files.wordpress.com/2014/04/img_20140403_232753.jpg?w=466)](http://jarvistmoorefrost.files.wordpress.com/2014/04/img_20140403_232753.jpg)

Side by side with the X60s (medium display brightness, WiFi, Google Chrome in the background) the power consumption of the X220 was a steady 2W below that of the X60s (9.W vs 11.W), which roughly compensates for the fact that the standard large battery is 6 cell. The laptop seems to run cooler, and though the fan comes on more regularly, it is whisper quiet at it's low speeds. (I haven't yet installed Thinkfan, but I will.)

Best of all, this new machine plays HD YouTube videos in full screen.

Macbook Air? Pah! All I ask is a tough stinkpad and a star to steer her by.

2015-01 Edit:

The X220 is so much faster than the X60, and the screen much better (including supporting an external monitor).

However, the hardware is definitely less durable, and lower quality. I really miss the lovely clasp on the X60, the X220 just sort of folds open, the plastic bezel of the screen all cracked and buckling.

One serious issue with it is that it regular wakes from sleep in my bag (and sometimes even just sitting nonchalently on a desk). I decided this was probably linked to the fact the Lid wasn't really attached, and managed to find a route to disable it via the ACPI commands:

[https://bbs.archlinux.org/viewtopic.php?id=146852](https://bbs.archlinux.org/viewtopic.php?id=146852)





    
    <code># echo LID > /proc/acpi/wakeup</code>



