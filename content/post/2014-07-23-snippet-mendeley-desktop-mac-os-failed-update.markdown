---
author: jarvistmoorefrost
comments: true
date: 2014-07-23 14:51:18+00:00
layout: post
slug: snippet-mendeley-desktop-mac-os-failed-update
title: 'Snippet: Mendeley Desktop (Mac OS) failed update'
wordpress_id: 395
---

Mendeley Desktop on my Mac at work had silently stopped working - clicking the button in Launchpad did nothing. Navigating to the directory on the shell, cd "/Applications/Mendeley\ Desktop.app/Contents/MacOS/" it appeared a prior update had broken halfway through, leaving a null file for 'Mendeley Desktop'. Whoops. However there was a 'Mendeley Desktop.bak'. Running this from the shell, Mendeley Desktop appeared, and then offered to update itself, this time completing successfully. 
